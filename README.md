# ISPP 2023 Showcase Project

Guide to simulate the golden flow and obtain metrics out of it using Governify ecosystem.

![Golden Flow Diagram](https://github.com/governifyauditor/ispp-2023-showcase-project/blob/main/img/goldenflow.png?raw=true)

This figure shows the Golden Flow, a workflow for projects in which different teams contribute individually to a large code repository. The upstream repository is forked and each planned feature is developed by a member of the team in a separate branch. Once a feature is completed, a pull request (PR) is opened for the whole team to discuss
the changes, and if accepted, merge the changes to the forked repository's main branch. Once merged, the main branch is deployed to the staging server for the client to validate new functionality. If the client signs off on the feature, another PR is opened to merge the changes into the main repository so the feature can be included in the production server.

## Prerequisites

### Create projects and tools
If you already have your tools setup you can skip this part.

First, you need to set up your different development tools:
 - Create Github Repository
 - Create a GitHub Project ([Guide](https://github.com/governifyauditor/ispp-2023-showcase-project/blob/main/guides/GHProjects.md))

### Bluejay
 - Create an info.yml file. For this purpose you can use Bluejay's ([wizard](https://join.bluejay.governify.io/wizard)). You can also use this [example](https://github.com/governifyauditor/ispp-2023-showcase-project/blob/main/info.yml), which shows how the info.yaml it should look like. This file will be used by Bluejay to know the different identities of your tools to evaluate and determine the different indicators.

### Governify auditor project invite
The Governify auditor should be present on the private tools in order to have access to your information:
 - GitHub: If your repository is public or it is present on your organization there is no need to add the auditor. If not, you'll need to add him by going to Settings→Manage access on your repository and click on the green button labeled as `Invite a collaborator`. Enter `governifyauditor` and accept.

![GH invite](https://github.com/governifyauditor/ispp-2023-showcase-project/blob/main/img/auditor1.png?raw=true)

Bear in mind that you might need to wait for the Governify auditor to accept the invitations in order for the points to appear in the dashboard.

## Join in Bluejay's system
Follow this steps:
1. Access to [https://join.bluejay.governify.io/?course=ISPP-2023](https://join.bluejay.governify.io/?course=ISPP-2023). This is the view for joining into the system and start the tools audition.

![Join 1](https://github.com/governifyauditor/ispp-2023-showcase-project/blob/main/img/join1.png?raw=true)

2. Enter your Repository URL. For example, `https://github.com/governifyauditor/ispp-2023-showcase-project` would be the URL of this repository.

3. Click on Check. Once checked, any errors concerning your info.yml file will appear. Correct them if you have any. If after fixing an error it keeps appearing wait 5 minutes before trying again.

4. If no errors are found, you'll get a success message and a new section will appear. Click on Join and you should see a success message. Congrats! You successfully completed the process of joining. If you have any problem when accomplishing this section, you can contact [governify.auditor@gmail.com](mailto:governify.auditor@gmail.com) for troubleshooting.

## Golden flow

In order to see how the process works we are going to explain each different stage to complete a successful iteration of one feature using golden flow.

### New branch - In progress issues correlation
1. Create a card in the "Todo" column on Github Projects kanban and convert it to issue.
2. Move the card to the "In progress" column.
3. Create a branch including in the name the number of the issue you've just created on step 1 (Check image below to see its location and the second image showing a branch name example based on the Issue number).

`Issue number location:`

![Issue number](https://github.com/governifyauditor/ispp-2023-showcase-project/blob/main/img/golden21.png?raw=true)

`GitHub Branch name:`

![Github branch name](https://github.com/governifyauditor/ispp-2023-showcase-project/blob/main/img/golden22.png?raw=true)

### Open PR - In review issues correlation
4. Modify the branch adding some changes to it. 
5. Move the issue to the `In review` column.
6. Open a PR from the created branch to main.

### Merge PR - Done issues correlation
7. Review the PR as a team. Don't rush it (1 hour) or it won't appear in the system.
8. Move the issue to the `Done` column.
9. Accept and merge the PR.

## Team practices
There are 7 TPs (Team practices) being audited:


- Correlation in progress issues and branches - At least 75% of in progress issues must match creation of a branch (Per team, every day).
- Correlation in review issues and open PRs - At least 75% of in review issues must match creation of a PR (Per team, every day).
- Correlation done issues and merged PRs - At least 75% of done issues must match the merge of a PR (Per team, every day).
- PRs with positive reviews - At least one positive review in each merged pull requests (Per team, every week).
- In progress issues - The amount of issues in the "In Progress" column must be equal or less than 1 (Per member, every hour). 
- Done issues - The amount of issues in the "Done" column must be greater than 1 every (Per member, every week). 
- Comments in PRs - The amount of comments in every pull requests must be greater than 1 (Per member, every week).

Every hour, the TPs are computed and verified to check they are being fulfilled.
