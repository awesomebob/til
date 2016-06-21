# How to use xargs

`xargs -l` is a shortcut for `xargs -L 1`, limiting each command to 1 line of input.

`xargs -i` is a shortcut for `xargs -I {}`, which will replace each further instance of {} with the current line of input.

```
echo -e "1\n2\n3" | xargs -l -i echo {} foo
1 foo
2 foo
3 foo
```

```
cat alphabet.txt | xargs -l -i sh -c 'mkdir tmp/{};touch tmp/{}/{}.txt'
tmp/a/a.txt
tmp/b/b.txt
tmp/c/c.txt
...
```
