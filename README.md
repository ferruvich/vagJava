# Vagrant for Cumlaude backend
To use this Vagrant, if have to:

1. Run ‘vagrant up’ in vagrant folder : it starts the vagrant. If it's the first time the vagrant is started, it installs everything that is written in playbook.yml (In this case: nginx, postgresql and jetty);
2. Connect to the vagrant with ssh or putty
  - Host: localhost (127.0.0.1);
  - Port: 2222
  - Username: ubuntu
  - Password: if you are using ‘putty’ use the file ‘credentials/vagrantPass.ppk’, if you are using ‘ssh’, execute the following command
    ‘ssh -p 2222 -i credentials/private_key ubuntu@127.0.0.1’;
3. If you make any change in ansible files, you have to run ‘vagrant provision’ to effectively execute them;
4. Run ‘vagrant halt’ to shutdown the vagrant.
