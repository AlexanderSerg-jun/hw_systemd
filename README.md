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
![image](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/50c5301b-011e-4581-a064-83ea04c2e49d)


# Содержимое скрипта
![Uploading image.png…]()


# Добавим права на запуск файла, используя команду chmod +x
 ![изображение](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/7efb5e77-666e-4b1d-af20-07d61af5731c)


# Создадим юнит для сервиса. Все юниты в системе Centos хрянятся в папке /etc/systemd/system
![изображение](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/cf39b45c-9b45-4f00-9965-c6cd1833c2f2)
# Сам юнит

![изображение](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/a98643cb-eb7f-42ac-9c36-41dd673a988b)
