# Cisco Backup
Set of Ansible playbooks for CIsco configs backup. Backups are stored in the git repository (**network_backup_repository** variable in the playbooks)

The ansible-network-backup role has some default vars that must be reinitialized in some reasons:
- **network_backup_file** - file name of the stored config 
- **multicontext: false** - must be true only when interact with multicontext devices

Also the group_vars/all.yml **ansible_network_os: asa** variable must be reinitialized in playbook in the case of interact with non asa devices (switches with ios for example)
