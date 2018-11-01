VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "master" do |master|
    master.vm.box = "CentOS7.5_1804"
    master.vm.network :private_network, ip: "192.168.9.100", virtualbox__intnet: "DFS-Network"
    master.vm.hostname = "controller"

    master.vm.provider :virtualbox do |vb|
      #vb.customize ["modifyvm", :id, "--cpus", "1", "--memory", 2048]
	  vb.customize ["modifyvm", :id, "--cpus", "1", "--memory", 2048, "--groups", "/ansible"]
	  vb.name = "ans-master"
    end
  end
  
  config.vm.define "web" do |web|
    web.vm.box = "CentOS7.5_1804"
    web.vm.network :private_network, ip: "192.168.9.101", virtualbox__intnet: "DFS-Network"
    web.vm.hostname = "web"

    web.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--cpus", "1", "--memory", 1024, "--groups", "/ansible"]
	  vb.name = "ans-web"
    end
  end
  
  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/trusty64"
    db.vm.network :private_network, ip: "192.168.9.102", virtualbox__intnet: "DFS-Network"
    db.vm.hostname = "database"

    db.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--cpus", "1", "--memory", 1024, "--groups", "/ansible"]
	  vb.name = "ans-db"
    end
  end
  
  config.vm.define "dev" do |dev|
    dev.vm.box = "CentOS7.5_1804"
    dev.vm.network :private_network, ip: "192.168.9.103", virtualbox__intnet: "DFS-Network"
    dev.vm.hostname = "dev"

    dev.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--cpus", "1", "--memory", 1024, "--groups", "/ansible"]
	  vb.name = "ans-dev"
    end
  end
   
end