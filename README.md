# Git tuto

>This repo introduces my favorite Git commands. (It can be used also as a tutorial)

:bulb: I recommend to follow the [Atlassian tutorials](https://www.atlassian.com/git/tutorials/) for more detailed explanations.

### Informative operations

`git branch -vv`

Double verbose on branches will show you all branches with their last sha1-commit, comment
and if they are synchronized with a remote.

`git remote -v`

Verbose on remote will show you all remotes name and their URLS.

### Cleaning operations

`git checkout -f`

Will discard all changes from the HEAD.

`git clean -f`

Will remove all new files (not added by git) from the HEAD (be careful!).

`git rm --cached -r folder`

Will remove recursively files that keep being tracked in the repo after even though they have been added in .gitignore.

`git stash -u`

Will put in a temporary excluded zone all modified and new files (`git stash apply` to retrieve them).

`git push remote :remote_branch`

Will delete remote branch.

### Cancelling operations

`git commit --amend`

Let you modify last comment commit. If the commit was pushed you will have to force on next push (-f).

`git merge --abort`

Let you cancel a merge that can lead to automatically overwritten conflicts for instance.

`git reset --hard HEAD^`

Revert to previous commit

### Advanced workflow operations

`git rebase -i`

Often use with squash after in order to combine various commits into one. (Only work onto branches synchronized with a remote).

`git log master.. --oneline --decorate`

Let you see which commits from your working branch are not present on the master.

`git cherry-pick sha1-commit`

Let you apply just one commit of another branch instead of merging everything.

### Global config operations

`git config --global core.editor nano`

Will set nano (if you like it also) as default editor when git will prompt you to insert some text.

`git config --global pull.rebase true`

Will set rebase for pull operations by default

`git config --global alias.YOUR_ALIAS real command`

example:

`git config --global alias.s status`

Will set an alias (shortcut) for a git command of your choice.

`git config --global help.autocorrect 50`

This configuration will correct and execute a wrong typo command after 5 seconds (be careful!).

### Handy commands

`git checkout -`

Will switch to brevious branch

:bulb: Eventually I recommend to use [Smartgit](http://www.syntevo.com/smartgit) as GUI client for 3 reasons:

- It is free
- Compatible with linux, osx and windows
- A handy native conflict solver
