Nodejs Vagrant box
================

Ubuntu Precise box simply installing Nodejs via apt.

Requirements
------------

* [VirtualBox](https://www.virtualbox.org)
* [Vagrant](http://vagrantup.com)

Installation
------------

```bash
$ git clone https://github.com/vicb/vagrant-nodejs.git
$ cd vagrant-nodejs
$ vagrant up
```

Once the VM is booted you can log via SSH

```bash
$ vagrant ssh
```

Start a default server
------------
```bash
$ node /opt/hello/server.js
```

