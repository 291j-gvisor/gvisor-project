# Reference: https://www.vagrantup.com/docs/

Vagrant.configure("2") do |config|
    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        # https://www.virtualbox.org/manual/UserManual.html#nested-virt
        v.customize ["modifyvm", :id, "--nested-hw-virt", "on"]
    end
    config.vm.box = "ubuntu/bionic64"
    config.vm.provision "shell", path: "script/provision-ubuntu.sh", privileged: false
    config.vm.synced_folder ".", "/home/vagrant/work"
end