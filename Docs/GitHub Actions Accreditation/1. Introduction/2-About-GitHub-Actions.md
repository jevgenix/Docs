# About Actions

### GitHub Actions types

There are three types of GitHub Actions:

1. <b>JavaScript Actions</b> - these actions don't include the environment in the code. Users should specify the environment for these actions. User can execute them in a VM in the cloud or on-premises. JavaScript Actions supports Linux, macOS and Windows environment. 

    Example of JavaScript Action
    ```yml
        steps:
            - uses: actions/checkout@v1
            - name: npm install and build webpack
            run: |
              npm install
              npm run build
    ```

    JavaScript actions can run directly on the runner machine and separate the action code from the environment that is used to run the action. The action code is simplified and can execute faster that actions within a Docker container. In order to create and use packaged JavaScript Actions, Node.js within the npm should be downloaded. Optional and recommended step would be using GitHub Actions toolkit Node.js, which is a collection of Node.js packages that enables developers to quickly build JavaScript actions with more consistency. Here are the steps to take to build a JavaScript actions:
    
    1.  Create an `action.yml` metadata file to define the inputs and outputs of the action as well as tell the action runner how to start running this JavaScript action
    2.  Create an `index.js` file with context information about the `Toolkit packages`, `routing`, and other functions of the action.
    3.  Commit and push action to GitHub with the following files: `action.yml`, `index.js`, `node_modules`, `package.json`, `package-lock.json` and `README.md`.


2. <b>Container Actions</b> - there environment is part of the action's code. These Actions can only be run in a Linux environment that GitHub hosts.

    Example of Container Action
    ```yml
        name: "Hello Actions"
        description: "Greet someone"
        author: "octocat@github.com"

        # Getting value of a variable called MY_NAME
        # Variable will be set in the workflow that runs this action
        inputs:
            MY_NAME:
              description: "Who to greet"
              required: true
              default: "World"


        runs:
            # uses requires the path to the Dockerfile
            using: "docker"
            image: "Dockerfile"

        # Branding personalizes the action in the GitHub Marketplace 
        # if user decides to publish it there
        branding:
            icon: "mic"
            color: "purple"
    ```
    Docker Containers package the environment with the GitHub Actions code. This means that the actions runs in a consistent and reliable environment because all of its dependencies are within that container. If the action needs to run in a specific environment configuration, then Docker containers are a good way to go because you can customize the operating system and tools. It often requires to build and retrieve the container, that is why Docker container actions are slower than JavaScript acctions. In order to start, developer should follow:
    
    1.  Create a `Dockerfile` to define the commands to assemle the Docker image
    2.  Create an `action.yml` metadata file to define the inputs and outputs of the action. Set the `runs: using:` value to `docker` and the `runs: image:` value to `Dockerfile` in the file.
    3.  Create an `entrypoint.sh` file to describe the docker image.
    4.  Commit and push the action to GitHub with the following files: `action.yml`, `entrypoint.sh`, `Dockerfile`, and `README.md`.


3. <b>Composite run actions</b> - this action enable to reuse actions using shell scripts. Developer can mix multiple shell languages within the same action. For example if developer have a multiple shell scripts to automate several tasks, he/she can turn them into action and reuse them for different workflows. Sometimes it's easier to just write a shell script than using JavaScript or wrapping code into a Docker container. Example of composite run action below:

    ```yml
    name: 'Hello World'
    description: 'Greet someone'
    inputs:
      who-to-greet:  # id of input
        description: 'Who to greet'
        required: true
        default: 'World'
    outputs:
      random-number:
        description: "Random number"
        value: ${{ steps.random-number-generator.outputs.random-number }}
    runs:
      using: "composite"
      steps:
        - run: echo Hello ${{ inputs.who-to-greet }}.
          shell: bash
        - id: random-number-generator
          run: echo "random-number=$(echo $RANDOM)" >> $GITHUB_OUTPUT
          shell: bash
        - run: echo "${{ github.action_path }}" >> $GITHUB_PATH
          shell: bash
        - run: goodbye.sh
          shell: bash
    ```
    

## GitHub Hosted versus self-hosted runners

- A runner is a server that has the GitHub Actions runner application installed. For example `runs-on: ubuntu-latest` will run using the `GitHub-hosted` <b>runner</b> that is running in the environment ubuntu-latest. If user uses a GitHub-hosted runner, each job will run in a fresh instance of the virtual environment that is specified in `runs-on: {operating system-version}` command.
- A self-hosted runner is a server that user manage himself. In order to use it, user must apply the self-hosted label, it's operating system and the system architecture. For example, a <b>self-hosted</b> runner with a <b>Linux</b> operating system and <b>ARM32</b> architecture would look like the following, `runs-on: [self-hosted, linux, ARM32]`.

Each type of runner has its own advantages and disadvantages. For example it is quicker and easier to start with GitHub-hosted runners, but they are not as flexible as self-hosted runners. On the other hand, self-hosted runners are more flexible, but they require more time and effort to set up and maintain.

## Metadata and syntax in order to create an action
Before creating or reviewing a GitHub action, the first step is to review the `action.yml` file to assess which inputs, outputs, descritpion, and other configuration information are needed for the action. Some of these parameters are required while other are optional. The table below represents these parameters that the `action.yml` file should define about the action:

| <b>Parameter</b>  |<b>Description</b>|<b>Required</b>|
|--------------|-----------|--------|
|Name        | The name of your action. Helps visually identify the action in a job.|<b>yes</b>|
|Description| A summary of what your action does.|<b>yes</b>|
|Runs       | The command to run when the action executes.|<b>yes</b>|
|Inputs      | Input parameters enable you to specify data that the action expects to use during runtime. These parameters become environment variables in the runner.|<b>no</b>|
|Outputs    | Output parameters enable you to specify data that subsequent actions can use later in the workflow after the action that defines these outputs has run.|<b>no</b>|
|Branding   | Color and Feather icon to use to create a badge to personalize and distinguish your action in GitHub Marketplace.|<b>no</b>|

## Runs, Inputs, Outputs, Branding

### Runs (required)
`runs` is a required statement which defines the command necessary to execute the action. Wether it's container, JavaScript or composite run steps action, the `runs` syntax is defined differently.

1. `runs` for Docker actions </br>
    Docker container action require that the `runs` statement configures the image used for the Docker action with the following arguments:
    -   `using`: needs to be set to `docker` to run a Docker container action.
    -   `image`: Docker image used as the container to run the action.

    ```yml
    runs:
      using: 'docker'
      image: 'Dockerfile'
    ```

2. `runs` for JavaScript actions </br>
    JavaScript actions require that the `runs` statements take the following two arguments:
    -   `using`: application used to execute the code as defined in `main`.
    -   `main`: file that contains the action code. The application defined in `using` executes this file.

    ```yml
    runs:
      using: 'node12'
      main: 'main.js'
    ```

3. `runs` for composite run steps actions </br>
    Composite run steps actions require that the `runs` statement take the following arguments:
    -   `using`: needs to be set to `composite` to run a composite run step
    -   `steps`: run steps to run the action.
    -   `steps[*].run`: command you want to run (can be inline or a script in action repository)

    ```yml
    runs:
      using: "composite"
      steps:
        - run: ${{ github.action_path }}/test/script.sh
          shell: bash
    ```

### Inputs
Inputs are the parameters that enable to specify data that the action expects to use during its runtime. GitHub stores these input parameters as environment variables. The example below is a list of inputs for an action. The `firstNameStudent` input is optional while the `studentGrade` input is required.

  ```yml
  inputs:
    firstNameStudent:
      description: 'First name of student'
      required: false
      default: '1'
    studentGrade:
      description: 'Grade of the student'
      required: true
  ```

### Outputs (optional)
Outputs are the parameters that enables to declare data. Actions that run later in a workflow can use the output data that was declared in a previosuly ran action. 

  ```yml
  outputs:
    average:
      description: 'The average grade of the students'
  ```

### Branding (optional)
An optional but fun feature is the ability to customiza the badge of action. The badge is displayed next to the action name in the `GitHub Marketplace`. The color and Feather icon can be used to create the badge. For branding should be specified the icon and color.

  ```yml
  branding:
    icon: 'shield'  
    color: 'blue'
  ```
The example of a badge for the Checkout action on the GitHub Marketplace:
![GitHub-Actions-Marketplace-Badge](./images/actions-branding.png)

