# How Vim Modelines work

If `set modeline=modeline` is set, vim will check `set modelines?` number of lines at the top and bottom of each file for a modeline.

For example: `set modelines=5` will check the top 5 and bottom 5 lines of each file for a modeline.

`help: modeline` for more info.
