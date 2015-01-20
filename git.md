# Git Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/git.md

# About

Git is a decentralized version control system.

# Documentation

[Git Documentation](http://git-scm.com/doc)

[Try Git](https://try.github.io/levels/1/challenges/1)

[Pro Git](http://git-scm.com/book/en/v2)

[Git flow](http://nvie.com/posts/a-successful-git-branching-model/)

# Install

```
$ apt-get install git

$ brew install git

C:\> chocolatey install git
```

[git-1.9.5.exe](http://git-scm.com/download/win)

# Configure

    ~/.gitconfig

[Reference Dotfile](https://gist.github.com/pksunkara/988716)

`~/.gitconfig` can be edited manually, and/or specific fields can be set with `git config` commands:

```
$ git config --global user.name "<Your Name>"
$ git config --global user.email <your@email.com>
$ git config --global core.editor emacs
```

# SSH Keys

Git encourages authentication with SSH keys, skipping the need for password authentication. Consult your [GitHub](https://help.github.com/articles/generating-ssh-keys/) or [GitLab](http://doc.gitlab.com/ce/ssh/ssh.html) documentation for more information on setting up SSH keys.

# Create a repository

```
$ git init
```

# Add new or changed files to version control

```
$ git add <files or folders>
```

## Add an empty directory to version control

Git does not version control folders, only files. To effectively force Git to add a directory to version control, we can add a dummy file, `.gitkeep` to the desired folder.

```
$ mkdir empty/
$ touch empty/.gitkeep
$ git add empty/
$ git commit
```

# Remove files from version control

```
$ git rm [-r] [-f] <files or folders>
```

# Create a local commit

```
$ git add <files or folders>
$ git commit
```

git-commit takes an optional `-m <message>` to enter the message directly into the shell.

git-commit can load the text editor of your choice for writing commit messages, by customizing `.gitconfig`.

# Push a local changes to remote

```
$ git push
```

Or

```
$ git push origin master
```

# Pull remote changes into local repo

```
$ git pull
```

# Exclude certain files and folders from version control

```
$ vi .gitignore
$ git add .gitignore
$ git commit
```

Example: https://github.com/mcandre/dotfiles/blob/master/.gitignore

# Create a local branch

```
project (master)$ git checkout -b myfeature
project (myfeature)$
```

# Git Prompt

You can display the current Git branch in your shell prompt by following the Git Prompt setup instructions:

https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh

# Merge another branches' changes into current branch

```
project (master)$ git merge myfeature
project (master)$ git commit
```

# Create a tag

```
$ git tag -a v1.0 -m 'bump to v1.0'
```

# List locally known tags

```
$ git tag -l
v1.0
```

# Push tags

```
$ git push --tags
```

# Pull tags

```
$ git pull --tags
```

# Checkout a branch at a tag

The first argument to `git-checkout -b` is the name of the branch we will create.

The second argument is the tag from which we want to base our branch. We can safely use the same name for our branch as our tag.

```
project (master)$ git checkout -b v1.0 v1.0
project (v1.0)$
```

# Hooks

Any scripts named `.git/hooks/post-merge`, `.git/hooks/post-checkout`, etc., will be run as a side effect of the associated Git process.

Example:

https://github.com/mcandre/dotfiles/blob/master/hooks/post-merge-checkout

# Stash

Git offers a spare queue for temporarily storing code changes, useful when editing Git history.

## Move changes since last commit into a new stash element

```
$ git stash
$ git status
nothing to commit, working directory clean
```

## Move stash change onto current files

```
$ git stash apply
```

# Alternatives

* [Mercurial](http://mercurial.selenic.com/)
* [Subversion](https://subversion.apache.org/)
* [Darcs](http://darcs.net/)
