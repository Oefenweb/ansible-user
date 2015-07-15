## user

[![Build Status](https://travis-ci.org/Oefenweb/ansible-user.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-user) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-user-blue.svg)](https://galaxy.ansible.com/list#/roles/4391)

Manages user and group accounts.

#### Requirements

None

#### Variables

* `user_groups`: [default: `[]`]: Group declarations
* `user_groups.{n}.name`: [required]: The name of the group to manage
* `user_groups.{n}.gid`: [optional]: GID to set for the group
* `user_groups.{n}.system`: [default: `false`]: If `true`, indicates that the group created is a system group
* `user_groups.{n}.state`: [default: `present`]: Whether the group should be present or not on the remote host

* `user_users`: [default: `[]`]: User declarations
* `user_users.{n}.name`: [required]: The name of the user to manage
* `user_users.{n}.uid`: [optional]: UID to set for the user
* `user_users.{n}.comment`: [default: `''`]: Sets the description (aka `GECOS`) of user account
* `user_users.{n}.group`: [default: `name`]: Sets the user's primary group (takes a group name)
* `user_users.{n}.groups`: [default: `[]`]: Puts the user in this list of groups. When set to `[]`, the user is removed from all groups except the primary group
* `user_users.{n}.append`: [default: `false`]: If `true`, will only add groups, not set them to just the list in groups
* `user_users.{n}.password`: [default: `*`]: Sets the user's password to this crypted value
* `user_users.{n}.update_password`: [default: `always`]: `always` will update passwords if they differ. `on_create` will only set the password for newly created users
* `user_users.{n}.shell`: [default: `/bin/bash`]: Sets the user's shell
* `user_users.{n}.home`: [default: `/home/name` or `/name` for `root`]: Sets the user's home directory
* `user_users.{n}.system`: [default: `false`]: If `true`, indicates that the user created is a system user
* `user_users.{n}.state`: [default: `present`]: Whether the user should be present or not on the remote host
* `user_users.{n}.remove`: [default: `false`]: When used with `state=absent`, behavior is as with `userdel --remove`

## Dependencies

None

#### Example

```yaml
---
- hosts: all
  roles:
  - user
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-user/issues)!
