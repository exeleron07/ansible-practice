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

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/9d191e7f2f6fe373b2686e656b39a1495e1f276e/img/5.png" alt="Header">
</p>

Войду в линукс, посмотрю ip-адрес через команду ip addr и подключусь через SSH в MobaXterm

```bash
ip addr
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/9d191e7f2f6fe373b2686e656b39a1495e1f276e/img/6.png" alt="Header">
</p>

Далее покажу подключение в MobaXterm, чтобы в виртуалке создать наши клоны. Команда 'su - root' отвечает за подключение к рут правам, команда 'shutdown now' перезапускает систему

```bash
su - root
shutdown now
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/9d191e7f2f6fe373b2686e656b39a1495e1f276e/img/7.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/da03bab488523f6cf2f76be1be1ce9c95fca2558/img/8.png" alt="Header">
</p>

Клонируем Centos и выбираем опцию, что нужно сгенерировать новые MAC-адреса всех сетевых адаптеров, потому что нам потребуются уникальные маки для всех наших виртуальных машин. Также выбираем связанный клон в опции, чтобы сэкономить место

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/58d2752cee3f004a2cfc14a934542515f971fef6/img/9.png" alt="Header">
</p>

Теперь подключаемся к этим машинам по очереди через команду 'ssh your_ip'

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/58d2752cee3f004a2cfc14a934542515f971fef6/img/10.png" alt="Header">
</p>

Подключение прошло успешно 

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/58d2752cee3f004a2cfc14a934542515f971fef6/img/11.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/58d2752cee3f004a2cfc14a934542515f971fef6/img/12.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/58d2752cee3f004a2cfc14a934542515f971fef6/img/13.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/58d2752cee3f004a2cfc14a934542515f971fef6/img/14.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/58d2752cee3f004a2cfc14a934542515f971fef6/img/15.png" alt="Header">
</p>

Теперь поменяем хосты названий, чтобы было более понятнее при работе. Вводим команду, после чего меняем на нужное название и выходим из редактора, сохраняем (esc + :wq)

```bash
sudo vi /etc/hostname
sudo vi /etc/hosts
```
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/0ea35bedf61921d11a81934734ed59f0b0b909e0/img/16.png" alt="Header">
</p>

Перезапускаем машину и делаем всё также в точности с другой машиной 

```bash
shutdown -r now
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/0ea35bedf61921d11a81934734ed59f0b0b909e0/img/17.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/0ea35bedf61921d11a81934734ed59f0b0b909e0/img/18.png" alt="Header">
</p>

Хосты успешно поменяли

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/0ea35bedf61921d11a81934734ed59f0b0b909e0/img/19.png" alt="Header">
</p>

Проверяю, что ansible стоит на моих машинах

```bash
ansible --version
```
## Тестируем связь с Ansible 

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e1e2c2ac5bd5247870bade31c5a216aed8ed923e/img/20.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e1e2c2ac5bd5247870bade31c5a216aed8ed923e/img/21.png" alt="Header">
</p>

Смотрим какой ip-адрес у второй машины, после чего от первой подключаемся ко второй

```bash
ssh your_ip
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e1e2c2ac5bd5247870bade31c5a216aed8ed923e/img/22.png" alt="Header">
</p>

Можем закрыть и прервать связь

```bash
exit
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/d6620b394dfc928a350e0384ef057be04593a811/img/23.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/d6620b394dfc928a350e0384ef057be04593a811/img/24.png" alt="Header">
</p>

Чтобы проверить возможность подключения через Ansible, создадим тестовый проект. Создаем папку, переходим в неё и создаем inventory файл. В этом файле будет одна запись для целевого хоста

```bash
mkdir project
cd project/
cat > inventory
target1 ansible_host=192.168.0.105 ansible_ssh_pass=your_pass
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e76cb953c6b11453dc0c88bab46ec1e176a6f094/img/25.png" alt="Header">
</p>

Команда 'ansible target1 -m ping -i inventory' проверяет доступность целевого хоста (target1) через Ansible, используя модуль ping и inventory-файл. Есть inventory файл с псевдонимом моего целевого сервера, его ip-адресом и паролем и это означает, что мы можем запустить проверку, выполнив команду:

```bash
ansible target1 -m ping -i inventory
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e76cb953c6b11453dc0c88bab46ec1e176a6f094/img/26.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e76cb953c6b11453dc0c88bab46ec1e176a6f094/img/27.png" alt="Header">
</p>
<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e76cb953c6b11453dc0c88bab46ec1e176a6f094/img/28.png" alt="Header">
</p>

Когда мы нажали энтер, ansible выполнил ping-тест и мы убедились может ли ansible установить успешное соединение с нашей целевой машиной. В этом случае он говорит об успехе и возвращает сообщение о понге.
Создадим ещё один клон: ansible-target 2, войдем туда и посмотрим ip-адрес

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e76cb953c6b11453dc0c88bab46ec1e176a6f094/img/29.png" alt="Header">
</p>

Теперь отредактируем файл inventory файл и добавим информацию об target2

```bash
ansible_ssh_pass=your_pass
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e76cb953c6b11453dc0c88bab46ec1e176a6f094/img/30.png" alt="Header">
</p>

Как мы можем заметить тест для target 1 прошёл успешно, а для target 2 нет

```bash
ansible target1 -m ping -i inventory
ansible target2 -m ping -i inventory
```

<p align="center">
  <img src="https://github.com/exeleron07/ansible-practice/blob/e76cb953c6b11453dc0c88bab46ec1e176a6f094/img/31.png" alt="Header">
</p>

Исправляем данную ситуацию (отключаем проверку ключа хоста). Если добавление вручную неудобно, временно отключите проверку ключей, добавив следующие настройки в команду Ansible:

```bash
ansible target2 -m ping -i inventory --ssh-extra-args="-o StrictHostKeyChecking=no
```









