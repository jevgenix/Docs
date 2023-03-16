### Enable the dependency graph for private repositories
1. Go to your GitHub repository.
2. Select your repository `Settings`.
3. Select `Code security and analysis`.
4. Select `Enable` in the dependency graph section


### View the dependency graph
1. Go to your `GitHub` repository.
2. Select your repository `Insights`.
3. Select `Dependency` graph.
4. You can select the `Dependencies` or `Dependents` tab from the Dependency graph view.


### Set up Dependabot alerts for private repositories
1. Sign in to your GitHub account and select your profile photo from the upper right.
2. Select Settings, then select Code security and analysis under Security in the left-side menu.
3. Select Enable all to the right of the feature you want to enable.
4. If you would like these settings to be applied to all new repositories in your organization, then select the Enable by default for new private repositories checkbox.
5. Select Enable FEATURE to enable the feature for all the repositories you own.


### Set up Dependabot alerts for organizations
1. Sign in to your GitHub account and select your profile photo from the upper-right.
2. Select Your organizations.
3. Select Settings next to the organization for which you would like to enable Dependabot alerts.
4. Select Code security and analysis from the left sidebar.
5. On the Configure security and analysis features page, select Enable all next to the feature you want to turn on.
6. If you would like these settings to be applied to all new repositories in your organization, select the Enable by default for new private repositories checkbox.
7. Select Enable FEATURE to enable the feature for all the repositories in your organization.


### Grant access to Dependabot alerts
1. Go to the main page of the repository.
2. In the left menu, select Code security and analysis.
3. In the Access to alerts section, type the name of the person or team that you would like to be able to manage Dependabot alerts in the search bar. Make your selection.
4. Select Save changes.


#### Resolve Dependabot alerts
After Dependabot alerts are enabled, it requires to create a process to regularly review and resolve the them.
The following steps explain how to resolve Dependabot alerts:

1. Go to the main page of the repository
2. Select the `Security tab` for the repository
3. Select `Dependabot alerts` from the security sidebar. A list of the Dependabot alerts for that repository will display
4. Select the alert you would like to view.
5. Review the alert details. In some cases, the alert may contain a pull request with an automated security update.
6. Resolve the alert by taking one of the following actions:
    - Review and merge the pull request.
    - Select Create Dependabot security update to manually fix the vulnerability.
    - Select the Dismiss dropdown and choose a reason for dismissing the vulnerability.

### Manually enable security updates
1. Sign in to your GitHub account and select your profile photo from the upper-right.
2. Select Settings > Code security and analysis.
3. Select Enable for Dependabot security updates.


### View dependencies being montiredby Dependabot
1. Go to the main page of the repository.
2. Under your repository name, select `Insights`.
3. Select `Dependency graph` in the left sidebar.
4. Select `Dependabot`.
5. Select the three dots next to a package manager to view the files being monitored.


### Version updates on forks
1. Go to the main page of the repository where you want to enable version updates.
2. Select `Insights`.
3. Select `Dependency graph` from the left sidebar.
4. Select `Dependabot`.
5. Select `Enable Dependabot`.


### Allow Dependabot to access private repositories
1. Go to the security and analysis settings for your organization.
2. Under `Grant Dependabot access to private repository`, select `Add private repositories` or `Add internal and private repositories`.
3. Start typing the name of the repository you want to allow.
4. Select the repository you want to allow.
5. Optionally, to remove a repository from the list, go to the right of the repository and select X.
