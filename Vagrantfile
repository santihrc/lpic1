Vagrant.configure("2") do |config|
  config.vm.define "out" do |out|
    out.vm.provider "virtualbox" do |v|
      v.name = "vagrant_out"
      v.linked_clone = true
    end
    out.vm.box = "centos/6"
    out.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.1",
      nic_type: "virtio",
      netmask: "255.255.255.0"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "mgmt" do |mgmt|
    mgmt.vm.provider "virtualbox" do |v|
      v.name = "vagrant_mgmt"
      v.linked_clone = true
    end
    mgmt.vm.box = "centos/6"
    mgmt.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.2",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "int" do |int|
    int.vm.provider "virtualbox" do |v|
      v.name = "vagrant_int"
      v.linked_clone = true
    end
    int.vm.box = "centos/6"
    int.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.3",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    int.vm.network "private_network",
      virtualbox__intnet: "dmz_net",
      ip: "192.168.255.1",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "nginx" do |nginx|
    nginx.vm.provider "virtualbox" do |v|
      v.name = "vagrant_nginx"
      v.linked_clone = true
    end
    nginx.vm.box = "centos/6"
    nginx.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.4",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    nginx.vm.network "private_network",
      virtualbox__intnet: "dmz_net",
      ip: "192.168.255.3",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "back" do |back|
    back.vm.provider "virtualbox" do |v|
      v.name = "vagrant_back"
      v.linked_clone = true
    end
    back.vm.box = "centos/6"
    back.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.5",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    back.vm.network "private_network",
      virtualbox__intnet: "dmz_net",
      ip: "192.168.255.2",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    back.vm.network "private_network",
      virtualbox__intnet: "back_net",
      ip: "172.31.255.1",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "php" do |php|
    php.vm.provider "virtualbox" do |v|
      v.name = "vagrant_php"
      v.linked_clone = true
    end
    php.vm.box = "centos/6"
    php.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.6",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    php.vm.network "private_network",
      virtualbox__intnet: "back_net",
      ip: "172.31.255.3",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "dns" do |dns|
    dns.vm.provider "virtualbox" do |v|
      v.name = "vagrant_dns"
      v.linked_clone = true
    end
    dns.vm.box = "centos/6"
    dns.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.7",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "dhcp" do |dhcp|
    dhcp.vm.provider "virtualbox" do |v|
      v.name = "vagrant_dhcp"
      v.linked_clone = true
    end
    dhcp.vm.box = "centos/6"
    dhcp.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.8",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "ntp" do |ntp|
    ntp.vm.provider "virtualbox" do |v|
      v.name = "vagrant_ntp"
      v.linked_clone = true
    end
    ntp.vm.box = "centos/6"
    ntp.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.9",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "mysql" do |mysql|
    mysql.vm.provider "virtualbox" do |v|
      v.name = "vagrant_mysql"
      v.linked_clone = true
    end
    mysql.vm.box = "centos/6"
    mysql.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.10",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
  config.vm.define "tomcat" do |tomcat|
    tomcat.vm.provider "virtualbox" do |v|
      v.name = "vagrant_tomcat"
      v.linked_clone = true
    end
    tomcat.vm.box = "centos/6"
    tomcat.vm.network "private_network",
      virtualbox__intnet: "mgmt_net",
      ip: "10.255.255.11",
      netmask: "255.255.255.0",
      nic_type: "virtio"
    out.vm.provision "shell", inline: <<-HASTAQUI
      sudo yum update -y && sudo yum install -y git
    HASTAQUI
  end
end
 
