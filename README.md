# hw_systemd
# Написать сервис, который будет раз в 30 секунд мониторить лог на предмет наличия ключевого слова. Файл и слово должны задаваться в /etc/sysconfig
# Используя команду vi создадим файл watchlog в директории /etc/sysconfig/
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/b737a731-62a4-4c6c-867c-be9825c37d5d)

# Содержимое файла watchlog:
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/d4b8994d-6153-40d3-a412-0389409f3028)

# При помощи команды touch создадим файл /var/log/watch.log
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/959d1a00-fec4-4666-8176-446300600f56)

# Внесем в него любые строки и ключевое слово "ALERT"
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/98f0368e-4ebb-492f-b60b-3729c78f82f8)

# Пишем скрипт watchlog.sh в директории /opt
![Screenshot from 2023-06-19 11-27-40](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/9354865b-c64b-475a-812a-cc5f981bd944)



# Содержимое скрипта
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/50c5301b-011e-4581-a064-83ea04c2e49d)


# Добавим права на запуск файла, используя команду chmod +x
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/01171f93-bf5e-4bf7-848f-6ada3d16420c)

# Создадим юнит для сервиса. Все юниты в системе Centos хрянятся в папке /etc/systemd/system
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/3a30dda6-c79e-4746-bec6-9f285b35e0ce)

# Сам юнит

![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/b4a78697-7369-4e86-b33d-b8c83e0ae6e6)

# Create unit for time
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/af31fdc3-5dfe-430b-97d2-c9aa7ba679ba)

# Code 
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/245b855a-bca3-40b2-aeff-79fe0fe93ea9)
# Start timer systemctl start watchlog.timer. Ande check result  tail -f /var/log/messages
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/c8a98edc-4150-4fab-9a11-4863a8517340)

# 2.Из epel установитþ spawn-fcgi и переписатþ init-скрипт на unit-файл. Имсервиса должно также назýватþсā.

![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/72f776df-12ea-4d9b-92b9-3830d5437a98)

# edit file 
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/62284945-c8d1-42a2-83d7-324b5fced886)
# uncomment string
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/73ebb9fa-f16d-440b-b813-996f8cf16ad2)
# create unit vi /etc/systemd/system/spawn-fcgi.service
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/21c79d21-26a8-4bc4-b3ba-e58b0f39e385)

# check it systemctl start spawn-fcgi systemctl status spawn-fcgi
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/e89bcc72-fa95-44f1-b697-6924add7b1c7)

# Дополнить Юнит-файл apache httpd возможностью запустить несколько инстансов сервера с разными конфигами


# Для запуска нескольких экземпляров сервиса будем использовать шаблон в конфигурации файла окружения (/usr/lib/systemd/system/httpd.service ) добавивь параметр %I
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/adb8d1fc-710f-4242-9725-a48d561f739d)
# Создаем двай файла окружения 
 ![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/9fecb72c-879a-4d4e-9b69-2f03f9d0bedd)
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/916c0008-3957-4871-b724-0501c5c5794c)

# Создаем два конфига
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/ee14661a-8192-4b3a-8791-7d0157f24813)

# Изменим настройка конфига second.conf
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/1c2b1288-7c8b-47f3-94f4-56be6345ab3a)
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/93e0ffd1-58d6-43c8-89c5-de815f50422f)

# Запустим два экземпляра # Проверим используя команду  ss -tulnp | grep httpd
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/a80647be-aee2-45e3-97a8-daba96cd5887)


