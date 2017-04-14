
##################################
#  Ansible Inventory Definitions #
##################################
      
groups = {
  "spine" => ["spine1", "spine2", "spine3"],
  "leaf" => ["leaf1", "leaf2", "leaf3", "leaf4", "leaf5", "leaf6"],
  "servers" => ["host12", "host34", "host56"],
  "networking:children" => ["spine", "leaf"]
}


##################################
#   Vagrant Machine Definitions  #
##################################
      
Vagrant.configure(2) do |config|
  
  config.vm.define "spine1" do |spine1|
	spine1.vm.box = "CumulusCommunity/cumulus-vx"
        spine1.vm.box_version = "3.2.1"


    spine1.vm.hostname = "spine1"
    spine1.vm.network "private_network", virtualbox__intnet: "l1s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l2s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l3s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l4s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l5s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l6s1"
    spine1.vm.network "private_network", virtualbox__intnet: "peerlink_s12"
    spine1.vm.network "private_network", virtualbox__intnet: "peerlink_s21"

    spine1.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end
    
    spine1.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111111"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end

  end

  config.vm.define "spine2" do |spine2|
	spine2.vm.box = "CumulusCommunity/cumulus-vx"
        spine2.vm.box_version = "3.2.1"
    spine2.vm.hostname = "spine2"

    spine2.vm.network "private_network", virtualbox__intnet: "l1s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l2s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l3s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l4s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l5s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l6s2"
    spine2.vm.network "private_network", virtualbox__intnet: "peerlink_s12"
    spine2.vm.network "private_network", virtualbox__intnet: "peerlink_s21"

    spine2.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    spine2.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111112"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end
  end

  config.vm.define "spine3" do |spine3|
	spine3.vm.box = "CumulusCommunity/cumulus-vx"
        spine3.vm.box_version = "3.2.1"

    spine3.vm.hostname = "spine3"
    spine3.vm.network "private_network", virtualbox__intnet: "l1s3"
    spine3.vm.network "private_network", virtualbox__intnet: "l2s3"
    spine3.vm.network "private_network", virtualbox__intnet: "l3s3"
    spine3.vm.network "private_network", virtualbox__intnet: "l4s3"
    spine3.vm.network "private_network", virtualbox__intnet: "l5s3"
    spine3.vm.network "private_network", virtualbox__intnet: "l6s3"

    spine3.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end
    
    spine3.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111113"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end

  end
  config.vm.define "leaf1" do |leaf1|
	leaf1.vm.box = "CumulusCommunity/cumulus-vx"
        leaf1.vm.box_version = "3.2.1"

    leaf1.vm.hostname = "leaf1"
    leaf1.vm.network "private_network", virtualbox__intnet: "l1s1"
    leaf1.vm.network "private_network", virtualbox__intnet: "l1s2"
    leaf1.vm.network "private_network", virtualbox__intnet: "peerlink_l12"
    leaf1.vm.network "private_network", virtualbox__intnet: "peerlink_l21"
    leaf1.vm.network "private_network", virtualbox__intnet: "host12l1"
    leaf1.vm.network "private_network", virtualbox__intnet: "l1s3"
    
    leaf1.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf1.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111121"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end

  end

  config.vm.define "leaf2" do |leaf2|
	leaf2.vm.box = "CumulusCommunity/cumulus-vx"
        leaf2.vm.box_version = "3.2.1"

    leaf2.vm.hostname = "leaf2"
    leaf2.vm.network "private_network", virtualbox__intnet: "l2s1"
    leaf2.vm.network "private_network", virtualbox__intnet: "l2s2"
    leaf2.vm.network "private_network", virtualbox__intnet: "peerlink_l12"
    leaf2.vm.network "private_network", virtualbox__intnet: "peerlink_l21"
    leaf2.vm.network "private_network", virtualbox__intnet: "host12l2"
    leaf2.vm.network "private_network", virtualbox__intnet: "l2s3"
    
    leaf2.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf2.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111122"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end

  end


  config.vm.define "leaf3" do |leaf3|
	leaf3.vm.box = "CumulusCommunity/cumulus-vx"
        leaf3.vm.box_version = "3.2.1"

    leaf3.vm.hostname = "leaf3"
    leaf3.vm.network "private_network", virtualbox__intnet: "l3s1"
    leaf3.vm.network "private_network", virtualbox__intnet: "l3s2"
    leaf3.vm.network "private_network", virtualbox__intnet: "peerlink_l34"
    leaf3.vm.network "private_network", virtualbox__intnet: "peerlink_l43"
    leaf3.vm.network "private_network", virtualbox__intnet: "host34l3"
    leaf3.vm.network "private_network", virtualbox__intnet: "l3s3"

    leaf3.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf3.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111123"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end

  end

  config.vm.define "leaf4" do |leaf4|
	leaf4.vm.box = "CumulusCommunity/cumulus-vx"
        leaf4.vm.box_version = "3.2.1"

    leaf4.vm.hostname = "leaf4"
    leaf4.vm.network "private_network", virtualbox__intnet: "l4s1"
    leaf4.vm.network "private_network", virtualbox__intnet: "l4s2"
    leaf4.vm.network "private_network", virtualbox__intnet: "peerlink_l34"
    leaf4.vm.network "private_network", virtualbox__intnet: "peerlink_l43"
    leaf4.vm.network "private_network", virtualbox__intnet: "host34l4"
    leaf4.vm.network "private_network", virtualbox__intnet: "l4s3"
  
    leaf4.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf4.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111124"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end

  end

  config.vm.define "leaf5" do |leaf5|
	leaf5.vm.box = "CumulusCommunity/cumulus-vx"
        leaf5.vm.box_version = "3.2.1"

    leaf5.vm.hostname = "leaf5"
    leaf5.vm.network "private_network", virtualbox__intnet: "l5s1"
    leaf5.vm.network "private_network", virtualbox__intnet: "l5s2"
    leaf5.vm.network "private_network", virtualbox__intnet: "peerlink_l56"
    leaf5.vm.network "private_network", virtualbox__intnet: "peerlink_l65"
    leaf5.vm.network "private_network", virtualbox__intnet: "host56l5"
    leaf5.vm.network "private_network", virtualbox__intnet: "l5s3"

    leaf5.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf5.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111125"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end

  end

  config.vm.define "leaf6" do |leaf6|
	leaf6.vm.box = "CumulusCommunity/cumulus-vx"
        leaf6.vm.box_version = "3.2.1"

    leaf6.vm.hostname = "leaf6"
    leaf6.vm.network "private_network", virtualbox__intnet: "l6s1"
    leaf6.vm.network "private_network", virtualbox__intnet: "l6s2"
    leaf6.vm.network "private_network", virtualbox__intnet: "peerlink_l56"
    leaf6.vm.network "private_network", virtualbox__intnet: "peerlink_l65"
    leaf6.vm.network "private_network", virtualbox__intnet: "host56l6"
    leaf6.vm.network "private_network", virtualbox__intnet: "l6s3"

    leaf6.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf6.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--macaddress1", "000000111126"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
    end

  end


  config.vm.define "host12" do |host12|
	host12.vm.box = "ubuntu/trusty64"

    host12.vm.hostname = "host12"
    host12.vm.network "private_network", virtualbox__intnet: "host12l1", auto_config: false
    host12.vm.network "private_network", virtualbox__intnet: "host12l2", auto_config: false
  
    host12.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
    end

    host12.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/host-provision.yml"
      ansible.groups = groups
    end

  end

  config.vm.define "host34" do |host34|
	host34.vm.box = "ubuntu/trusty64"

    host34.vm.hostname = "host34"
    host34.vm.network "private_network", virtualbox__intnet: "host34l3", auto_config: false
    host34.vm.network "private_network", virtualbox__intnet: "host34l4", auto_config: false
  
    host34.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
    end

    host34.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/host-provision.yml"
      ansible.groups = groups
    end

  end

  config.vm.define "host56" do |host56|
	host56.vm.box = "ubuntu/trusty64"

    host56.vm.hostname = "host56"
    host56.vm.network "private_network", virtualbox__intnet: "host56l5", auto_config: false
    host56.vm.network "private_network", virtualbox__intnet: "host56l6", auto_config: false
  
    host56.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
    end

    host56.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/host-provision.yml"
      ansible.groups = groups
    end
  end
end
