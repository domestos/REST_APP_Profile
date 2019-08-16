# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  
  #For virtualBox
  #config.vm.box = "ubuntu/xenial64"
  #For KVM
  config.vm.box = "peru/ubuntu-18.04-desktop-amd64"

  config.vm.network "forwarded_port", host_ip: "127.0.0.1", guest: 8080, host: 8080
  config.vm.synced_folder "./src", "/home/vagrant/"

  config.vm.provision "shell", inline: <<-SHELL
    # Update and upgrade the server packages.
    sudo apt-get update
    sudo apt-get -y upgrade
    # Set Ubuntu Language
    sudo locale-gen en_GB.UTF-8
    # Install Python, SQLite and pip
    sudo apt-get install -y python3-dev sqlite python-pip
    # Upgrade pip to the latest version.
    sudo pip install --upgrade pip
    # Install and configure python virtualenvwrapper.
    sudo apt install virtualenv -y
    sudo apt install  git -y
    git clone https://github.com/domestos/varenik_bash

    
    # sudo pip install virtualenvwrapper
    # sudp apt install python3-venv
    # if ! grep -q VIRTUALENV_ALREADY_ADDED /home/vagrant/.bashrc; then
    #     echo "# VIRTUALENV_ALREADY_ADDED" >> /home/vagrant/.bashrc
    #     echo "WORKON_HOME=~/.virtualenvs" >> /home/vagrant/.bashrc
    #     echo "PROJECT_HOME=/vagrant" >> /home/vagrant/.bashrc
    #     echo "source /usr/local/bin/virtualenvwrapper.sh" >> /home/vagrant/.bashrc
    # fi
    # sudo python3 -m venv venv_profile_api
  
  
    SHELL
  
end