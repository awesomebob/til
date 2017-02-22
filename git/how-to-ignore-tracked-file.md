# How to ignore a tracked file

    git update-index --skip-worktree config.php

And to undo:

    git update-index --no-skip-worktree config.php

If you've forgotten which files you've skipped, you can do:

    git ls-files -v

