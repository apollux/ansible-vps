# This guide is optimized for Vagrant 1.7 and above.
# Although versions 1.6.x should behave very similarly, it is recommended
# to upgrade instead of disabling the requirement below.
Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network "public_network"

  config.vm.provision "shell", inline: "apt-get update && apt-get -qq install python python-pycurl python-apt"

  config.vm.provision "streisand-host", type: "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "ansible/playbook.yml"
    ansible.sudo = true
  end


end


