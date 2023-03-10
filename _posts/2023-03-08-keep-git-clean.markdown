---
layout: post
title:  "Keep your git history clean!"
date:   2023-03-08 10:58:00 +0100
categories: [vcs]
tags: [git]
---

_Set a few rules_

- Commit messages should be meaningful. `description` and `Add description column to Book table` are not the same.

- Don't commit secrets/credentials, libraries, automatically generated files/directories

_Nice to setup first_

- Protect branches
- Add pre-commit hooks

_Don't do this unless you're 100% sure_

- Delete untracked changes
    - `git clean`

- Ignore uncommitted changes and point to commit:
    - `git reset --hard COMMIT`

_It's okay to make mistakes_

- Wrong commit message?

    - `git commit --amend -m "New message :)"`

- Forgot to change something before committing?

    - change file
    - `git add`
    - `git commit --amend --no-edit`

- Merge conflicts?

    - Fix conflicts
    - `git add`
    - `git diff --check`
    - `git commit`

- Endless conflicts when rebasing?
    - `git rebase --abort`
    - `git merge-base master feature_branch`
    - `git rebase -i sha_from_previous_command`
    - `git rebase master`

- Committed to wrong branch?

    - `git checkout new_branch`
    - `git cherry_pick commit`
    - `git checkout wrong_branch`
    - `git reset --hard HEAD^` (Make sure to stash any untracked code before resetting)

- Reset branch to X old commits?

    - `git reset --hard HEAD~X`

- Undo an old commit?

    - `git revert old_commit`

- Committed a file you should've ignored?

    - `git rm --cached FILENAME`
    - `git commit --amend`

- Pushed a file you should've ignored?

    - `git reset --soft HEAD~1`
    - `git reset HEAD file_name`
    - `git commit`
    - `git push --force`

- Committed to master?

    - `git checkout master`
    - `git branch new_branch`
    - `git reset --hard HEAD~`
    - `git checkout new_branch`
