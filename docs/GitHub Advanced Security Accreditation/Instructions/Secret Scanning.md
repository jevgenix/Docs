### Enable secret scanning for a private repository
1. In your repository, navigate to `Settings > Security & analysis`.
2. Under `Configure security and analysis features`, click the `Enable` button next to `GitHub Advanced Security`.
3. Review the impact of enabling Advanced Security and click `Enable GitHub Advanced Security` for this repository.
4. Click the `Enable` button next to `Secret scanning`. If you see a `Disable button`, it means that secret scanning was already enabled at organization level.


### Enable secret scanning for an organization

1. In your organization, navigate to `Settings` > `Security & analysis`.
2. Under `Configure security and analysis features`, click the `Enable` all button next to GitHub Advanced Security.
3. Review the impact of enabling Advanced Security on all repositories and click Enable all.
4. Click the Enable all button next to Secret scanning.
5. Optionally enable the feature by default for new repositories in your organization, and click Enable for eligible repositories.

### Creating a custom secret pattern for Secret Scanning
1. In your repository, navigate to Settings > Code security & analysis.
2. Under GitHub Advanced Security > Secret scanning, click New pattern.
3. Provide the following details for your custom pattern:
    - The name of the pattern
    - The pattern of the secret specified as Hyperscan regex
    - A sample test string to make sure your configuration is matching the patterns you expect
