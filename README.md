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

## Установка Ansible на Centos9

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/fcb390092d48468490d85d98b508acc69ac6ad48/img/1.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/fcb390092d48468490d85d98b508acc69ac6ad48/img/2.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/fcb390092d48468490d85d98b508acc69ac6ad48/img/3.png" alt="Header">
</p>

Команда sudo yum install epel-release устанавливает репозиторий EPEL (Extra Packages for Enterprise Linux) на CentOS, RHEL или другие совместимые дистрибутивы. Команда sudo yum install ansible устанавливает Ansible на CentOS, RHEL или другие совместимые дистрибутивы, использующие пакетный менеджер yum. Команда ansible --version выводит информацию об установленной версии Ansible и его зависимостях

```bash
sudo yum install epel-release
sudo yum install ansible
ansible --version
```

## Настройка

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/85584da117e0d5a8206295c4a7f59accea823e8f/img/4.png" alt="Header">
</p>

Прежде чем запустить шаблон, нам нужно войти в настройки и внести несколько изменений. Настроим адаптер в режиме мостовой сети. Внутренняя машина получит ip-адрес и также сможет подключаться к интернету для загрузки и установки пакетов по мере необходимости

















