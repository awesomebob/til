Run an interactive shell:

`bash -i` will run an interactive shell, meaning that it loads .bash_profile and .bash_aliases, etc.

`bash -c` will run the following command.

```
find -name \*bar\* | xargs bash -ic vo foo
```
