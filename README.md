## Cheat Sheet 

Whenever you're confused about git, come read this cheat sheet. Remember that all git commands can be run with the `--help` option. For example: 

`$ git branch --help` or `$git log --help`

### Essential Git Commands

####Create a new git repository
`$ git init` - Create a new, local repository

#### Repo Status
`$ git status` - Check the status of your current repository and see which files have changed.

`$ git diff` - __Fill Me Out__

#### Repo History
`$ git log` - __Fill Me Out__

`$ git log --oneline --decorate --color --graph --all` - __Fill Me Out__

`$ git log -p [filename]` __Fill Me Out__

#### Stage files to commit
`$ git add <filename>` - Add file contents to the index

`$ git add -A` - Tell the command to automatically stage files that have been modified and deleted, but new files you have not told Git about are not affected.

#### Commit changes in staged files
`$ git commit -m "<commit message>"` - Record changes to the repository
#### Branching
`$ git branch <branch name>` - __Fill Me Out__

`$ git branch` - __Fill Me Out__

`$ git checkout <branch name>` - __Fill Me Out__

#### Merging

`$ git merge <branch name>` - __Fill Me Out__