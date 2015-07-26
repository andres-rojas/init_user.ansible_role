init_user
=========

This role sets up a user that matches the ansible_ssh_user.

Role Variables
--------------

```yaml
init_user_admin:        root               # The user to login as to set up the user
init_user_name:         fooser             # The name of the initial user
init_user_groups:       []                 # A list of groups to add the user to
init_user_shell:        /bin/sh            # Set the user's shell
init_user_auth_key:     ~/.ssh/id_rsa.pub  # Path to the public key to add to authorized_keys
init_user_root_has_key: false              # Use the public key already set in /root/.ssh/authorized_keys
```

Example Playbook
----------------

```yaml
- hosts: vagrant
  roles:
    - init_user
  vars:
    int_user_admin: vagrant
    init_user_groups:
      - ansible
      - wheel
    init_user_shell: /bin/bash
    init_user_root_has_key: true
```

License
-------

Licensed under the MIT License. See the LICENSE file for details.

Author Information
------------------

- http://conpat.io
- andres@conpat.io
