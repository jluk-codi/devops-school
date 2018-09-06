Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "webserver"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.usable_port_range = 3000..8999
  config.vm.network "forwarded_port", guest: 3000, host: 3000, auto_correct: true, protocol: "tcp"
  config.vm.network "forwarded_port", guest: 3000, host: 3000, auto_correct: true, protocol: "udp"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "2048"
  end
  # Ansible start
  config.vm.provision "ansible_local" do |ansible|
    ansible.install = true
    ansible.playbook = "ansible_playbook.yml"
  end
end
