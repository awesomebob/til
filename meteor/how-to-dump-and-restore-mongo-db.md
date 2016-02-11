# Dump and restore Mongo database

- Tested dump with MongoDB --version 3.0.1
- Tested restore with MongoDB --version 2.6.3
- Nothing seemed to break

1. `ssh [servername] mongodump`
2. `rsync -rsv [servername]:~/dump/ ./`
3. `mongorestore --port 3001 path/to/dump/dir`
    - Meteor runs on port 3000 by default
    - Meteor's Mongo instance runs on port 3001 by default
