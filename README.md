# git-commands
Conglomeration of Git commands.

Most of these commands are focused on Python packages with a [GitLab workflow](https://docs.gitlab.com/ee/workflow/gitlab_flow.html):
![alt tag](https://github.com/robbert-harms/git-commands/blob/master/git_workflow.png)


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
