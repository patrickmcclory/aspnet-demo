# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Vagrant configuration and machine provision


  config.vm.define 'mono' do |mono|    
    mono.vm.box = 'ubuntu1404lts'
    mono.vm.box_url = 'https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box'
    mono.vm.hostname = 'mono.vagrant.dev'
    mono.vm.network 'private_network', type: 'dhcp'
    mono.vm.provision 'shell', inline:'wget http://download.mono-project.com/repo/xamarin.gpg -O /tmp/xamarin.gpg'
    mono.vm.provision 'shell', inline:'echo "deb http://download.mono-project.com/repo/debian wheezy main" | sudo tee -a /etc/apt/sources.list.d/mono-xamarin.list'
    mono.vm.provision 'shell', inline:'echo "deb http://download.mono-project.com/repo/debian wheezy-apache24-compat main" | sudo tee -a /etc/apt/sources.list.d/mono-xamarin.list'
    mono.vm.provision 'shell', inline:'sudo apt-get update -y'
    mono.vm.provision 'shell', inline:'sudo apt-get install -y mono-devel --force-yes'
  end

end
