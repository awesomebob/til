# How to give access to a sudo command without password

Obligatory [XKCD](https://xkcd.com/149/)

The `/etc/sudoers` file can be a real pain to edit.
If you do it wrong, you can lock yourself out of ever being able to `sudo` again.

To do it right, you have you use the `visudo` command.
Obviously, you want to do it with `EDITOR=vi` in your ENV.

The last line in the default `/etc/sudoers` file looks suspiciously like a comment but is actually a directive:

```
#includedir /etc/sudoers.d
```

This will include any file in the `/etc/sudoers.d/` directory, so it is recommended you add new lines there.
Files in this directory must have chmod permissions set to 440.

For my purposes, I needed this line in a file in the `/etc/sudoers.d/` directory:

```
deploy ALL=(root) NOPASSWD: /etc/init.d/nginx reload, /usr/sbin/nginx -t
```

This gives the `deploy` user the permission to use `sudo nginx -t` without needing a password.
Note that the user still needs to actually type `sudo`.

