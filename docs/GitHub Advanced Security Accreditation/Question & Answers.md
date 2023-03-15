1. What is the name of the code scanning workflow file? 
    - `codeql-analysis.yml`

2. You want to add the CodeQL workflow to your repository. What is the correct navigation path to achieve that? 
    - `Security` > `Set up code scanning` > `Set up this workflow`

3. What action GitHub Actions uses to upload a third-party SARIF file to a repository? 
    - `upload-sarif`

4. How to exclude `.md` and `.txt` files from code scanning?
    ```yml
    paths-ignore:
      - '**/*.md'
      - '**/*.txt'
    ```
  
5. What is the first step in codeQL analysis? 
    - creating database

6. How does CodeQL database creation work for compiled languages?
    - monitoring normal build process

7. What parameter do you use when you want to use external configuration file for code scanning?  
    - `config-file`

8. When you use language matrix in your code scanning workflow, what does it mean? 
    - CodeQL is analyzes only the languages in the matrix

9. What building options there are for compiled languages in code scanning?
    - auto-build, manually add build steps

10. What do you need when you are creating custom pattern for secret scanning (select two)? 
    - Pattern name, secret format

11. In which document do you tell how to report a security vulnerabilities in the project? 
      - `SECURITY.md`

12. Two questions about depandabot.yml syntax:
    - First one asks about the top level keys:
        - version and updates 
    - the second about the keys under updates: 
        - package-ecosystem, directory and schedule.interval

13. How many required reviewers does Depandabot assign by default without a configured depandabot.yml file? Options: 0, 1, 2 or 3
    - 0

14. In query suite file, what metadata tag matches on the last path component of the query? 
    - query filename

15. What is the instruction in a query suite file to look for one or more specified .ql files? 
      - query

16. What query metadata property results in a simple alert? 
    - '@kind problem'

17. Question about notification settings contents. Don't remember the specific question, but familiarise yourself with those settings.
    - By default users receive notifications:
        - By email
        - In the GitHub UI
        - In the GitHub mobile app
        - On the command line
        - In your inbox
    - You can change the default settings in `Settings` > `Notifications` > `Dependabot alerts`

18. What are the consequences of someone ignoring code scanning alerts? 
    - Using data insecurely, passing dangerous arguments to functions and leaking sensitive information.

19. What is a mandatory key in dependabot.yml 
    - version

20. What is default access for the actions scope for the restricted GITHUB_TOKEN 
    - none

21. How you verify that you have configured correctly CodeQL CLI setup? 
    - run subcommands, as available languages

22. What is required to communicate with GraphQL server?
    - token with `user`, `public_repo`, `repo`, `repo_deployment`, `repo:status`, `read:repo_hook`, `read:org`, `read:public_key` and `read:gpg_key` scopes

23. What is end point for GraphQL API? 
    - `https://api.github.com/graphql`

24. What are direct dependencies?
    - Dependencies that are explicitly defined in the manifest or lock file.

25. When is a Dependabot alert generated?
    - Whenever a new vulnerability is added to the GitHub Advisory Database.

26. What is a prerequisite for Dependabot to automatically enable security updates for a repository?
    - Repository is public

27. What query can you use to view all the notifications you've marked as done?
    - `is:done`

28. To which area of focus does GitHub dependency management belong?
    - Supply chain

29. What's the purpose of security advisories?
    - To provide a safe space for code maintainers to discuss how to best address errors and vulnerabilities found in the codebase.

30. Which GitHub feature is powered by CodeQL?
    - Code scanning

31. What does the term 'shifting left' mean?
    - Incorporating security principles early in the software development lifecycle

32. Which technology does GitHub use to authenticate one application with another?
    - Secrets

33. What's a common cause of security breaches?
    - Administrators delay patching a system after updates are available.

34. What do you need to do if you want to change the settings for secret scanning on a public repository?
    - Switch the repository to a private one with GitHub Advanced Security

35. Where can you configure the recipients of secret scanning alerts?
    - In the Security and analysis settings of a repository

36. How many custom patterns can you create for an organization?
    - 500

37. When code scanning is enabled, what is one default event that triggers a scan?
    - Pushing a change.

38. Which of the following are the tools used to upload a SARIF file?
    - The tools used are GitHub Actions, the code scanning API, and the CodeQL CLI.

39. What is the difference between scheduled versus triggered events in code scanning?
    - Scheduled events run based on a specified schedule and triggered events run on code events such a push.

40. What are three main commands for the CodeQL CLI?
    - `codeql database create`
    - `codeql resolve languages`
    - `codeql resolve qlpacks`

41. Which command definition is required to use in order to create database with multiple languages?
    - `--db-cluster` along with `--no-run-unnecessary-builds` to suppress the build command for languages where the CodeQL CLI doesn't need to monitor the build process.

42. What does CodeQL first do when creating a database?
    - Extracts a single relational representation of each source file

43. What is the format of the command used to create and analyze CodeQL database from the CLI?
    - `codeql [command] [subcommand]`

44. What is an extractor?
    - A tool that produces the relational data

45. The CLI's built-in search operations does which of the following?
    - Automatically looks in all of its sibling directories for the files used in the database creation and analysis

46. By default, which severity level will cause a pull request check failure when using code scanning?
    - Error

47. Which is one way to optimize CodeQL analysis runtimes?
    - Increase the memory

48. What are three default query suites?
    - `code-scanning`
    - `security-extended`
    - `security-and-quality`

49. What file QL pack must contain?
    - `qlpack.yml`

50. What is the format for all QL extensions?
    - `.ql`: query
    - `.qll`: library
    - `.qls`: sequence of instructions

51. In CodeQL, errors like bugs and vulnerabilities are modeled as:
    - Queries

52. How many default query suites are there with GitHub code scanning with CodeQL?
    - 3

53. What are all the parts of a CodeQL database?
    - Hierarchical representation of the code
    - data-flow graph
    - control-flow graph
    - A representation of the language's abstract syntax tree

54. To create a database, CodeQL extracts:
    - A single relational representation of each source file in the codebase.

55. How does CodeQL database creation work for compiled languages?
    - For compiled languages, extraction works by monitoring the normal build process.

56. What are all the steps of CodeQL analysis?
    - Creating database
    - Running queries against the database
    - Interpreting the results

57. What feature does QL add to the Datalog programming language?
    - Support for aggregates

58. One major difference between QL and general purpose programming languages is:
    - QL does not have any imperative features such as assignments to variables or file system operations.

59. What semantics of QL are based on?
    - Datalog

60. What enables you to customize how code scanning analyzes your code?
    - The code scanning workflow

61. Dave's company wants to use GitHub actions to generate code scanning alerts. What tools can they use for code analysis?
    - CodeQL or supported third party tools.

62. What are two options for specifying which queries you want to run with CodeQL code scanning?
    - Using code scanning workflow
    - Using a custom configuration file

63. How to specify query packs in a workflow file?
    ```yaml
    - uses: github/codeql-action/init@v1
      with:
        # Comma-separated list of packs to download
        packs: scope/pack1,scope/pack2@1.2.3,scope/pack3@~1.2.3
    ```

64. What is required to use if the queries are in a private repository?
    - `external-repository-token` parameter with `${{ secrets.ACCESS_TOKEN }}`

65. What options are available for referencing other queries in a workflow file?
    - Workflow files can reference query packs, individual query files, and query suite files.

66. What is the method for ensuring that any packs or queries referenced in a custom configuration file are run in addition to the ones included in the workflow file?
    - Prefix the value of packs or queries in the workflow file with the `+` symbol.

67. What is the basic CodeQL query file extension structure and what it should contain?
    - file extension structure is `.ql` and contains a `select` clause.

68. What are the two types of queries and what it requires?
    - @kind has only two options:
      - problem (same as Alert queries) 
      - path problem (same as Path queries)
    - metadata is required

69. How qlpack.yml syntax looks like?
    ```yml
    name: codeql/java-queries
    version: 0.0.6-dev
    groups: java
    suites: codeql-suites
    extractor: java
    defaultSuiteFile: codeql-suites/java-code-scanning.qls
    dependencies:
        codeql/java-all: "*"
        codeql/suite-helpers: "*"
    ```

70. How to use query packs in the workflow file?
    ```yml
    packs:
    # Use the latest version of 'pack1' published by 'scope'
    - scope/pack1
    # Use version 1.23 of 'pack2'
    - scope/pack2@v1.2.3
    # Use the latest version of 'pack3' compatible with 1.23
    - scope/pack3@~1.2.3
    ```

71. How to use queries in the workflow file?
    ```yml
    queries:
      - uses: ./my-basic-queries/example-query.ql
      - uses: ./my-advanced-queries
      - uses: ./query-suites/my-security-queries.qls
    ```

72. What action is required to load config-file?
    - `github/codeql-action/init@v1`

73. How to disable default queries in the workflow file?
    - By setting `disable-default-queries` parameter to `true`

74. What is the method for specifying other queries in a custom configuration file?
    - A 'queries' array where each element contains a 'uses' parameter.

75. Dave's repository contains code in multiple languages, but he would like CodeQL code scanning to only analyze C++ and Python. Which of the following options is a method to do that?
    - List the languages that he wants to analyze in the 'languages' array in the workflow file.
    - An example:
    ```yml
      packs:
        # Use these packs for JavaScript analysis
        javascript:
          - scope/js-pack1
          - scope/js-pack2
        # Use these packs for Java analysis
        java:
          - scope/java-pack1
          - scope/java-pack2@v1.0.0
      ```

76. What are the commands in order to analyze or upload results to GitHub?
    - `codeql database analyze`
    - `githb upload-results`

77. What is the appropriate syntax to create a database with multiple languages?
    ```bash 
    codeql database create <database> --command<build> \
    --db-cluster --language=<language-identifier>,<language-identifier>
    ```

78. What does the `--command` syntax do?
    - tell the tool the build command for the codebase

79. Which command is used to create a CodeQL database using the CLI?
    - codeql database create

80. What is the file format generated by use of the database analyze command?
    - SARIF

81. Manual build steps in your workflow file are necessary in which situation?
    - If there are supported languages with a non-standard build process.

82. Autobuild is currently succeeding for one of the languages in Layla's repository, but failing for another. What should she do?
    - Add language-specific build commands for the language where autobuild is failing.

83. Which GitHub Advanced Security feature is not available on public repositories? (Secret scanning, Security Overview, Code scanning)
    - Security Overview

84. Where can you enable GitHub Advanced Security for all the private and internal repositories in an organization?
    - In the organization's Code and security settings

85. What can you do to ensure that everyone in your organization is using GitHub Advanced Security?
    - Set a security policy at the organization level

86. What should you keep in mind when using GitHub Actions for your security workflows?
    - You should correctly set up the permissions for the GITHUB_TOKEN used to make authenticated API calls.

87. What file should you use to create documentation for collaborators that lists supported versions of the project?
    - `SECURITY.md`

88. What tool should you use to automate part of your security process?
    - Add Dependabot to your code base

89. Which two pieces of information should be included in a security advisory?
    - Product affected and severity

90. What two pieces of information are included in your organization’s log?
    - The user that performed the action and the date and time of the action

91. What are all the information logs includes?
    - which repository an action was performed in
    - the user that performed the action 
    - which country/region the action took place in
    - the date and time of the action

92. What GHAS features are not accessible from the user interface?
    - CodeQL and third-party tool integration

93. Code scanning is using GitHub Advisory Database. Where this database populates information from?
    - 1) National vulnerability database, 2) combination of machine learning and human reviews to detect vulnerabilities in public commits on GitHub, 3) Security advisories reported on GitHub, 4) The npm Security advisories database.

94. What features Dependabot provides?
    - Dependabot alerts, security updates, verion updates

95. The `version` configuration in `dependabot.yml` file must be set to:
    - `2`

96. What are required names for configuration files in GHAS?
    - `dependabot.yml`: for Dependabot configuration
    - QL pack must contain a `qlpack.yml` file
    - code scanning workflow file must be named as `codeql-config.yml`
    - 
  

97. Who will the secret scanning tool notify about the breach?
    - organization owner, repository administrator, and author of commits that trigger the alert

98. What is a supported custom media type for the code scanning REST API?
    - `application/sarif+json`

99. With what version data is fromatted as SARIF?
    - `2.1.0`

100. How CodeQL works during data base creation for interpreted languages?
    - CodeQL extracts a single relation representation of each source file in the codebase by running on the source code, resolving dependencies to give an accurate representation of the codebase.

101. How many options users have for specigying which queries to run with CodeQL code scanning?
    - Two options, using code scanning workflow or a custom configuration file.

102. What are the options to specify the additional queries?
    - `packs` to install one or more CodeQL query packs
    - `queries` to specify a single `.ql` file, a directory containing multiple `.ql` files, query definition file `.qls`, or any combintation
    - It is possible to use both packs and queries in the same workflow file.

103. How to add one or more CodeQL query packs?
    - by using `with: packs` parameter along with the `uses: github/codeql-action/init@v1` action in the workflow file.

104. How to specify a comma-separated list of packs to download in the workflow?
    ```yml 
    - uses: github/codeql-action/init@v1
      with:
        # Comma-separated list of packs to download
        packs: scope/pack1,scope/pack2@1.2.3,scope/pack3@~1.2.3
    ```

105. What is the value to provide a token to access queries stored in private repository?
    - `external-repository-token: ${{ secrets.ACCESS_TOKEN }}`

106. What query suites are built into CodeQL code scanning tool?
    - `code-scanning, security-extended and security-and-quality`

107. What is the action to take to specify the configuration file for CodeQL code scanning in the workflow file?
    - by using `github/codeql-action/inite@v1` along with `with: config-file: <path-to-config-file>` parameter.

108. How to refernce to a configuration file located in a external repositroy?
    - by using `OWNER/REPOSITORY/FILENAME@BRANCH` syntax
  
109. How do you specify and CodeQL query packs to run in a custom configuration file?
    - by using a nested map of packs:
    ```yml
    packs:
      # Use these packs for JavaScript analysis
      javascript:
        - scope/js-pack1
        - scope/js-pack2
      # Use these packs for Java analysis
      java:
        - scope/java-pack1
    ```

110. What is the rule for character when using `paths-ignore` keyword?
    - characters can only be at the start or end of a line, or surrounded by slashes. For example `foo/**, **/foo, and foo/**/bar` are all valid patterns.

111. What kind of information CodeQL database schema includes?
    - `expressions` and `statements` tables
    - CodeQL library defines classes to provide a layer of abstraction over the each of these tables. This includes the related auxuliary tables `Expr` and `Stmt`.
  
112. What are the levels to monitor security alerts using Security overview?
    - `Organization`, `Team` and `Repository` levels

113. What are the permissions you can grant to users on each level of your control over GitHub Advanced Security?
    - `None`, `Read`, `Write` and `Admin` permissions

