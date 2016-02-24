# How to set directory execute permissions

To read a file on a UNIX file system, you must have execute permissions on all it's ancestory directories.

Protip: You can use `chmod a+X -R` to set execute permissions on directories but not on files.
