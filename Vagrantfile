# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "puphpet/ubuntu1404-x64"
  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--vram", "256"]
    v.gui = true
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y haskell-platform
    sudo apt-get install -y cabal-install
    sudo cabal update
    sudo cabal install cabal-install --global 
    sudo apt-get install python-software-properties software-properties-common
    sudo add-apt-repository ppa:zoogie/sdl2-snapshot -y
    sudo apt-get update
    sudo apt-get install -y libsdl2-dev=2.0.3+z4~20140315-8621-1ppa1trusty1 
    sudo apt-get install -y git
    sudo apt-get install -y xfce4
    sudo apt-get install -y firefox
    sudo apt-get install -y virtualbox-guest-dkms virtualbox-guest-utils virtualbox-guest-x11
  SHELL
end
