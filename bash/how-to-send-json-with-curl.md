# Need to send JSON with curl in a bash script?

Don't bother trying to get everything escaped correctly.
Just put the JSON in an external file and include it with `@filename`:

```bash
#!/bin/bash
curl example.com \
  -H "Content-Type:application/json" \
  -d @payload.json \
  -v
```
