# Require vagrant 1.8 or newer:
Vagrant.require_version ">= 1.8"

# BOX Configuration:
Vagrant.configure("2") do |config|
    #config.ssh.forward_agent = true

    # Configure our project to use Official Ubuntu 22.04 (https://app.vagrantup.com/ubuntu/boxes/jammy64)
    # (Trusty Tahr) build as a base:
    config.vm.box = "dduportal/alpine2docker"

    # The hostname the machine should have. Defaults to nil. If nil, 
    # Vagrant will not manage the hostname. If set to a string, the 
    # hostname will be set on boot.
    config.vm.hostname = "vagrant.test"

    # Configures networks on the machine:
    config.vm.network "private_network", ip: "172.28.128.30"

    config.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
    end

    # Define shell:
    #config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

    # Enable provisioning with a shell script. Additional provisioners such as
    # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
    # documentation for more information about their specific syntax and use.
    config.vm.provision "shell", inline: <<-SHELL
        sudo apk update
        sudo apk add nmap
	    echo "+-------------------------------------+"
	    echo "|                                     |"
	    echo "|      Vagrant setup completed        |"
	    echo "|                                     |"
	    echo "+-------------------------------------+"
    SHELL
end
