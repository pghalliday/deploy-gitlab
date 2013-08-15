# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # set the chef version
  config.omnibus.chef_version = :latest

  # enable berkshelf
  config.berkshelf.enabled = true

  config.vm.define "berkshelf" do |node|
    node.vm.hostname = "berkshelf"
    node.vm.box = "opscode_ubuntu-12.04_provisionerless"
    node.vm.box_url = "https://opscode-vm-bento.s3.amazonaws.com/vagrant/opscode_ubuntu-12.04_provisionerless.box"

    node.vm.provider :virtualbox do |vb|
      # Give enough horsepower to build without taking all day.
      vb.customize [
        "modifyvm", :id,
        "--memory", "1024",
        "--cpus", "2",
      ]
    end
    
    node.vm.provision :chef_solo do |chef|
      # Currently overriding git urls to work around firewall issues
      chef.run_list = [
        "recipe[berkshelf]"
      ]
    end
  end
end