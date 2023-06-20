Vagrant.configure("2") do |config|

    config.vm.box = "centos/7"   # выбираем базовый образ
    config.vm.provision "file", source: "../etc/systemd/system/spawn-fcgi.service", destination: "/etc/systemd/system/spawn-fcgi.service"
  
    config.vm.provision "shell", inline: <<-SHELL
      # Обновляем список пакетов и устанавливаем EPEL-репозиторий
      yum -y update
      yum -y install epel-release
  
      # Устанавливаем spawn-fcgi
      yum -y install spawn-fcgi
  
      # Удаляем init-скрипт spawn-fcgi
      rm -f /etc/init.d/spawn-fcgi
  
      # Активируем сервис spawn-fcgi
      systemctl enable spawn-fcgi.service
      systemctl start spawn-fcgi.service
  
    SHELL
  
  end
  