Users
=========

This is a basic role to create both system and regular users and groups, including self-named groups for users with a matching gid to the uid.

Requirements
------------

- Python passlib for generating password_hash
- Ansible 2.9+

Role Variables
--------------

- users\_groups - _groups besides self-named groups to create. Any groups listed in the users\_accounts var need to exist here too._
- users\_accounts - _user information as passed to the user module. Additionally, auth\_keys to add ssh public keys to user accounts and extra booleans to intergrate with other roles such as herd-the-cats.dotfiles and herd-the-cats.cinnamon. Note: the password value will be rehashed each run._
- users\_set\_rootpw - _Boolean. Requires users\_rootpw to be set. Set to false if looping this role._
- users\_rootpw - _Vaulted variable with root password. Note: the password value will be rehashed each run._


Dependencies
------------

Booleans in users\_accounts indicate whether to execute other herd-the-cats roles. These individual user values are accessed via varnames lookup, prepending "user\_" and the user's name to the role variable to create user-specific settings that override the default, group, or host variables. E.g. "user\_johndoe\_dotf\_git\_repo".

License
-------

BSD

Author Information
------------------

herd-the-cats
