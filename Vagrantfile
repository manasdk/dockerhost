# -*- mode: ruby -*-
# vi: set ft=ruby :

hostname = ENV['HOSTNAME'] ? ENV['HOSTNAME'] : 'dockerhost'

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.network "private_network", ip: "192.168.80.10"
    config.vm.hostname = "#{hostname}"

    config.vm.define "dockerhost" do |dockerhost|
      dockerhost.vm.box = 'bento/ubuntu-14.04'
    end

    config.vm.provider :virtualbox do |vb|
      vb.name = "#{hostname}"
      vb.memory = 4096
      vb.cpus = 2
    end

    config.vm.provision :shell, :path => "scripts/bootstrap.sh"

end
