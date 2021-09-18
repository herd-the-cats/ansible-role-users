Users
=========

This is a basic role to create both system and regular users and groups, including self-named groups for users with a matching gid to the uid.

Requirements
------------

- Python passlib for generating password_hash
- Ansible 2.9+

Role Variables
--------------

- users\_groups_w_gids - _groups besides self-named groups to create with specific gids._
- users\_accounts - _user information as passed to the user module. Additionally, auth\_keys to add ssh public keys to user accounts._
- users\_set\_rootpw - _Boolean. Requires users\_rootpw to be set._
- users\_rootpw - _Vaulted variable with root password. Note: the /etc/shadow value will be rehashed if the inventory\_hostname changes._

License
-------

BSD

Author Information
------------------

herd-the-cats
