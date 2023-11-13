# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Конфигурация для Windows Server 2016
  config.vm.define "windows" do |windows|
    windows.vm.box = "gusztavvargadr/windows-server"
    windows.vm.communicator = "winrm"
    windows.vm.network "private_network", ip: "192.168.56.10"
    windows.vm.hostname = "windowsldap"
    
    # Дополнительные настройки для Windows Server 2016
    windows.vm.provider "vmware_desktop" do |vb|
      vb.name = "windowsldap"
      vb.memory = "4096"
      vb.gui = false
      vb.cpus = "4"
    end
  end

  # Конфигурация для CentOS Linux
  config.vm.define "centos" do |centos|
    centos.vm.box = "bento/centos-8.5"
    centos.vm.network "private_network", ip: "192.168.56.20"
    centos.vm.hostname = "centos-server"
    
    # Дополнительные настройки для CentOS Linux
    centos.vm.provider "vmware_desktop" do |vb|
      vb.name = "centos"
      vb.memory = "1024"
      vb.gui = false
      vb.cpus = "1"
    end
  end

end
