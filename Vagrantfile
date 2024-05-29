# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
  #class2 server 
  config.vm.define "class2server" do |class2server|
  class2server.vm.box = 'almalinux/8'
  class2server.vm.hostname = 'class2server.example.com'
  class2server.vm.network "private_network", ip: '192.168.28.5'
 
config.vm.provider "virtualbox" do |v|
  v.memory = 8192
  v.cpus = 2
end


  class2server.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;"

  end

  #class2 client 
  config.vm.define "class2client" do |class2client|
  class2client.vm.box = 'almalinux/8'
  class2client.vm.hostname = 'class2client.example.com'
  class2client.vm.network "private_network", ip: '192.168.28.7'
  
  class2client.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;"

  end
end
