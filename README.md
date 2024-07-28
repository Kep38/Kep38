Установлен ансибл- sudo apt-add-repository ppa:ansible/ansible sudo apt update sudo apt install ansible

Настроены файл inventory

проверена комманда- ansible dbserver -m command -a uptime

проверил работу с хостами- ansible app -m ping

выполнил создание inventory.yml ansible all -m ping -i inventory.yml

проверка на серверах: ansible app -m command -a 'ruby -v' ansible app -m command -a 'bundler -v' или обе ansible app -m command -a 'ruby -v; bundler -v' - но это не работает(не работоспособно) ansible app -m shell -a 'ruby -v; bundler -v'(работает)

Проверка сервера db ansible db -m command -a 'systemctl status mongod' ansible db -m shell -a 'systemctl status mongod' ansible db -m systemd -a name=mongod или ansible db -m service -a name=mongod

Установка git ansible app -u ubuntu -b -K -m shell -a "sudo apt install -y git" Проверка: ansible app -m apt -a name=git

Клон репозитория в новую папку- ansible app -m git -a 'repo=https://github.com/express42/reddit.git dest=/home/ubuntu/reddit'

Создал ansible-playbook clone.yml

Clone hosts: app tasks:
Clone repo git: repo- https://github.com/express42/reddit.git dest: /home/appuser/reddit
Удален и заново внесен в репозиторий- ansible app -m command -a 'rm -rf ~/reddit' ansible-playbook clone.yml 
