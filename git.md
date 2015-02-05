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

```
~/.gitconfig
```

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

## Partial commit

Git can commit specific line changes, temporarily ignoring other line changes.

```
$ git add -p
```

This launches an interactive patch session in which a commit is constructed based on user selections of yes (`y`), no (`n`), or split (`s`) for each change to consider.

Then commit the partial changes:

```
$ git commit
```

# View most recent commits

```
$ git log
```

# View difference between two commits

```
$ git diff <commit a> <commit b>
```

For more ways to view Git history, see Pro Git Chapter 2:

http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History

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

# How to checkout a branch at a tag

Git purists will complain that you can't *technically* checkout a tag, but we can effectively do this by checking out a new branch *based* on a tag.

```
project (master)$ git checkout -b v1.0 v1.0
project (v1.0)$
```

Here, we supplied the tag name as the second argument, and the same tag name as the first argument, to git-checkout.

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

# Checkout specific commits

Sometimes you want to revisit an earlier commit:

```
$ git checkout <commit>
```

# Moving HEAD

Sometimes you need to point HEAD to a commit:

```
$ git reset <commit ID> [--hard]
```

# Delete a local commit

Reset to an earlier commit and continue working.

# Delete a recent commit from a remote

```
$ git reset --hard <an earlier commit>
$ git push origin HEAD --force
```

If you are quick enough, this will alter Git history on the remote before anyone has pulled the commit you deleted. This could save you if you accidentally pushed sensitive information in a commit.

But in many cases, this will result in a very awkward state, almost corrupting your fellow Git users' Git histories.

# Reverse specific commits

Generally, the safer option is to revert the commit, a sort of Git Undo operation:

```
$ git revert <commit-to-remove> [<another-commit-to-remove> ...]
$ git push
```

# Cherry pick commits from one branch to another

```
$ git checkout <destination-branch>
project (destination branch)$ git cherry-pick <desired-commit>
```

# Convert a svn repo to git

## Quick and dirty (no svn history)

```
$ cd project/
project$ find . -type d -name .svn -exec rm -rf {} \;
project$ git init && git add . && git commit && git remote add origin <...> && git push
```

## Slow and steady (keep svn history)

This may require upgrading to latest Git (e.g., `brew install git`).

```
$ cd svnproject/
svnproject$ svn log --stop-on-copy .
<revision start point>

$ mkdir gitproject/
gitproject$ git init
gitproject$ git svn clone -r <revision start point>:HEAD <svn URL> .
```

Create a remote on GitHub/GitLab/BitBucket/Google Code, etc. Then:

```
gitproject$ git remote add origin <...>
gitproject$ git push
```

# Repositories

* GitHub https://github.com/
* BitBucket https://bitbucket.org/
* GitLab https://about.gitlab.com/
* Google Code https://code.google.com/
* Assembla https://www.assembla.com/home
* Beanstalk http://beanstalkapp.com/
* Gitorious https://gitorious.org/
* repo.or.cz http://repo.or.cz/
* SourceForge http://sourceforge.net/

Git can integrate with Subversion repositories with [git svn](https://www.kernel.org/pub/software/scm/git/docs/git-svn.html).

# Alternatives

* [Mercurial](http://mercurial.selenic.com/)
* [Subversion](https://subversion.apache.org/)
* [Darcs](http://darcs.net/)
