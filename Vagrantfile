Vagrant.configure("2") do |config|
  config.vm.box = "jiehoes/lvtofossa"
  config.vm.network "private_network", ip: "192.168.56.30"
  #config.vm.network "private_network", type: "dhcp"
  config.vm.synced_folder "./", "/var/www/html", create: true, group: "www-data", owner: "www-data"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "2048"
  end
end
