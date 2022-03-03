Vagrant.configure("2") do |config|

  config.vm.box = "generic/ubuntu2004"
  config.vm.provider :libvirt do |domain|
    domain.memory = 2048
    domain.cpus = 2
  end

  config.vm.define :manager do |manager|
    manager.vm.network 'private_network', ip: "192.168.1.10"
  end

  config.vm.define :worker1 do |worker1|
    worker1.vm.network 'private_network', ip: "192.168.1.11"
  end

  config.vm.define :worker2 do |worker2|
    worker2.vm.network 'private_network', ip: "192.168.1.12"
  end

  config.vm.provision "docker" do |d|
    d.pull_images "busybox"
  end  
end
