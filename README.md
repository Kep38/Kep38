<<<<<<< HEAD
Создан основной файл main.tf, определены провайдеры и модули для приложения и базы данных.
Добавлены переменные в variables.tf.

Настройка путей к модулям:

В файле main.tf для каждого окружения созданы пути к модулям  ./modules/app и ./modules/db

Выполнено развертывание ресурсов с помощью Terraform, проверены и созданы необходимые инстансы, результат работы отображен с указанием внешних IP-адресов созданных ресурсов.

Создание окружений Stage и Prod:

Созданы директории stage и prod в корневой папке проекта для раздельного управления окружениями.
Скопированы все необходимые файлы (main.tf, variables.tf, outputs.tf, terraform.tfvars, key.json) в каждую из директорий.
В файле main.tf для каждого окружения изменены пути к модулям на ../modules/app и ../modules/db.

=======
#HW4
testapp_IP = 51.250.86.183 
testapp_port = 9292
Для автоматического развертывания ВМ в облаке запускаем скрипт create-reddit.sh.

yc compute instance create \
  --name reddit-app \
  --hostname reddit-app \
  --memory=4 \
  --create-boot-disk image-folder-id=standard-images,image-family=ubuntu-1604-lts,size=10GB \
  --network-interface subnet-name=default-ru-central1-a,nat-ip-version=ipv4 \
  --metadata serial-port-enable=1 \
  --metadata-from-file user-data=/home/remi/.ssh/user-data.yaml

>>>>>>> packer-base
