# User an group management role
A simple Ansible role to manipulate users and groups

## Role configuration

* default_groups: (empty list by default) - the default groups for the user if none is specified.
* default_shell: (default BASH) - the default shell if none is specified.
* create_home: (yes|no) - create home if it is not specified.
* remove_home: (yes|no) - by default remove user home directory if remove action is needed.

## Adding new user(s)

Add a **users_to_add** variable containing the list of users to add.
A good place to put this is in *group_vars/groupname.yml* if you only want the users to be on certain machines.

The following attributes are required for each user:

* name: the user's username.
* comment: The full name of the user (gecos field).
* uid: *optional* - The numeric user id for the user.
* groups: *optional* - a list of supplementary groups for the user.
* shell: *optional* - the user's shell. By defaults /bin/bash
* ssh-key - This should be a list of ssh keys for the user..

## Removing user(s)
Add a **users_to_del** variable containing the list of users to remove.

* name (required)
* remove_home: optional - by default 'yes'

## Creating new group(s)
Add a **group_to_add** variable containing the list of groups to add.

* name: group's name
* gid: optional - group id number
* system: optional (yes|no) system group

## Removing group(s)

Add a **group_to_del** variable containing the list of groups to remove.

*Example:*

```yml
users_to_add:
 - name: user
   comment: "Juan Perez"
   shell: /bin/bash
   uid: 1012
   groups: 
     - sudo
     - admin
     - test
   pub_keys:
     - ssh-rsa AAAAB ... BjFdOuzUXjX user@localhost
     - ssh-rsa AAAAB ... SjdsklXifgX user@localhost2

users_to_del:
 - name: user2
   remove_home: no

groups_to_add:
 - name: test
   system: yes

groups_to_del:
 - test2

```
