# Vagrant virual machine with clean centos-7

Your need install vagrant and virtualbox for up this configuration.

Your need install [vagrant](https://github.com/hashicorp/vagrant-installers/releases/tag/v2.3.4.dev%2Bmain "vagrant") and  [virtualbox](https://www.virtualbox.org/ "virtualbox") for up this configuration. Optional you can use [make](https://www.gnu.org/software/make/ "make").

### Step 1

Download box bento/centos-8.5 for virtualbox from [vagrantup](https://app.vagrantup.com/bento/boxes/centos-8.5 "vagrantup").

Download box devopsguys/Windows2012R2Eval for virtualbox from [vagrantup](https://app.vagrantup.com/gusztavvargadr/boxes/windows-server "vagrantup").

### Step 2

Clonr this repository: git clone https://github.com/codesshaman/vagrant_ldap_with_win.git

### Step 3

Copy box and go inside the repository folder:

``cp ~/Downloads/41bd180b-c435-464a-9100-c3b9220fb263 path_to/vagrant_ldap_with_win/centos``

``cp ~/Downloads/d4a33e01-bf8b-405b-a949-06d72f1f10f4 path_to/vagrant_ldap_with_win/windows``

``cd vagrant_ldap_with_win``

### Step 4

Inicialize configuration:

``vagrant box add bento/centos-7 debian``
``vagrant box add jborean93/WindowsServer2012R2 windows``

or with make:

``make build``

### Step 5

Install configuration:

``vagrant up --provider=virtualbox``

or with make:

``make``

### Step 6

WinRM transport may not set, you can install vbox guest addition in the ssl installation step and abort vagrant installing. All be work.

### Step 7

Connect to centos:

``ssh vagrant@192.168.58.202``

or with make:

``make connect``
