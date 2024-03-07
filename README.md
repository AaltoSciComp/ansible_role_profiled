ansible_role_profiled
=====================

A small role that manages /etc/profile.d scripts.

Requirements
------------

None.

Role Variables
--------------

| Name                 | Explanation                                       |
|----------------------|---------------------------------------------------|
| `profiled_templates` | List of profile templates to add to /etc/profiled |

Each template should be written like this:

```yml
profiled_templates:
  - template: my_template.sh.j2
    owner: root
    group: root
    mode: 0555
```

Defaults for owner, group and mode are `root`, `root` and `555` respectively.

Example Playbook
----------------

```yml
- hosts: servers
  roles:
    - role: ansible_role_profiled
      vars:
        profiled_templates:
          - template: example_script.sh.j2
```

License
-------

MIT

Author Information
------------------

Simo Tuomisto, Aalto University 2024
