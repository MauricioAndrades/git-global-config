## Cheat Sheet

usage comm:

    git clone url
    git init
    git init --bare
    git update-server-info

    git add file1 file(n)
    git add dir
    git add .
    git rm file1 file(n)
    git commit -a -m "message"

    git push remote branch: update remote(defaultname: origin)
    git pull remote (default name: origin)

    git diff
    git diff --cached
    git diff HEAD
    git diff rev [path(s)]
    git status

    git show rev:file
    git ls-files [-t]
    git ls-files --others
    git log
    git log [path(s)]


`$ git branch --help` or `$git log --help`

### Essential Git Commands

####Create a new git repository
`$ git init` - Create a new, local repository

#### Repo Status
`$ git status` - Check the status of your current repository and see which files have changed.

`$ git diff` - Show changes between commits, commit and working tree, etc

    git diff [options] [<commit>] [--] [<path>...]
    git diff [options] --cached [<commit>] [--] [<path>...]
    git diff [options] <commit> <commit> [--] [<path>...]
    git diff [options] <blob> <blob>
    git diff [options] [--no-index] [--] <path> <path>


#### Repo History
`$ git log` - __Fill Me Out__

`$ git log --oneline --decorate --color --graph --all` - __Fill Me Out__

`$ git log -p filename` __Fill Me Out__

#### Stage files to commit
`$ git add `<filename>`` - __Fill Me Out__

`$ git add -A` - -A, --all, --no-ignore-removal
>    Update the index not only where the working tree has a file
>    matching `<pathspec>` but also where the index already has an entry.
>    This adds, modifies, and removes index entries to match the working
>    tree.

#### Commit changes in staged files

`$ git commit -m "<commit message>"` - __Fill Me Out__

####Branching

`$ git branch <branch name>` - __Fill Me Out__

`$ git branch` - List, create, or delete branches

    git branch --color=`<when>` | --no-color -r | -a
       --list -v --abbrev=`<length>` | --no-abbrev
       --column=`<options>` | --no-column
    (--merged | --no-merged | --contains) `<commit>` `<pattern>`...
    git branch --set-upstream | --track | --no-track -l -f `<branchname>` <start-point>
    git branch (--set-upstream-to=`<upstream>` | -u `<upstream>`) `<branchname>`
    git branch --unset-upstream `<branchname>`
    git branch (-m | -M) `<oldbranch>` `<newbranch>`
    git branch (-d | -D) -r `<branchname>`...
    git branch --edit-description `<branchname>`

    -d, --delete
Delete a branch. The branch must be fully merged in its upstream
branch, or in HEAD if no upstream was set with --track or
--set-upstream.

    -D
Delete a branch irrespective of its merged status.

    -l, --create-reflog
Create the branch's reflog. This activates recording of all changes
made to the branch ref, enabling use of date based sha1 expressions
such as "<branchname>@{yesterday}". Note that in non-bare
repositories, reflogs are usually enabled by default by the
core.logallrefupdates config option.

    -f, --force
Reset <branchname> to <startpoint> if <branchname> exists already.
Without -fgit branch refuses to change an existing branch.

    -m, --move
Move/rename a branch and the corresponding reflog.

    -M
Move/rename a branch even if the new branch name already exists.

    --color[=<when>]
Color branches to highlight current, local, and remote-tracking
branches. The value must be always (the default), never, or auto.

    --no-color
Turn off branch colors, even when the configuration file gives the
default to color output. Same as --color=never.

    --column[=<options>], --no-column
Display branch listing in columns. See configuration variable
column.branch for option syntax.--column and --no-column without
options are equivalent to always and never respectively.
This option is only applicable in non-verbose mode.

    -r, --remotes
List or delete (if used with -d) the remote-tracking branches.

    -a, --all
List both remote-tracking branches and local branches.

    --list
Activate the list mode.  git branch <pattern> would try to create a
branch, use git branch --list <pattern> to list matching branches.

    -v, -vv, --verbose
When in list mode, show sha1 and commit subject line for each head,
along with relationship to upstream branch (if any). If given
twice, print the name of the upstream branch, as well (see also git
remote show <remote>).

    -q, --quiet
Be more quiet when creating or deleting a branch, suppressing
non-error messages.

    --abbrev=<length>
Alter the sha1's minimum display length in the output listing. The
default value is 7 and can be overridden by the core.abbrev config
option.

    --no-abbrev
Display the full sha1s in the output listing rather than
abbreviating them.

    -t, --track
When creating a new branch, set up branch.<name>.remote and
branch.<name>.merge configuration entries to mark the start-point
branch as "upstream" from the new branch. This configuration will
tell git to show the relationship between the two branches in git
status and git branch -v. Furthermore, it directs git pull without
arguments to pull from the upstream when the new branch is checked
out.
This behavior is the default when the start point is a
remote-tracking branch. Set the branch.autosetupmerge configuration
variable to false if you want git checkout and git branch to always
behave as if --no-track were given. Set it to always if you want
this behavior when the start-point is either a local or
remote-tracking branch.

    --no-track
Do not set up "upstream" configuration, even if the
branch.autosetupmerge configuration variable is true.

    --set-upstream
If specified branch does not exist yet or if --force has been
given, acts exactly like --track. Otherwise sets up configuration
like --track would when creating the branch, except that where
branch points to is not changed.

    -u <upstream>, --set-upstream-to=<upstream>
Set up <branchname>'s tracking information so <upstream> is
considered <branchname>'s upstream branch. If no <branchname> is
specified, then it defaults to the current branch.

    --unset-upstream
Remove the upstream information for <branchname>. If no branch is
specified it defaults to the current branch.

    --edit-description
Open an editor and edit the text to explain what the branch is for,
to be used by various other commands (e.g.  request-pull).

    --contains [<commit>]
Only list branches which contain the specified commit (HEAD if not
specified). Implies --list.

    --merged [<commit>]
Only list branches whose tips are reachable from the specified
commit (HEAD if not specified). Implies --list.

    --no-merged [<commit>]
Only list branches whose tips are not reachable from the specified
commit (HEAD if not specified). Implies --list.

    <branchname>
The name of the branch to create or delete. The new branch name
must pass all checks defined by git-check-ref-format(1). Some of
these checks may restrict the characters allowed in a branch name.

    <start-point>
The new branch head will point to this commit. It may be given as a
branch name, a commit-id, or a tag. If this option is omitted, the
current HEAD will be used instead.

    <oldbranch>
The name of an existing branch to rename.

    <newbranch>
The new name for an existing branch. The same restrictions as for
<branchname> apply.

`$ git checkout <branch name>` - Checkout a branch or paths to the working tree

#### Synopsis:

    git checkout -q -f -m `<branch>`
    git checkout -q -f -m --detach `<branch>`
    git checkout -q -f -m --detach `<commit>`
    git checkout -q -f -m -b|-B|--orphan `<new_branch>` `<start_point>`
    git checkout -f|--ours|--theirs|-m|--conflict=`<style>` <tree-ish> -- `<paths>`...
    git checkout -p|--patch <tree-ish> -- `<paths>`...

git checkout `<branch>`

     To prepare for working on `<branch>`, switch to it by updating the
     index and the files in the working tree, and by pointing HEAD at
     the branch. Local modifications to the files in the working tree
     are kept, so that they can be committed to the `<branch>`.

     If `<branch>` is not found but there does exist a tracking branch in
     exactly one remote (call it `<remote>`) with a matching name, treat
     as equivalent to

$ git checkout -b `<branch>` --track `<remote>`/`<branch>`

     You could omit `<branch>`, in which case the command degenerates to
     "check out the current branch", which is a glorified no-op with a
     rather expensive side-effects to show only the tracking
     information, if exists, for the current branch.



#### Merging

`git-merge` - Join two or more development histories together

####useful comm:

    git-merge [--no]|--commit: perform merge and commit.
    git-merge --stat : show diffstat


# `git config` [options]

Config file location

    --global              use global config file
    --system              use system config file
    --local               use repository config file
    -f, --file <file>     use given config file
    --blob <blob-id>      read config from given blob object


     --get                 get value: name [value-regex]
     --get-all             get all values: key [value-regex]
     --get-regexp          get values for regexp: name-regex [value-regex]
     --get-urlmatch        get value specific for the URL: section[.var] URL
     --replace-all         replace all matching variables: name value [value_regex]
     --add                 add a new variable: name value
     --unset               remove a variable: name [value-regex]
     --unset-all           remove all matches: name [value-regex]
     --rename-section      rename section: old-name new-name
     --remove-section      remove a section: name
     -l, --list            list all
     -e, --edit            open an editor
     --get-color <slot>    find the color configured: [default]
     --get-colorbool <slot>
                   find the color setting: [stdout-is-tty]

 Type

     --bool                value is "true" or "false"
     --int                 value is decimal number
     --bool-or-int         value is --bool or --int
     --path                value is a path (file or directory name)

 Other

     -z, --null            terminate values with NUL byte
     --includes            respect include directives on lookup


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
