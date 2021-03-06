# Git Commands Cheat Sheet

A list of git commands and some example command chains for increased productivity

## Cloning

`git clone [GIT_LINK]`

## Pushing

Push and remember branch:

`git push -u origin [BRANCH_NAME]`

Push to remembered branch:

`git push [BRANCH_NAME]` or simply `git push`

## Workflow

Add, commit, and push:

`git add . && git commit -m 'MESSAGE_HERE' && git push`

Shorthand:

`git commit -am 'MESSAGE_HERE' && git push`

Note: This only works on currently tracked files. If you have created any new files on the current commit, you must use the long version:

`git add . && git commit -m 'MESSAGE_HERE' && git push`

## Commits

Basic commit message:

`git commit -m 'MESSAGE_HERE'`

Commit with a title and description:

`git commit -m 'TITLE_HERE' -m 'DESCRIPTION_HERE'`

## Branches

View local branches:

`git branch`

View remote branches:

`git branch -r`

Get remote branch currently not on local:

`git switch [BRANCH_NAME]`

Switch to different local branch

`git checkout [BRANCH_NAME]`

## Pulling

Get the latest from a remote branch:

`git pull origin [BRANCH_NAME]`

## CREATE NEW BRANCH BASED OF EXISTING BRANCH (eg. main)

Create the branch:

`git branch [NEW_BRANCH_NAME]`

Switch to the new branch:

`git checkout [NEW_BRANCH_NAME]`

Push the branch up to GitHub:

`git push --set-upstream origin [NEW_BRANCH_NAME]`

## CREATE NEW BRANCH, AND BRING UNCOMMITTED CHANGES TO IT

Create the branch:

`git checkout -b [NEW_BRANCH_NAME]`

Push the branch up to GitHub:

`git push --set-upstream origin [NEW_BRANCH_NAME]`

Commit the changes to the new branch:

`git add . && git commit -m 'MESSAGE_HERE' && git push -u origin `[NEW_BRANCH_NAME]

## CREATE NEW EMPTY BRANCH (IGNORED FILES WILL STILL REMAIN)

Create the branch:

`git switch --orphan [NEW_BRANCH_NAME]`

Make first commit:

`git commit --allow-empty -m "Initial commit on orphan branch"`

Make sure you are on the new empty branch:

`git branch`

Push the branch up to GitHub:

`git push -u origin [NEW_BRANCH_NAME]`

## DELETE BRANCHES:

Locally:

`git branch -d [BRANCH_NAME]`

Remotely:

`git push origin --delete [BRANCH_NAME]`

## MERGE ONE BRANCH INTO ANOTHER:

`git checkout [BRANCH_TO_MERGE_INTO]`

`git pull origin [BRANCH_TO_MERGE_INTO]`

`git merge [BRANCH_TO_MERGE_FROM]`

`git push -u origin [BRANCH_TO_MERGE_INTO]`

## SWITCH BACK TO MAIN AFTER PR MERGE:

After merging the PR, GitHub allows you to safely delete the branch. Do that if possible

Switch to main branch:

`git checkout main`

Get latest from GitHub:

`git pull origin main`

Delete the branch locally:

`git branch -d [BRANCH_NAME]`

Delete the branch remotely:

`git push origin --delete [BRANCH_NAME]`

## MERGE A SPECIFIC COMMIT:

`git cherry-pick [SHA_CODE]`

## RESET ALL CURRENT CHANGES ON CURRENT LOCAL BRANCH:

`git restore .`

## FATAL / CANNOT PUSH TO GITHUB (LIKELY A PROXY ISSUE):

`git config --global --unset http.proxy && git config --global --unset https.proxy`

## CONFIGURE GIT TO USE YOUR PREFERRED TEXT EDITOR:

Atom:

`git config --global core.editor "atom --wait"`

Sublime Text:

`git config --global core.editor "subl -n -w"`

Visual Studio Code:

`git config --global core.editor "code --wait"`
