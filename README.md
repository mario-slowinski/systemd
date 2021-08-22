systemd
=======

Configure systemd unit.

Requirements
------------

* [ansible.builtin](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)

Role Variables
--------------

* defaults

  ```yaml
  systemd_units:            # list of systemd units to configure
    - name: ""              # systemd unit name
      type: ""              # systemd unit type

      config_unit:          # options for [Unit] section
        Description: ""
        Documentation: []   # list => space separated value
        After: []
        ConditionPathIsDirectory: ""

      config_service:       # options for [Service] section
        ExecStart: ""
        KillMode: process
        WorkingDirectory: ""

      config_install: {}    # options for [Install] section
  ```

* vars

  ```yaml
  systemd_config: {}        # systemd unit config file attributes
  ```

Dependencies
------------

*No* *dependencies*

Tags
----

* systemd.config

Example Playbook
----------------

* `requirements.yml`

  ```yaml
  - name: systemd
    src: https://github.com/mario-slowinski/systemd
  ```

* playbook usage

  ```yaml
  - hosts: servers
    gather_facts: yes  # to determine network interface
    roles:
      - role: systemd
  ```

License
-------

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)

Author Information
------------------

[mario.slowinski@gmail.com](mailto:mario.slowinski@gmail.com)
