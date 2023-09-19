Vagrant.configure("2") do |config|
  config.vm.define "windows" do |windows|
    windows.vm.box = "devopsguys/Windows2012R2Eval"
    windows.vm.hostname = "windowsldap"
    windows.vm.network "private_network", ip: "192.168.58.201"
    windows.vm.synced_folder "./shared", "/shared", type: "virtualbox"
    windows.vm.communicator = "winrm"
    windows.winrm.transport = :ssl
    windows.winrm.ssl_peer_fingerprint = "ac:bd:ef:01:23:45:67:89:ab:cd:ef:01:23:45:67:89:ab:cd:ef"
    windows.winrm.ssl_ca_cert = "certs/ca_cert.pem"
    windows.winrm.ssl_cert = "certs/client_cert.pem"
    windows.winrm.ssl_key = "certs/client_key.pem"
    windows.winrm.ssl_peer_verification = false
    windows.vm.provider "virtualbox" do |v|
      v.name = "windowsldap"
      v.memory = 2048
      v.cpus = 2
  end
end
  config.vm.define "centos" do |centos|
    centos.vm.box = "bento/centos-7"
    centos.vm.hostname = "centosldap"
    centos.vm.network "private_network", ip: "192.168.58.202"
    centos.vm.synced_folder "./shared", "/shared", type: "virtualbox"
    id_rsa_pub = File.read("#{Dir.home}/.ssh/id_rsa.pub")
    centos.vm.provision "copy ssh public key", type: "shell",
    inline: "echo \"#{id_rsa_pub}\" >> /home/vagrant/.ssh/authorized_keys"
    centos.vm.provider "virtualbox" do |v|
      v.name = "centosldap"
      v.memory = 1024
      v.cpus = 1
    end
  end
end
