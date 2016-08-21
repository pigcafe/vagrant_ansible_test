Vagrant.configure("2") do |config|
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
  config.ssh.insert_key = false
  
  config.vm.define "mngsrv", primary: true do |mngsrv|
    mngsrv.vm.box = "bento/centos-7.2"
    mngsrv.vm.network "private_network", ip: "10.0.0.10"
  end

  config.vm.define "dbgsrv" do |dbgsrv|
    dbgsrv.vm.box = "bento/ubuntu-14.04"
    dbgsrv.vm.network "private_network", ip: "10.0.0.20"
  end

  config.vm.define "devsrv" do |devsrv|
    devsrv.vm.box = "bento/ubuntu-14.04"
    devsrv.vm.network "private_network", ip: "10.0.0.30"
  end

end

