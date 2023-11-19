# -*- mode: ruby -*-
# vi: set ft=ruby :

#Параметры указываются в цикле

Vagrant.configure("2") do |config|

  #Указываем, какую ОС мы будем использовать
  config.vm.box = "generic/centos8s"
  # Задаем hostname
  config.vm.hostname = "otus-ansible"
#  config.vm.network "public_network", ip: "192.168.2.11"
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  #Указываем настройки спецификации ВМ
  #Указывается в отдельном цикле
  config.vm.provider "virtualbox" do |vb|
     # Указываем количество ОЗУ и ядер процессора
     vb.memory = "1024"
     vb.cpus = "2"
  end
  config.vm.provision "ansible" do |ansible|
  ansible.playbook = "nginx-role.yml"
  ansible.become = "true"
  end
end
