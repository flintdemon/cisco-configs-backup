Original role here: https://developer.cisco.com/codeexchange/github/repo/ciscops/ansible-network-backup
* This role was extended for multicontext asa support

# Ansible Network Backup

This role backs up the configuration of a network device into a git repository.

The file is backed up to the directory specified in `network_backup_dir`.  A git repo is used when
`network_backup_repository` is specified.


## Requirements


Currently supports:
* Cisco IOS XE
* Cisco NX OS
* Cisco ASA

## Role Variables


* `network_backup_repository`: The git repository that will be use to store the backups
  * _Backups will not be pushed to git when `network_backup_repository` is not specified_
* `network_backup_dir`: The directory where the backups will be placed. Default: `"{{ playbook_dir }}/backups"`
  * _`network_backup_dir` will be created when it does not exist_
* `git_name`: Set the user's git name when not otherwise specified
* `git_email`: Set the user's git email when not otherwise specified

## Dependencies

None


## Example Playbook


```yaml
- hosts: network
  gather_facts: no
  connection: network_cli
  tasks:
    - include_role:
        name: network-backup
      vars:
        network_backup_repository: 'git@m42-vs1-ansbl-e01.scada.cpc.scd:root/cisco-backups.git'
```

## License


[CISCO SAMPLE CODE LICENSE](./LICENSE).
