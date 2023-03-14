# Introduction to Actions

`GitHub Actions` are packaged scripts to automate tasks in a software development workflow in GitHub. User can configure GitHub Actions to trigger complex workflows that meet his organization's needs. By using GitHub Actions developers can build a reliable and sustainable automated workflow, which leads to a significant decrease in development time. GitHub Actions are scripts that adhere to a yml data format. <br>
Each repository has an Actions tab that provides a quick, automated and easy way to get started with setting up first workflow. If user want to see the workflow, the great way to start would be selecting `Configure` button to add the script and beging editing the source YML.

##### Beyond this features Actions tab allows users to:
- Search for GitHub Actions in the GitHub Marketplace.
- Search for open-source projects.
- Write own GitHub Actions from scratch.

#### Using GitHub Actions to decrease development time

All of the tasks that must happen after the code is written, but before the code can be reliably used for its purpose, can be automated with GitHub Actions.
##### This includes:
- Ensuring the code passes all unit tests
- Performing code quality and compliance checks to make sure the source code meets the organization's standards
- Checking the code and its dependencies for known security issues
- Building the code integrating new source from (potentially) multiple contributors
- Ensuring the software passes integration tests
- Versioning the new build
- Delivering the new binaries to the appropriate filesystem location
- Deploying the new binaries to one or more servers

If any of these tasks do not pass, actions reports the issue to the proper individual or team for resolution automatically. This allows the development team to focus on writing code, and not on the tasks that must happen after the code is written! This is just an example of an ideal job for worklow automation, however the biggest challenge is to do these tasks reliable, consistently and in a suistanable manner.

## Open-source GitHub Actions
There are plenty of open source actions available for anyone who wants to use them. Open-source doesn't mean these actions are secure. User's must carefully check them before using then in their project. 

##### Recommended community stadart with open-source software is:
- Including README file
- Including Code of Conduct
- Including Contributing file
- Including issue templates
<br>

###### Before user's start using open-source Actions, GitHub recommends to check following:
- Review the action's `action.yml` file for inputs, outputs, and to make sure the code does what it says it does.
- Check if the action is in the GitHub Marketplace. This is a good check, even if an action does not have to be on the GitHub Marketplace to be valid.
- Check if the action is verified in the GitHub Marketplace. This means that GitHub has approved the use of this action. However, you should still review it before using it.
- Include the version of the action you're using by specifying a Git ref, SHA, or tag.

