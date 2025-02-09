# fail2ban Ansible role

This role is currently a work in progress.

## Example Playbook

```yaml
- name: Install/configure fail2ban
  hosts: all
  gather_facts: true
  become: true
  roles:
    - cmurphy.fail2ban
  vars:
    fail2ban_default_ban_time: 86400 # 1 day
    fail2ban_jails:
      - name: sshd
        enabled: true
      - name: nginx-botsearch
        enabled: true
        logpath:
          - /var/log/nginx/error.log

```