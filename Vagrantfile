# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

if Vagrant.has_plugin? "vagrant-vbguest"
config.vbguest.no_install = true
config.vbguest.auto_update = false
config.vbguest.no_remote = true
end

config.vm.define :clienteFw do |clienteFw|
clienteFw.vm.box = "centos/stream8"
clienteFw.vm.network :private_network, ip: "209.191.10.20"
clienteFw.vm.hostname = "clienteFw"
end

config.vm.define :firewall do |firewall|
firewall.vm.box = "centos/stream8"
firewall.vm.network :private_network, ip: "209.191.10.30"
firewall.vm.network :private_network, ip: "192.168.10.30"
firewall.vm.network :forwarded_port, guest: 80, host:4577
firewall.vm.network :forwarded_port, guest: 443, host:4578
firewall.vm.hostname = "firewall"
end

config.vm.define :servidorFTPseguro do |servidorFTPseguro|
servidorFTPseguro.vm.box = "centos/stream8"
servidorFTPseguro.vm.network :private_network, ip: "192.168.10.40"
servidorFTPseguro.vm.network :forwarded_port, guest: 80, host:4567
servidorFTPseguro.vm.network :forwarded_port, guest: 443, host:4568
servidorFTPseguro.vm.hostname = "servidorFTPseguro"
end

end
