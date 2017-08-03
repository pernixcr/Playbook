# Git workflow

## Branching 
- __master__
Only for production, the changes here should be fully tested and ready for release.
- __develop__
Development branch, this branch will have nightly changes.
- __feature branches__
Feature branch, this branch will be related to a certain user story or task.

## How to create a new branch
1. Checkout develop branch
    ```
    git checkout develop
    ```
2. Make sure you have the latest changes in your local environment.
    ```
    git fetch && git pull origin develop
    ```
2. Create a new branch with a proper name, in this case we will use 10 as the user story number (card_number-feature-task).
    ```
    git checkout -b 10-sign_up-sign_up_view
    ```

    This way have the user story number and then a descriptive name for the user story.

## Commits
Commits should have a proper name 

1. Pull master

git checkout master
git pull --rebase
2. Create a branch

Create a descriptive branch name. We use branch prefixes to classify a branch as a feature, chore or bug.

git checkout -b feature/my_awesome_new_idea
3. Do work, and make commits

Commit messages should follow this guide.

4. Rebase master

Your branch should be fully tested and have a passing build. Rebasing will apply any new commits from master to your branch.

git checkout master
git pull --rebase
git checkout feature/my_awesome_new_idea
git rebase master
5. Open a pull request

git push origin feature/my_awesome_new_idea
Find your branch on GitHub and click the pull request button.

6. Merge the branch

This should be done by the code reviewer. A --no-ff merge ensures that a merge bubble is preserved in the commit log.

git checkout master
git merge --no-ff feature/my_awesome_new_idea
Your default text editor will display a merge commit message. Save the file to apply the merge.
