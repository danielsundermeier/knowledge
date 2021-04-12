# Github

- [Oh Shit, Git!?!](https://ohshitgit.com/)
- [Git Concepts I Wish I Knew Years Ago ](https://dev.to/g_abud/advanced-git-reference-1o9j)
- [Git Magic](https://crypto.stanford.edu/~blynn/gitmagic/ch01.html)

## Pull Requests

1. [Fork](https://guides.github.com/activities/forking/) the Repository
2. Connect your local to the original “upstream” repository by adding it as a remote
3. [Create a branch](https://guides.github.com/introduction/flow/) for your edits.

### Links

- [Fork and Pull Request Workflow](https://github.com/susam/gitpr)
- [Contributing to an open source PHP package](https://johnbraun.blog/posts/contributing-to-a-PHP-package)

## Actions

- [GitHub Action for GitHub Push](https://github.com/ad-m/github-push-action) - GitHub Actions for pushing to GitHub repository local changes authorizing using GitHub token.
- [GitHub Actions: Hello World](https://lab.github.com/githubtraining/github-actions:-hello-world)

## Issues

- [Improving GitHub Issue Labels](http://karolis.koncevicius.lt/posts/improving_github_issue_labels/)

## Braches

- [A successful Git branching model (2020)](https://nvie.com/posts/a-successful-git-branching-model/)

## Commits

- [Conventional Commits](https://www.conventionalcommits.org/)

## Secrets

- [Best practices for managing and storing secrets](https://blog.gitguardian.com/secrets-api-management/)

## Config

### Deploy Key

```
ssh-keygen -t rsa -b 4096 -C "{email}"
cat .ssh/id_rsa.pub

ssh -T git@github.com
```

.git/config:
```
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
[remote "origin"]
        url = git@github.com:user/repo.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
        remote = origin
        merge = refs/heads/master
```

[Using Github Deploy Key](https://gist.github.com/zhujunsan/a0becf82ade50ed06115)
