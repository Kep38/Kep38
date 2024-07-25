Создан основной файл main.tf, определены провайдеры и модули для приложения и базы данных.
Добавлены переменные в variables.tf.

Настройка путей к модулям:

В файле main.tf для каждого окружения созданы пути к модулям  ./modules/app и ./modules/db

Выполнено развертывание ресурсов с помощью Terraform, проверены и созданы необходимые инстансы, результат работы отображен с указанием внешних IP-адресов созданных ресурсов.

Создание окружений Stage и Prod:

Созданы директории stage и prod в корневой папке проекта для раздельного управления окружениями.
Скопированы все необходимые файлы (main.tf, variables.tf, outputs.tf, terraform.tfvars, key.json) в каждую из директорий.
В файле main.tf для каждого окружения изменены пути к модулям на ../modules/app и ../modules/db.

