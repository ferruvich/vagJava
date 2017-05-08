# Vagrant for Cumlaude backend
To use this Vagrant, if have to:

1. Run `vagrant up` in vagrant folder to start it. If it's the first time the vagrant is started, it installs everything that is written in playbook.yml (In this case: nginx, postgresql and jetty);
2. Copy the file `.vagrant/machines/virtualbox/virtualbox/private_key` in a new folder named `credentials`. If you'll use putty to connect via ssh, create a `.ppk` key with PuttyGen and put it into `credentials`;
3. Connect to the vagrant with ssh or putty
  - Host: localhost (127.0.0.1);
  - Port: 2222
  - Username: ubuntu
  - Password: if you are using `putty` use the file `credentials/{ppkFileName}.ppk`, if you are using `ssh`, execute the following command:
    `ssh -p 2222 -i credentials/private_key ubuntu@127.0.0.1`;
4. If you make any change in ansible files, you have to run `vagrant provision` to effectively execute them;
5. Run `vagrant halt` to shutdown the vagrant.
