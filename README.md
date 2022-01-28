# lab1-centos8
This project will create 3 machines named: ansible-server, ansible-client-1,  ansible-client-2. Connection between them will be already established. You can edit server-config and client-config to put whatever you want to be preinstalled.

### Requirements:
- Oracle Virtual Box installed https://www.virtualbox.org/
- Vagrant installed https://www.vagrantup.com/
- Vagrant host manager plugin installed, by running this command:  
`vagrant plugin install vagrant-hostmanager`
- Put `C:\Program Files\Oracle\VirtualBox` in PATH environment variable (If you are on Windows) so this line in Vagrantfile will work ``VBoxManage.exe guestproperty get #{vm.id} "/VirtualBox/GuestInfo/Net/1/V4/IP"`.split()[1]``, on Linux just removing `.exe` part should work.

### Provisioning
- Clone/download repository 
- Open folder with repository and run `vagrant up`

After lab is provisioned, generate ssh key pair on ansible-server and copy public key to `authorized_keys` file on client servers.


