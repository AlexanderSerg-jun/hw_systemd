# hw_systemd
# Написать сервис, который будет раз в 30 секунд мониторить лог на предмет наличия ключевого слова. Файл и слово должны задаваться в /etc/sysconfig
# Используя команду vi создадим файл watchlog в директории /etc/sysconfig/
![1684764087847](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/653a35fc-5e44-4ab6-9959-ad762f4471bd)
# Содержимое файла watchlog:
![1684764125733](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/fc2f95c5-aba6-4dc5-be94-7c7696793f8b)
# При помощи команды touch создадим файл /var/log/watch.log
![1684764147596](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/c3a4e28d-ef7a-4c1f-848c-691b0e2a1f44)
# Внесем в него любые строки и ключевое слово "ALERT"
![1684764332915](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/ecc68afb-74e1-417d-a4ce-57cb28cf9fe7)
* Пишем скрипт watchlog.sh в директории /opt


******
![1684764986621](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/55c6fe06-b0b3-4f8d-956b-cc12be1f7448)
# Содержимое скрипта
![1684764968095](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/23ea5ecb-8352-4176-b79c-526ed806ab5d)

# Добавим права на запуск файла, используя команду chmod +x
 ![изображение](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/7efb5e77-666e-4b1d-af20-07d61af5731c)


# Создадим юнит для сервиса. Все юниты в системе Centos хрянятся в папке /etc/systemd/system
![изображение](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/cf39b45c-9b45-4f00-9965-c6cd1833c2f2)
# Сам юнит

![изображение](https://github.com/AlexanderSerg-jun/hw_systemd/assets/85576634/a98643cb-eb7f-42ac-9c36-41dd673a988b)
