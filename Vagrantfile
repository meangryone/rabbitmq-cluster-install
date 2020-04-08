# -*- mode: ruby -*-
# vi: set ft=ruby :

nodes = {
 "rabbit-node1"      => ["hashicorp/bionic64", 4, 2048, 120, "00:50:56:11:11:47"],
 "rabbit-node2"      => ["hashicorp/bionic64", 4, 2048, 120, "00:50:56:11:11:48"],
 "rabbit-node3"      => ["hashicorp/bionic64", 4, 2048, 120, "00:50:56:11:11:49"], 
}

Vagrant.configure("2") do |config|
 nodes.each do | (name, cfg) | box, numvcpus, memory, storage, mac = cfg
  
  config.vm.define name do |machine|
   machine.vm.box = box
   machine.vm.hostname = name
   machine.vm.synced_folder('.', '/vagrant', type: 'rsync')
  
   machine.vm.provider :vmware_esxi do |esxi|
    esxi.esxi_hostname = '192.168.1.241'
    esxi.esxi_username = 'root'
    esxi.esxi_password = 'prompt:'
    esxi.guest_numvcpus        = numvcpus
    esxi.guest_memsize         = memory
    esxi.guest_boot_disk_size  = storage
    esxi.guest_disk_type       = 'thin'
    esxi.guest_mac_address = [mac]
   end
  end
 end

# config.vm.provision :ansible do |ansible|
#  ansible.playbook = "site.yml"
# end
end