
# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # --------------------------------------------------------------------
  # Definitions for the VirtualBox machine
  # --------------------------------------------------------------------
  config.vm.define "virtualbox"  do |vbox|
    vbox.vm.provider "virtualbox" do |v|
        v.name = "vagCumlaude"
        v.memory = 4096
        v.cpus = 2
    end
    vbox.vm.box = "ubuntu/xenial64"
      # Configure vbguest auto update options
      #vbox.vbguest.auto_update = false
      #vbox.vbguest.no_install = false
      #vbox.vbguest.no_remote = true

    vbox.vm.hostname = "ansible-Java"
    vbox.vm.network "forwarded_port", guest: 80, host: 8080
    vbox.vm.network "forwarded_port", guest: 8080, host: 8081
    vbox.vm.network "forwarded_port", guest: 8090, host: 8090
    vbox.vm.network "forwarded_port", guest: 5432, host: 5432
    #vbox.vm.network "forwarded_port", guest: 5050, host: 5050

    # --------------------------------------------------------------------
    # Definitions user and passwd for the VirtualBox machine
    # --------------------------------------------------------------------

      vbox.ssh.username = "ubuntu"
      vbox.ssh.password = "easynetwork"

    # --------------------------------------------------------------------
    # Definitions synced_folder for the VirtualBox machine
    # ps. Use this post provisioning action
    # --------------------------------------------------------------------

      #vbox.vm.synced_folder "./fs/vagrant", "/vagrant", :mount_options => ["ro"]
      vbox.vm.synced_folder "./www", "/var/www"
      #vbox.vm.synced_folder "./fs/code", "/code"


    vbox.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
    #vbox.vm.provision "shell", path:
    end
      # Tell the user what to do next
    vbox.vm.provision "shell", inline: "echo 'Happy Ending! Now try logging in with: vagrant ssh virtualbox'"
    end
end
