What is new in Git 2.9

- Change the location of git hooks

        core.hooksPath

- git rebase -x

    execute a command on each commit (say, maybe a test suite?)

- diff highlighting

        git config --global diff.compactionHeuristic true
        git config --global interactive.diffFilter diff-highlight
        git config --global pager.log 'diff-highlight | less'
        git config --global pager.show 'diff-highlight | less'
        git config --global pager.diff 'diff-highlight | less'

- git commit --verbose

        git config −−global commit.verbose true
