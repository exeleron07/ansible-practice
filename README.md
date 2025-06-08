# Ansible-practise на CentOs

В этом проекте демонстрируется работа с Ansible
---

## Основные команды в работе с Ansible

- `sudo yum install epel-release` — 123
- `sudo yum install ansible` - 123
- `ansible --version` - 123
- `sudo vi /etc/hostname` - 123
- `sudo vi /etc/hosts` - 123
- `ssh your_ip` - 123
- `cat > inventory` `target1 ansible_host=your_ip ansible_ssh_pass=your_pass` - 123 - 123
- `ansible target1 -m ping -i inventory` - 123
- `ansible target2 -m ping -i inventory --ssh-extra-args="-o StrictHostKeyChecking=no"` - 123
---
