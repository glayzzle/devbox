Glayzzle devbox
================

Devbox for the Glayzzle project http://glayzzle.com.

In the box
------------

Ubuntu Precise 64 with latest :
- nodejs
- npm
- glayzzle

Requirements
------------

* [VirtualBox](https://www.virtualbox.org)
* [Vagrant](http://vagrantup.com)

Installation
------------

```bash
$ git clone https://github.com/glayzzle/devbox.git
$ cd devbox
$ vagrant up
```

Once the VM is booted you can log via SSH

```bash
$ vagrant ssh
```

Update
------------

Update devbox OS, nodejs and npm packages. 

```bash
$ vagrant provision
```

Glayzzle
------------
https://github.com/ichiriac/glayzzle
