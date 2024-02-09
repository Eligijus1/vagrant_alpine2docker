# Require vagrant 1.8 or newer:
Vagrant.require_version ">= 1.8"

# BOX Configuration:
Vagrant.configure("2") do |config|
    # Configure our project to use alpine2docker Vagrant Box (https://github.com/dduportal/alpine2docker):
    config.vm.box = "dduportal/alpine2docker"

    # The hostname the machine should have:
    config.vm.hostname = "vagrant.test"

    # Configures networks on the machine:
    config.vm.network "private_network", ip: "172.28.128.30"

    # Configure machine settings:
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
    end

    # Enable additional provisioning with a shell script:
    config.vm.provision "shell", inline: <<-SHELL
        sudo apk update
        sudo apk add nmap
        sudo apk add git
        sudo apk add vim
	    echo "+-------------------------------------+"
	    echo "|                                     |"
	    echo "|      Vagrant setup completed        |"
	    echo "|                                     |"
	    echo "+-------------------------------------+"
    SHELL
end
