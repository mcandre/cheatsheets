# Subversion Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/svn.md

# About

Subversion is a tried-and-true version control system.

# Documentation

[Version Control with Subversion](http://svnbook.red-bean.com/)

[man svn](http://man.cx/svn)

# Install

On some operating systems (Mac OS X), Subversion is built-in. Otherwise, install with:

```
$ apt-get install subversion

$ brew install subversion

C:\> chocolatey install tortoisesvn
```

[TortoiseSVN-1.8.10.msi](http://tortoisesvn.net/downloads.html)

# Configure

```
$HOME/.subversion/config
```

[Reference Dotfile](https://github.com/jspahrsummers/dotfiles/blob/master/.subversion/config)

# Create a repository

Setup a Subversion server and repo (e.g. with [SourceForge](http://sourceforge.net/), [Assembla](https://www.assembla.com/), [Beanstalk](http://beanstalkapp.com/), [Bountysource](https://www.bountysource.com/), or even [GitHub](https://help.github.com/articles/support-for-subversion-clients/)).

# Checkout a local copy of a repository

```
$ svn checkout <SVN URL> <local-name>
```

Example:

```
$ svn checkout http://checkthread.googlecode.com/svn/ checkthread
```

# Add new files to version control

```
$ svn add <files or folders>
```

# Remove files from version control

```
$ svn rm [-r] [-f] <files or folders>
```

# Commit to both local and remote repositories

```
$ svn add <files or folders>
$ svn commit
```

svn commit takes an optional `-m <message>` to enter the message directly into the shell.

# Clear away uncommitted changes

```
$ svn revert -R <files or folders>
```

# Reverse specific commits

A safe option is to unmerge a commit, a sort of Subversion Undo operation:

```
$ svn merge -c<commit> .
$ svn commit
```

# View most recent commits

```
$ svn log -l 4
```

# View difference between two commits

```
$ svn diff -r <commit a>:<commit b>
```

# Pull remote changes into local repo

```
$ svn update
```

# Exclude certain files and folders from version control

```
$ svn propedit svn:ignore .
```

This launches a text editor, at which point you edit the ignore patterns. Then you need to commit the changes to the ignore property.

```
$ svn diff
$ svn commit
```

# Create a branch, locally and remotely

```
project (trunk)$ svn copy http://svn.example.com/repos/calc/trunk http://svn.example.com/repos/calc/branches/myfeature -m 'My Feature'
project (trunk)$ cd ..
project$ svn checkout http://svn.example.com/repos/calc/branches/myfeature
project$ cd myfeature/
project (myfeature)$
```

# List branches

```
$ svn ls ^/branches
myfeature
trunk
```

# Delete branches and/or tags

In Subversion, branches and tags are not special, they're just folders that happen to be used as branches or tags. Therefore, they can be deleted with:

```
$ svn delete <branch or tag URL> -m <message>
```

Then

```
$ svn up
```

Or

```
$ rm -rf <local copy of branch or tag>
```

# Svn Prompt

You can display the current Subversion branch in your shell prompt by following the Svn Prompt setup instructions:

https://github.com/mcandre/svn-prompt/blob/master/svn-prompt.sh

# Merge another branches' changes into current branch

```
project (myfeature)$ cd ../trunk/
project (trunk)$ svn merge -r<myfeature creation revision>:HEAD http://svn.example.com/repos/calc/branches/myfeature
project (trunk)$ svn commit
```

# Create a tag

```
project (trunk)$ svn copy http://svn.example.com/repos/calc/trunk http://svn.example.com/repos/calc/tags/v1.0 -m "Bump to v1.0"
project (trunk)$ cd ../tags/
project$ svn checkout http://svn.example.com/repos/calc/tags/v1.0
project$ cd v1.0
```

# List tags

```
$ svn ls ^/tags
v1.0
```

# Convert a svn repo to git

See https://github.com/mcandre/cheatsheets/blob/master/git.md#convert-a-svn-repo-to-git

# Repositories

* GitHub https://github.com/
* Google Code https://code.google.com/
* Assembla https://www.assembla.com/home
* Beanstalk http://beanstalkapp.com/
* SourceForge http://sourceforge.net/

## Integration

Subversion can integrate with non-Subversion repositories:

* git svn https://www.kernel.org/pub/software/scm/git/docs/git-svn.html
* hgsubversion https://bitbucket.org/durin42/hgsubversion/overview/

# Alternatives

* [Git](https://github.com/mcandre/cheatsheets/blob/master/git.md)
* [Mercurial](http://mercurial.selenic.com/)
* [Darcs](http://darcs.net/)
