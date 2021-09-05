Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.ssh.insert_key = false

  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|
    v.memory=1024
    v.linked_clone = true
  end

  # Kubernetes Master Server
  config.vm.define "master" do |master|
    master.vm.hostname = "master.test"
    master.vm.network :private_network, ip: "192.168.10.100"
  end

  # Kubernetes pod 1
  config.vm.define "pod1" do |pod|
    pod.vm.hostname = "pod1.test"
    pod.vm.network :private_network, ip: "192.168.10.101"
  end

  # DB server
  config.vm.define "pod2" do |pod|
    pod.vm.hostname = "pod2.test"
    pod.vm.network :private_network, ip: "192.168.10.102"
  end
end
