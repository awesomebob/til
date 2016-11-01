With the default nginx configuration, `nginx.conf` sources the files found in the sites-enabled directory:

```
include /etc/nginx/sites-enabled/*;
```

Files are loaded in alphabetical order.
The file labeled `default` isn't magic,
it has no greater or lesser priority than any other file.

If you have the files:

```
sites-enabled/
  default
  dev-wildcard
```

The `default` one will take priority!
One possible solution for ordering your vhosts would be to prefix with digits:

```
sites-enabled/
  010-dev-wildcard
  020-other-dev-site
  ... etc ...
  default
```

