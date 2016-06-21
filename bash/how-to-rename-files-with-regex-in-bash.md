Sources:
  1. http://stackoverflow.com/questions/1224766/how-do-i-rename-the-extension-for-a-batch-of-files
  2. man bash /Pattern substitution/

```bash
for file in *.log; do
  mv "${file}" "${file/%log/txt}"
done
```
