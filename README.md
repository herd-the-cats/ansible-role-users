Users
=========

This is a basic role to create both system and regular users and groups, including self-named groups for users with a matching gid to the uid.

Requirements
------------

- Python passlib for generating password_hash
- Ansible 2.9+

Role Variables
--------------

users_groups - _groups besides self-named groups to create. Any groups listed in the users_accounts var need to exist here too._
users_accounts - _user information as passed to the user module. Additionally, auth_keys to add ssh public keys to user accounts and extra booleans to intergrate with other roles such as herd-the-cats.dotfiles and herd-the-cats.cinnamon. Note: the password value will be rehashed each run._
users_set_rootpw - _Boolean. Requires users_rootpw to be set. Set to false if looping this role._
users_rootpw - _Vaulted variable with root password. Note: the password value will be rehashed each run._


Dependencies
------------

Booleans in users_accounts indicate whether to execute other herd-the-cats roles. These individual user values are accessed via varnames lookup, prepending "user_" and the user's name to the role variable to create user-specific settings that override the default, group, or host variables. E.g. "user_johndoe_dotf_git_repo".

License
-------

BSD

Author Information
------------------

herd-the-cats
