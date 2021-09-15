Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.ssh.insert_key = false

  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|
    v.memory=1024
    v.linked_clone = true
  end

  # Master server
  config.vm.define "master" do |master|
    master.vm.hostname = "master.test"
    master.vm.network :private_network, ip: "192.168.10.100"
  end

  # Node 1
  config.vm.define "node1" do |node|
    node.vm.hostname = "node1.test"
    node.vm.network :private_network, ip: "192.168.10.101"
  end

  # Node 2
  config.vm.define "node2" do |node|
    node.vm.hostname = "node2.test"
    node.vm.network :private_network, ip: "192.168.10.102"
  end
end
