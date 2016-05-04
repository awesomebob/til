# How git stores objects

Objects are hashed with SHA1. The first 2 characters are used as a directory name, the remaining 38 characters as a file name.

This is mostly to avoid having too many files in a single directory.

Directories become tree objects, with the file contents pointing to child trees or blobs with filenames.
Blobs contain file contents.

Commits point to a tree and probably to a parent commit.

You can pretty-print a git object with the command `git cat-file -p {object}`, where an object can be a git hash or an alias to a git hash, such as a branch name.

For bonus points: you can print the tree pointed to by a branch alias, such as `git cat-file -p master^{tree}`.

If you want to print the tree of the commit before the current head, the syntax is `git cat-file -p HEAD^^{tree}`.

