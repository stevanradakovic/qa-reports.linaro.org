# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/xenial64"
    master.vm.hostname = "qa-reports-master"
    master.vm.provider :libvirt do |domain|
      domain.machine_virtual_size = 30
    end
  end

  config.vm.define "worker" do |worker|
    worker.vm.box = "ubuntu/xenial64"
    worker.vm.hostname = 'qa-reports-worker'
  end

  config.vm.define "worker-quick" do |worker|
    worker.vm.box = "ubuntu/xenial64"
    worker.vm.hostname = 'qa-reports-worker-quick'
  end

  config.vm.provider :libvirt do |domain|
    domain.memory = 4096
    domain.cpus = 2
  end

  config.vm.provision "shell", inline: <<-SHELL
  DEBIAN_FRONTEND=noninteractive apt-get install -qy avahi-daemon python3
  SHELL
end
