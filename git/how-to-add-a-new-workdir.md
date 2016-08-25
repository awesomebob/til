# How to add a new git workdir

There used to be a script called `git-new-workdir`, but it has been superceded by the new `git worktree` command.

From any git repo:

```
git worktree add /path/to/new/directory/ [branch]
```

This will create a 'linked' workdir in a new branch named after the new directory.

