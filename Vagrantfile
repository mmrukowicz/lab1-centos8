VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "generic/centos8"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
  end

  config.vm.network "private_network", type: "dhcp"

  config.hostmanager.enabled = true
  config.hostmanager.ip_resolver = proc do |vm, resolving_vm|
	  if vm.id
		`VBoxManage.exe guestproperty get #{vm.id} "/VirtualBox/GuestInfo/Net/1/V4/IP"`.split()[1]
	  end
  end

  config.vm.define :server do |srv|
    srv.vm.hostname = "ansible-server"
    srv.vm.provision "shell", path: "server-config"
  end

  config.vm.define :client1 do |cl1|
    cl1.vm.hostname = "ansible-client-1"
    cl1.vm.provision "shell", path: "client-config"
  end
  
  config.vm.define :client2 do |cl2|
    cl2.vm.hostname = "ansible-client-2"
    cl2.vm.provision "shell", path: "client-config"
  end
end
