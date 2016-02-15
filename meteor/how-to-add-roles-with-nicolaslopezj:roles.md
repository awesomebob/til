# Add user roles with nicolaslopezj:roles

I had version 1.5.3 installed, and roles were defined in the roles collection.

To make an existing user an admin on the server, I had to run the following insert:

`db.roles.insert({"userId": "really-long-mongo-id-5A2BC", "roles": ["admin"]})`

In the new 2.0.0 version of the roles package, roles are defined in the user meta.

`db.users.update({"_id": "really-long-mongo-id-5a2bc"}, { $addToSet: { "roles": "admin" } })`
