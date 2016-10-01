# git-commands
Conglomeration of Git commands.

Most of these commands are focused on Python packages with a [GitLab workflow](https://docs.gitlab.com/ee/workflow/gitlab_flow.html). 

## Workflow commands
Commands needed on a daily basis.


## General useful commands
Useful commands needed once in a while.

#### Adding a tag to a Python package
```sh
git tag -a v$(python setup.py --version) -m 'description of version'
```
