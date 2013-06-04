.. _install:

How to install?
=======================

This document shows the basic steps of installing AppScale on a laptop. 


Install VirtualBox
------------------------------------

Download and install VirtualBox on your host machine using these `instructions <http://www.virtualbox.org/wiki/Downloads>`_.


Install Vagrant
---------------------------

Download and install Vagrant on your host machine using these `directions <http://docs.vagrantup.com/v2/installation/>`_.

Install AppScale tools on local machine
--------------

First, Install `homebrew <http://mxcl.github.com/homebrew/>`_.

Make sure that homebrew is installed properly with ``brew doctor``. Fix all issues if there are any.

Then, get latest appscale tools. If a newer version is available at the `appscale download page <http://download.appscale.com/>`_, please update this page accordingly. ::

	brew install wget
	wget https://github.com/AppScale/appscale-tools/archive/1.6.9.tar.gz -O appscale-tools-1.6.9.tar.gz
	tar xvf appscale-tools-1.6.9.tar.gz
	./appscale-tools-1.6.9/osx/appscale_install.sh

Update PATH ::

	export PATH="$PATH:/usr/local/appscale-tools/bin"

Register the Image with Vagrant
-----------------

To register an AppScale virtual machine (VM) with vagrant, execute the following: ::

	mkdir -p ~/appscale
	cd ~/appscale
	vagrant box add appscale1.6.9 http://download.appscale.com/download/AppScale%201.6.9%20VirtualBox%20Image
	vagrant init

Configure and start your virtual machine
-------------------

The ``vagrant init`` command above creates a ``Vagrantfile`` in the current directory. Next, we need to modify this file to give our VM an IP address that our host machine can access it on. To do this, open ``Vagrantfile`` and modify the following lines ::

	config.vm.network :hostonly, "192.168.33.10"
	config.vm.box = "appscale1.6.9"
	config.vm.customize ["modifyvm", :id, "--memory", 2048]

Next, start your AppScale virtual machine, ssh into it, and change the root password: ::


	vagrant up
	vagrant ssh     
	sudo -s passwd 
	exit

Start and shutdown AppScale
-------------------

Start AppScale by running: ::

	appscale up

Shut down your apps and AppScale deployment by running: ::

	appscale down
