ansible-users
=============

The hawt new way to easily manage users in ansible

The goals of the project are:
- Have one central file where we store the users's info
- Be able to include a user with one line

All the heavy lifting is done by users-common. All you have to do is add the
user's deets to userc-common/vars/main.yml and then include the user
 (and optionally the group) in your dependencies like so:

```
---
dependencies:
  - { role: users-common, group: "others", user: "rick" }
```

You can also group these dependencies into a separate role (see other-users)