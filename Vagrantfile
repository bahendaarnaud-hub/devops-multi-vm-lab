Vagrant.configure("2") do |config|

  # Define VM 1: The Front-End / Web Server
  config.vm.define "web-vm" do |web|
    web.vm.box = "ubuntu/jammy64"
    web.vm.network "private_network", ip: "192.168.56.10"
    web.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
      v.name = "web-vm"
    end
    # Synced directory: sync local html folder to web server root
    web.vm.synced_folder "html", "/var/www/html"
  end

  # Define VM 2: The Back-End / App Server (Tomcat)
  config.vm.define "app-vm" do |app|
    app.vm.box = "ubuntu/jammy64"
    app.vm.network "private_network", ip: "192.168.56.20"
    app.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
      v.name = "app-vm"
    end
  end

end
