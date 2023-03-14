#### Add the CodeQL workflow to your repository
1. Navigate to the main page of the repository.
2. Under your repository name, click `Security`.
3. Click `Set up code scanning`. If this option is not available, ask an organization owner or repository administrator to enable GitHub Advanced Security.
4. In the `Get started with code scanning` section, click `Set up this workflow` on the CodeQL analysis workflow.
5. To customize how code scanning scans your code, edit the workflow.
6. Select the `Start commit` drop-down, and type a commit message.
7. Choose whether you'd like to commit directly to the default branch, or create a new branch and start a pull request.
8. Click `Commit new file` or `Propose new file`.



#### Enabling Code Scanning with third-party analysis


#### Code scanning with GitHub Actions and CodeQL
1. Go to the Security tab of your repository.
2. To the right of Code scanning alerts, click Set up code scanning. If code scanning is missing, this means you need to enable GitHub Advanced Security.
3. Under Get started with code scanning, click Set up this workflow on the CodeQL analysis workflow or on a third-party workflow. Note: Workflows are only displayed if they are relevant for the programming languages detected in the repository. The CodeQL analysis workflow is always displayed, but the "Set up this workflow" button is only enabled if CodeQL analysis supports the languages present in the repository.
4. To customize how code scanning scans your code, edit the workflow. Generally you can commit the CodeQL analysis workflow without making any changes to it. However, many of the third-party workflows require additional configuration, so read the comments in the workflow before committing.
5. Use the Start commit drop-down, and type a commit message.
6. Choose whether you'd like to commit directly to the default branch, or create a new branch and start a pull request.
7. Click Commit new file or Propose new file.