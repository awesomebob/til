# Update a user's password from `meteor shell`

Tested with Meteor version 1.0.5

1. `meteor shell`
2. `Meteor.users.find().fetch()`
3. `Accounts.setPassword('[user id found with previous command]', '[newpassword]', { logout: true })`
