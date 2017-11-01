# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.vm.box = "centos7test"
  config.vm.hostname = "happy"
  config.vm.network :private_network, ip: "192.168.0.42"
  config.ssh.username = "oa"
  config.ssh.private_key_path = "./keys/oa.priv"

  # centos not initiating private network 
  # https://stackoverflow.com/questions/32518591/centos7-with-private-network-lost-fixed-ip
  config.vm.provision "shell",
    inline: "sudo nmcli connection reload && sudo systemctl restart network.service"

  # config.vm.provision "ansible" do |ansible|
	 #  ansible.playbook = "provision.yml"
  # end
end
