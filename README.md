ansible-role-repo-rpmfusion-nonfree
=========

Both should be in sync.
https://github.com/erwinboon/ansible-role-repo-rpmfusion-nonfree
https://gitlab.com/prutser/ansible-role-repo-rpmfusion-nonfree

Role is working but administration is not complete yet.

Requirements
------------

It is only tested on Centos 8

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

All variables are set in default and i made the assumption that you wish to have it at least installed but made it so that you can also delete it via the role.

rpmfusion_nonfree_repo_url: 
- url where packages can be downloaded
- shouldn't be changed

rpmfusion_nonfree_repo_gpg_key_url:
- set to the location of the repository key (locale filesystem when rpm is installed) 
- shouldn't be changed

rpmfusion_nonfree_repo_file: 
- repository file when package is installed
- shouldn't be changed, but if you "manually" add a/the repo file you can specify it here so it does not install it for you.

rpmfusion_nonfree_repo_disabled: 
- default true
- if you wish to keep the repository installed and available but not enabled
- should be changed to your needs

rpmfusion_nonfree_repo_remove:
- default true
- if you wish to remove the repository rpm ( yeah i know it does an install first, to be fixed later)
- should be changed to your needs

rpmfusion_nonfree_repo_name: 
- default something i made up like "RPMFusion-nonfree repository"
- shouldn't be changed

Dependencies
------------

The package is dependend on the rpmfusion free, so be sure to have it installed else you will be served with a nice ansible error message.

Example Playbook
----------------

Example below gives default configuration with installed and enabled rpmfusion nonfree repository

    - hosts: servers
      roles:
      - { role: ansible-role-repo-rpmfusion-nonfree, rpmfusion_nonfree_repo_remove: false, rpmfusion_nonfree_repo_disabled: false }

License
-------

yeah

Author Information
------------------

Prutser
