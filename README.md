<p align="center">
  <img src="https://github.com/mode/public-site/blob/master/source/about/img/mode-logo-green.png" alt="mode logo" />
</p>

----
## Overview

GitHub sync is a two way connection between Mode and the default branch of your GitHub repository (usually called `main` or `master`). Changes made in Mode can be pushed to the GitHub repository, and changes made in GitHub will automatically be pushed to Mode. GitHub sync enables you to:
 - View all changes happening in your Mode organization
 - Make multiple changes across many queries or notebooks
 - Back up and restore all the components of your Mode analysis, including: queries, definitions, notebooks, reports, and themes

### Mode -> GitHub
Edit reports in Mode as usual. When you are ready to sync changes to GitHub, click Report > Push to GitHub, enter a commit messages to describe the changes and your updates will be pushed to GitHub.

### GitHub -> Mode
Any commit to the default branch in your GitHub repo will automatically trigger a sync to Mode. You can commit changes directly to `main/master` or create a branch in GitHub to work on code without impacting production reports. Changes must be committed to the default branch in order to be reflected in Mode.

Changes to this README won't be synced to any content in Mode, so feel free to edit and update it as needed.

## Repository Structure

When initialized, the repository will be structured as shown below:

```
Mode/                          // All Mode orgs get installed into "Mode" directory in the repo
├── org-foo/                   // Directory name is org username
|  ├── definitions/
|  |  ├── definition-1.sql
|  |  └── definition-2.sql
|  ├── spaces/
|  |  └── space_foo/
|  |      ├── report_foo.token/
|  |      |   ├── query-1.token.sql
|  |      |   ├── query-2.token.sql
|  |      |   ├── index.html
|  |      |   ├── settings.yml
|  |      |   └── python-notebook/
|  |      |       ├── cell-1.token.py
|  |      |       └── cell-2.token.py
|  |      ├── report_bar.token/
|  |      |   ├── query-1.token.sql
|  |      |   ├── query-2.token.sql
|  |      |   ├── index.html
|  |      |   ├── settings.yml
|  |      |   └── python-notebook/
|  |      |       ├── cell-1.token.py
|  |      |       └── cell-2.token.py
|  |      └── archived/
|  |          └──report_old.token/
|  |             ├── query-1.token.sql
|  |             ├── query-2.token.sql
|  |             ├── index.html
|  |             └── settings.yml
|  ├── themes/
|  |  ├── theme-1.css
|  |  └── theme-2.css
|  └── README.md
```

All code synced from your Mode Analytics organization to your Github repository will be stored under a top-level directory called 'Mode'. This is to allow you to nest other analytics code (e.g. dbt, airflow, etc.) within this repository.

## Repository Contents

What gets synced when you initialize your Mode/GitHub integration?

 - Spaces - All shared and private Spaces will be automatically synced. No personal or community Spaces will be synced.
 - Reports - All reports in applicable spaces.
 - Themes - All report themes.
 - Definitions - All definitions.

## User Administration

Please also note that administration of users will be up to you. Anyone making changes through the Mode UI can sync those changes. However, if users want to make changes in GitHub they'll need to be added to the repo in GitHub.

## Visibility of your GitHub Repository
- If you have non-Mode data in the GitHub repository used for GitHub sync, please be aware that Mode has visibility to the entire repository.
- Reports in private spaces will be synced to your GitHub repo. Anyone with access to the GitHub repo will be able to see the files associated with these reports (though they still won't have access to the reports in Mode unless they're added to the corresponding spaces).

## Important notes

 Please do not start your commit messages with `[Mode]` as this could cause the sync to malfunction.

## Additional Documentation

 For help getting set up, see [Setting up GitHub to integrate with Mode](https://mode.com/help/articles/github/#github-%E2%86%92-mode).

 For details about how the integration works, see [Using Mode with GitHub](https://mode.com/help/articles/github/#mode-%E2%86%92-github).
