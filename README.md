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










