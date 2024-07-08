Vagrant.configure("2") do |config|
    # Configuración de la primera máquina virtual
    config.vm.define "webserver1" do |node|
      node.vm.box = "ubuntu/bionic64"
      node.vm.network "private_network", type: "dhcp"
      
      # Instalación de Apache
      node.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get install -y apache2
      SHELL
      
      # Configuración para compartir carpeta local con Apache
      node.vm.synced_folder "C:/xampp/htdocs/local/index.html", "/var/www/html"
    end
  
    # Configuración de la segunda máquina virtual (opcional)
    config.vm.define "webserver2" do |node|
      node.vm.box = "ubuntu/bionic64"
      node.vm.network "private_network", type: "dhcp"
      
      # Instalación de Apache
      node.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get install -y apache2
      SHELL
      
      # Configuración para compartir carpeta local con Apache
      node.vm.synced_folder "C:/xampp/htdocs/local/in.html", "/var/www/html"
    end
  end