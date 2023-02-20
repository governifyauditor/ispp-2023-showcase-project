# ISPP 2023 Showcase Project

Guide to simulate the golden flow and obtain metrics out of it using Governify ecosystem.

![Golden Flow Diagram](https://github.com/governifyauditor/ispp-showcase-project/blob/main/img/goldenflow.PNG?raw=true)

This figure shows the Golden Flow, a workflow for projects in which different teams contribute individually to a large code repository. The upstream repository is forked and each planned feature is developed by a member of the team in a separate branch. Once a feature is completed, a pull request (PR) is opened for the whole team to discuss
the changes, and if accepted, merge the changes to the forked repository's main branch. Once merged, the main branch is deployed to the staging server for the client to validate new functionality. If the client signs off on the feature, another PR is opened to merge the changes into the main repository so the feature can be included in the production server. 

All this flow is supported by different tools including deployment, CI and project management tools. In this guide three different tools for this purposes (Heroku, Travis and GitHub Projects) will be explained to correctly use them for fulfilling a set of TPs explained at the end of this document.

## Prerequisites

### Create projects and tools
If you already have your tools setup you can skip this part.

First, you need to set up your different development tools:
 - Create Github Repository
 - Create a GitHub Project ([Guide](https://github.com/governifyauditor/ispp-showcase-project/blob/main/guides/GHProjects.md))
 - Add GitHub Repository to Travis-CI and configure a simple workflow ([Guide](https://github.com/governifyauditor/ispp-showcase-project/blob/main/guides/Travis.md))
 - Create Heroku App and enable automatic deploys ([Guide](https://github.com/governifyauditor/ispp-showcase-project/blob/main/guides/Heroku.md))

### Bluejay
 - Create info.yml file. You can use this [template](https://github.com/governify/audited-project-template/blob/main/info.yml) and also take a look at this [example](https://github.com/governifyauditor/ispp-showcase-project/blob/main/info.yml) showing what it should look like. This file will be used by Bluejay to know the different identities of your tools to evaluate and determine the different indicators.

### Governify auditor project invite
The Governify auditor should be present on the private tools in order to have access to your information:
 - GitHub: If your repository is public or it is present on your organization there is no need to add the auditor. If not, you'll need to add him by going to Settings→Manage access on your repository and click on the green button labeled as `Invite a collaborator`. Enter `governifyauditor` and accept.

![GH invite](https://github.com/governifyauditor/ispp-showcase-project/blob/main/img/auditor1.PNG?raw=true)

 - Heroku: You'll need to add the auditor as a collaborator. On your app dashboard view, click on `Access` at the top and then `Add collaborator`. Enter governify.auditor@gmail.com and save changes.

![H invite](https://github.com/governifyauditor/ispp-showcase-project/blob/main/img/auditor3.PNG?raw=true)

 - Travis: You don't need to add the auditor if the repository is public. If it isn't, having the auditor on your GitHub repo is required.

Bear in mind that you might need to wait for the Governify auditor to accept the invitations in order for the points to appear in the dashboard.

## Join in Bluejay's system
Follow this steps:
1. Access to [https://join.bluejay.governify.io/?course=ISPP-2021](https://join.bluejay.governify.io/?course=ISPP-2021). This is the view for joining into the system and start the tools audition.

![Join 1](https://github.com/governifyauditor/ispp-showcase-project/blob/main/img/join1.PNG?raw=true)

2. Enter your Repository URL. For example, `https://github.com/governifyauditor/ispp-showcase-project` would be the URL of this Repository.

3. Click on Check. Once checked, any errors concerning your info.yml file will appear. Correct them if you have any. If after fixxing an error it keeps appearing wait 5 minutes before trying again.

4. If no errors are found, you'll get a success message and a new section will appear. Click on Join and you should see a success message. Congrats! You successfully completed the process of joining. If you have any problem when accomplishing this section, you can contact [governify.auditor@gmail.com](mailto:governify.auditor@gmail.com) for troubleshooting.

## Golden flow
Make sure that your repository files look something like this before continuing (not mandatory to be a node.js app but travis and heroku should be configured. The file "travis.yml" and "Procfile" should be present.):

![Files](https://github.com/governifyauditor/ispp-showcase-project/blob/main/img/repoReady.PNG?raw=true)

In order to see how the process works we are going to explain each different stage to complete a successful iteration of one feature using golden flow.

### New branch - In progress issues correlation
1. Create a card in the "Backlog" column on Github Projects by pressing the button `+` on the top part of the column, entering a title for them and then clicking on the `Add` button. After it, convert it to issue by opening the menu, clicking on the three dots button on the right top corner of the card, and then clicking on "Convert to issue".
2. Then, move the card to the "In progress" column.
3. Create a branch including in the name the number of the issue you've just created on step 1 (Check image below to see its location and the second image showing a branch name example based on the Issue number).

`Issue number location:`

![Issue number](https://github.com/governifyauditor/ispp-showcase-project/blob/main/img/golden21.PNG?raw=true)

`GitHub Branch name:`

![Github branch name](https://github.com/governifyauditor/ispp-showcase-project/blob/main/img/golden22.PNG?raw=true)

### Open PR - In review issues correlation
4. Modify the branch adding some changes to it. 
5. Move the issue to the `In review` column.
6. Open a PR from the created branch to main.

### Merge PR - Done issues correlation
7. Review the PR as a team. Don't rush it (10 minutes) or it won't appear in the system.
8. Move the issue to the `Done` column.
9. Accept and merge the PR.

## Team practices
There are 5 TPs (Team practices) being audited:
- In progress issues - New branch: At least 75% of in progress issues must match creation of a branch by the whole team.
- In review issues - Open PR: At least 75% of in review issues must match creation of a PR by the whole team.
- Done issues - Merge PR: At least 75% of done issues must match the merge of a PR by the whole team.
- Heoroku release - Merge PR: At least 75% of releases must match a the merge of a PR into master within ten minutes by the whole team.
- Travis successful builds: At least 80% of Travis builds should pass correctly by the whole team.

Every ten minutes the TPs are computed and verified to check they are being fulfilled.
