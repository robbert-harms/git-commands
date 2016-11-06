# git-commands
Conglomeration of Git commands.

Most of these commands are focused on Python packages with a [GitLab workflow](https://docs.gitlab.com/ee/workflow/gitlab_flow.html):
![alt tag](https://github.com/robbert-harms/git-commands/blob/master/git_workflow.png)

The yellow branch is a release branch, that can sometimes be updated with a hotfix branch. The hotfix is created in master and pushed to master and later cherry picked into the release branch. There are multiple release branches possible. The green branches are feature branches, they are eventually merged into master. It is not necessary to push every master commit into a release branch.


## Workflow commands
Commands needed on a daily basis.


## General useful commands
Useful commands needed once in a while.

#### Adding a tag to a Python package
```sh
git tag -a v$(python setup.py --version) -m 'description of version'
```
#### Removing a tag
```sh
git tag -d <tag_name>
```

#### Using the remote version, overriding all your local updates
```sh
git fetch origin
git reset --hard origin/master
```


#### Finding a deleted file (copied from stackoverflow)
Get a list of the deleted files and copy the full path of the deleted file
```sh
git log --diff-filter=D --summary | grep delete
```
Execute the next command to find commit id of that commit and copy the commit id
```sh
git log --all -- FILEPATH
```
Show diff of deleted file
```sh
git show COMMIT_ID -- FILE_PATH
```
Remember, you can write output to a file using > like
```sh
git show COMMIT_ID -- FILE_PATH > deleted.diff
```


#### Merge another branch with only one commit message
This is useful if you want to merge a bugfix branch or a feature branch but do not want to include all the intermediate commit messages. If you add git commit without the -m flag after the merge, it automatically generates a commit messages from the intermediate messages.
```sh
git checkout master
git merge --squash my_feature_branch
git commit
```
