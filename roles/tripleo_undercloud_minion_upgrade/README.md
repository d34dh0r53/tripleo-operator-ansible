tripleo_undercloud_minion_upgrade
=================================

A role to run the upgrade of a TripleO undercloud minion.

Requirements
------------

None.

Role Variables
--------------

* `tripleo_undercloud_minion_upgrade_debug`: (Boolean) Flag used to enable the debug version of commands. Default: false
* `tripleo_undercloud_minion_upgrade_dry_run`: (Boolean) Flag to add --dry-run to the upgrade command. Default: false
* `tripleo_undercloud_minion_upgrade_force_stack_update`: (Boolean) Flag to add --force-stack-update to the upgrade command. Default: false
* `tripleo_undercloud_minion_upgrade_home_dir`: (String) Home directory for the undercloud user. Default: "{{ ansible_env.HOME }}"
* `tripleo_undercloud_minion_upgrade_inflight_validations`: (Boolean) Flag to add --inflight-validations to the upgrade. Default: false
* `tripleo_undercloud_minion_upgrade_log_combine`: (Boolean) Flag to combine stdout and stderr in the logfile. Default: true
* `tripleo_undercloud_minion_upgrade_log_output`: (Boolean) Flag to log the output to a file rather than show it in the ansible output. Default: true
* `tripleo_undercloud_minion_upgrade_no_validations`: (Boolean) Flag to add --no-validations to the upgrade. Default: false
* `tripleo_undercloud_minion_upgrade_timeout`: (Number) Timeout for the upgrade command. Default: 7200
* `tripleo_undercloud_minion_upgrade_yes`: (Boolean) Flag to add --yes to the upgrade. Default: false
* `tripleo_undercloud_minion_upgrade_log`: (String) Upgrade log file path. Default: "{{ tripleo_undercloud_minion_upgrade_home_dir }}/undercloud_minion_upgrade.log"

Output Variables
----------------

* `tripleo_undercloud_minion_upgrade_result`: Ansible shell execution results

Dependencies
------------

None.

Example Playbook
----------------

Example upgrade execution playbook

```yaml
- hosts: undercloud
  gather_facts: true
  tasks:
    - name: Upgrade undercloud minion
      import_role:
        name: tripleo_undercloud_minion_upgrade
      vars:
        tripleo_undercloud_minion_upgrade_debug: true
```

License
-------

Apache-2.0