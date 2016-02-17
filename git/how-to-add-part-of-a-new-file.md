# How to add part of a new file to git

`git add -i [filename]` is a great tool, but it is not immediately obvious how to use it with a new file.

[StackOverflow][] had the answer: use `git add -N [filename]` first.

[StackOverflow]: http://stackoverflow.com/a/6440500

Here's what `git add --help` has to say about -N

>  -N, --intent-to-add
>       Record only the fact that the path will be added later. An entry for the path is placed in the index with
>       no content. This is useful for, among other things, showing the unstaged content of such files with git
>       diff and committing them with git commit -a.

