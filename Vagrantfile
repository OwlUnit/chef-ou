# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "opscode-ubuntu-12.04-i386"
  config.vm.box_url = "https://opscode-vm.s3.amazonaws.com/vagrant/opscode_ubuntu-12.04-i386_provisionerless.box"

  config.vm.hostname = "local.owlunit.com"

  # A Vagrant plugin that ensures the desired version of Chef is installed via the platform-specific Omnibus packages
  # vagrant plugin install vagrant-omnibus
  config.omnibus.chef_version = :latest

  # Enables Berkself integration, installs all cookbooks listed in berksfile
  # vagrant plugin install vagrant-berkself
  config.berkshelf.enabled = true 

  config.vm.network :forwarded_port, guest: 8080, host: 9090

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network :private_network, ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider :virtualbox do |vb|
    # Don't boot with headless mode
    # vb.gui = true
  
    # Use VBoxManage to customize the VM. For example to change memory:
    vb.customize ["modifyvm", :id, "--memory", "512"]
  end

  # config.vm.provision :chef_solo do |chef|
  #   chef.cookbooks_path = "cookbooks"
  #   chef.roles_path = "roles"
  #   chef.data_bags_path = "data_bags"
  #   chef.add_recipe "mysql"
  #   chef.add_role "web"
  #
  #   # You may also specify custom JSON attributes:
  #   chef.json = { :mysql_password => "foo" }
  # end

  # Enable provisioning with chef server, specifying the chef server URL,
  # and the path to the validation key (relative to this Vagrantfile).
  #
  # config.vm.provision :chef_client do |chef|
  #   chef.chef_server_url = "https://api.opscode.com/organizations/owlunit"
  #   chef.validation_client_name = "owlunit-validator"
  #   chef.validation_key_path = ".chef/owlunit-validator.pem"
  # end
end
