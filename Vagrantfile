# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.synced_folder "./src", "/var/www/project"

  # Tăng thời gian timeout (mặc định 300 giây).
  # Thêm option để tránh lỗi boot chậm trên máy yếu hoặc mạng chậm.
  config.vm.boot_timeout = 900
  # Tắt auto update Guest Additions khi boot
  config.vbguest.auto_update = false
  # Không cho vbguest tải ISO từ Internet
  config.vbguest.no_remote = true
  
  config.vm.provision "shell", inline: <<-SHELL
    mkdir -p /var/www/project
  SHELL
end
