Vagrant.configure("2") do |config|
   config.vm.box = "centos6.5"

   config.vm.network :private_network, ip: "10.10.81.22"

   config.vm.provider :virtualbox do |vb|
     vb.customize ["modifyvm", :id, "--memory", "1024", "--cpus", "2", "--ioapic", "on"]
   end

   config.vm.provision :chef_solo do |chef|
     chef.cookbooks_path = [ "./cookbooks", "./site-cookbooks" ]
     chef.roles_path = "./roles"
     chef.add_role  "seleniumserver"

   end

end

