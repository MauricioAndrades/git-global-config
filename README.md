# Global GitConfig

> A General Reference & Backup of my `$HOME/.gitconfig` file. 

```shell

[user]
    name = localUser
    email = localUserEmail

[credential]
    helper = osxkeychain

[filter "lfs"]
    clean = git-lfs clean %f
    smudge = git-lfs smudge %f
    required = true

[alias]
    co = checkout
    loglast = log -1 HEAD
    undo= reset --soft HEAD^
    rmc = rm --cached -r .
    lsf = ls-files -s
    bp = big-picture

[alias]
    lg  = !"git lg1-specific --all"
    lg2 = !"git lg2-specific --all"
    lg3 = !"git lg3-specific --all"

    lg1-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(yellow)%d%C(reset)'

    lg2-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%n'

    lg3-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset) %C(yellow)%d%C(reset)'' %C(white)%s%C(reset)'' %C(dim white)- %cn %C(reset) %C(dim white)'
    
[push]
    default = simple
[core]
    excludesfile = /Users/Op/.gitignore_global
[difftool "sourcetree"]
    cmd = opendiff \"$LOCAL\" \"$REMOTE\"
    path =
[mergetool "sourcetree"]
    cmd = /Applications/SourceTree.app/Contents/Resources/opendiff-w.sh \"$LOCAL\" \"$REMOTE\" -ancestor \"$BASE\" -merge \"$MERGED\"
    trustExitCode = true

```

```shell

# ls current branch
alias gsbc=" git show-branch --current"

# ls config
alias gconfig=" git config --list"

# show origin
alias gfrom=" git config --get remote.origin.url"

# view recent
alias grecent=" git recent -a"

# view relationship between two repos
alias gitrel=" git relation $1 $2"

# clear the index cache
alias grmcached="git rm -r --cached ."

# self explanatory
alias gadot="git add ."

# remove untracked files from index
alias grmig="git ls-files --ignored --exclude-standard | xargs git rm --cached"

```

#FULL COMMAND LIST:

`git add` - Add file contents to the index

`git am` - Apply a series of patches from a mailbox

`git annotate` - Annotate file lines with commit information

`git apply` - Apply a patch to files and/or to the index

`git archimport` - Import an Arch repository into Git

`git archive` - Create an archive of files from a named tree

`git bisect` - Find by binary search the change that introduced a bug

`git blame` - Show what revision and author last modified each line of a

`git branch` - List, create, or delete branches

`git bundle` - Move objects and refs by archive

`git cat-file` - Provide content or type and size information for

`git check-attr` - Display gitattributes information

`git check-ignore` - Debug gitignore / exclude files

`git check-mailmap` - Show canonical names and email addresses of

`git checkout` - Checkout a branch or paths to the working tree

`git checkout-index` - Copy files from the index to the working tree

`git cherry` - Find commits yet to be applied to upstream

`git cherry-pick` - Apply the changes introduced by some existing commits

`git citool` - Graphical alternative to git-commit

`git clean` - Remove untracked files from the working tree

`git clone` - Clone a repository into a new directory

`git column` - Display data in columns

`git commit` - Record changes to the repository

`git commit-tree` - Create a new commit object

`git config` - Get and set repository or global options

`git count-objects` - Count unpacked number of objects and their disk

`git credential` - Retrieve and store user credentials

`git credential-cache` - Helper to temporarily store passwords in memory

`git credential-store` - Helper to store credentials on disk

`git cvsexportcommit` - Export a single commit to a CVS checkout

`git cvsimport` - Salvage your data out of another SCM people love to

`git cvsserver` - A CVS server emulator for Git

`git daemon` - A really simple server for Git repositories

`git daemon` - A really simple server for Git repositories

`git describe` - Show the most recent tag that is reachable from a commit

`git diff` - Show changes between commits, commit and working tree, etc

`git diff-files` - Compares files in the working tree and the index

`git diff-index` - Compare a tree to the working tree or index

`git diff-tree` - Compares the content and mode of blobs found via two

`git difftool` - Show changes using common diff tools

`git fast-export` - Git data exporter

`git fast-import` - Backend for fast Git data importers

`git fetch` - Download objects and refs from another repository

`git fetch-pack` - Receive missing objects from another repository

`git filter-branch` - Rewrite branches

`git format-patch` - Prepare patches for e-mail submission

`git fsck` - Verifies the connectivity and validity of the objects in the

`git fsck-objects` - Verifies the connectivity and validity of the

`git gc` - Cleanup unnecessary files and optimize the local repository

`git grep` - Print lines matching a pattern

`git gui` - A portable graphical interface to Git

`git hash-object` - Compute object ID and optionally creates a blob from

`git help` - Display help information about Git

`git http-backend` - Server side implementation of Git over HTTP

`git http-fetch` - Download from a remote Git repository via HTTP

`git http-push` - Push objects over HTTP/DAV to another repository

`git imap-send` - Send a collection of patches from stdin to an IMAP

`git index-pack` - Build pack index file for an existing packed archive

`git init` - Create an empty Git repository or reinitialize an existing

`git init-db` - Creates an empty Git repository

`git instaweb` - Instantly browse your working repository in gitweb

`git interpret-trailers` - help add structured information into commit

`git log` - Show commit logs

`git ls-files` - Show information about files in the index and the

`git ls-remote` - List references in a remote repository

`git ls-tree` - List the contents of a tree object

`git mailinfo` - Extracts patch and authorship from a single e-mail

`git mailsplit` - Simple UNIX mbox splitter program

`git merge` - Join two or more development histories together

`git merge-base` - Find as good common ancestors as possible for a merge

`git merge-file` - Run a three-way file merge

`git merge-index` - Run a merge for files needing merging

`git merge-tree` - Show three-way merge without touching index

`git mergetool` - Run merge conflict resolution tools to resolve merge

`git mktag` - Creates a tag object

`git mktree` - Build a tree-object from ls-tree formatted text

`git mv` - Move or rename a file, a directory, or a symlink

`git name-rev` - Find symbolic names for given revs

`git notes` - Add or inspect object notes

`git p4` - Import from and submit to Perforce repositories

`git pack-objects` - Create a packed archive of objects

`git pack-redundant` - Find redundant pack files

`git pack-refs` - Pack heads and tags for efficient repository access

`git patch-id` - Compute unique ID for a patch

`git prune` - Prune all unreachable objects from the object database

`git prune-packed` - Remove extra objects that are already in pack files

`git pull` - Fetch from and integrate with another repository or a local

`git push` - Update remote refs along with associated objects

`git quiltimport` - Applies a quilt patchset onto the current branch

`git read-tree` - Reads tree information into the index

`git rebase` - Forward-port local commits to the updated upstream head

`git receive-pack` - Receive what is pushed into the repository

`git reflog` - Manage reflog information

`git relink` - Hardlink common objects in local repositories

`git remote` - Manage set of tracked repositories

`git remote-ext` - Bridge smart transport to external command.

`git remote-fd` - Reflect smart transport stream back to caller

`git repack` - Pack unpacked objects in a repository

`git replace` - Create, list, delete refs to replace objects

`git request-pull` - Generates a summary of pending changes

`git rerere` - Reuse recorded resolution of conflicted merges

`git reset` - Reset current HEAD to the specified state

`git rev-list` - Lists commit objects in reverse chronological order

`git rev-parse` - Pick out and massage parameters

`git revert` - Revert some existing commits

`git rm` - Remove files from the working tree and from the index

`git send-email` - Send a collection of patches as emails

`git send-pack` - Push objects over Git protocol to another repository

`git shell` - Restricted login shell for Git-only SSH access

`git shortlog` - Summarize 'git log' output

`git show` - Show various types of objects

`git show-branch` - Show branches and their commits

`git show-index` - Show packed archive index

`git show-ref` - List references in a local repository

`git stage` - Add file contents to the staging area

`git stash` - Stash the changes in a dirty working directory away

`git status` - Show the working tree status

`git stripspace` - Remove unnecessary whitespace

`git submodule` - Initialize, update or inspect submodules

`git subtree` - Merge subtrees together and split repository into

`git svn` - Bidirectional operation between a Subversion repository and

`git symbolic-ref` - Read, modify and delete symbolic refs

`git tag` - Create, list, delete or verify a tag object signed with GPG

`git unpack-file` - Creates a temporary file with a blob's contents

`git unpack-objects` - Unpack objects from a packed archive

`git update-index` - Register file contents in the working tree to the

`git update-ref` - Update the object name stored in a ref safely

`git upload-archive` - Send archive back to git-archive

`git upload-pack` - Send objects packed back to git-fetch-pack

`git var` - Show a Git logical variable

`git verify-commit` - Check the GPG signature of commits

`git verify-pack` - Validate packed Git archive files

`git verify-tag` - Check the GPG signature of tags

`git web`--browse - Git helper script to launch a web browser

`git whatchanged` - Show logs with difference each commit introduces

`git worktree` - Manage multiple worktrees
