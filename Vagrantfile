# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.network :forwarded_port, guest: 80, host: 8088
  config.vm.network :private_network, ip: "192.168.88.88" 

  config.vm.provider :virtualbox do |vb|
    vb.name = "Glayzzle devbox"
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--ostype", "Ubuntu_64"]
  end

  config.vm.provision "shell", inline: <<-shell
    apt-get install python-software-properties  -y --force-yes
    apt-get install screen vim -y --force-yes
    apt-get install git -y --force-yes

    add-apt-repository ppa:chris-lea/node.js
    apt-get update
    apt-get install python g++ make nodejs -y --force-yes

    apt-get install npm -y --force-yes

    if [ ! -d "/usr/lib/node_modules/glayzzle" ]; then
        sudo npm install -g glayzzle
    fi

    if [ ! -d "/usr/lib/node_modules/node-gyp" ]; then
        sudo npm install -g node-gyp
    fi

    sudo npm update -g

    if [ ! -d "/vagrant/glayzzle" ]; then
      git clone https://github.com/glayzzle/glayzzle.git /vagrant/glayzzle
      chmod -R 755 /vagrant/glayzzle
    fi

    if [ ! -d "/vagrant/poojs" ]; then
        git clone https://github.com/glayzzle/poojs.git /vagrant/poojs
    fi

    if [ ! -d "/vagrant/tests" ]; then
        git clone https://github.com/glayzzle/tests.git /vagrant/tests
    fi


    cp /vagrant/.bash_login /home/vagrant/.bash_login
    cp /vagrant/.motd /home/vagrant/.motd
  shell
end
