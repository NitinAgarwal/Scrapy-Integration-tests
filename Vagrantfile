# Vagrant file in which the virtual machine ready to run docker containers on bootup

box = "ubuntu"
url = "http://files.vagrantup.com/precise64.box"
hostname = "scrapy-gsoc2014-it"
ram = "512"


# Make sure you have the latest version of Vagrant 1.4.3 and Virtualbox 4.3.6 installed in your system before running this Vagrantfile.
  
Vagrant::configure("2") do |config|
  # All Vagrant configuration is done here.

  # Make sure you have installed vagrant-proxyconf plugin
  # vagrant plugin install vagrant-proxyconf
  if Vagrant.has_plugin?("vagrant-proxyconf")
    config.proxy.http     = "http://proxy.iiit.ac.in:8080/"
    config.proxy.https    = "http://proxy.iiit.ac.in:8080/"
    config.proxy.no_proxy = "localhost,127.0.0.1"
  end
  
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = box

  # The url from where the 'conf.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  config.vm.box_url = url
  
  # Hostname
  config.vm.host_name = hostname

  config.vm.provider "virtualbox" do |v| 
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end


  # Docker Provision can automatically install docker, pull docker containers
  # and configure certain containers to run on boot.
  config.vm.provision "docker" do |docker|
    # Pulling images
    docker.pull_images "ubuntu" 
  end  
end
