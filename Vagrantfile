# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "frensjan/centos-7-64-lxc"

  #config.vm.define "logstash" do |logstash|
    #logstash.vm.hostname = "logstash"
    #logs.vm.network :private_network, ip: "192.168.9.90"

    #logs.vm.provision :ansible do |ansible|
      #ansible.playbook = "provisioning/elk/playbook.yml"
      #ansible.inventory_path = "provisioning/elk/inventory"
      #ansible.sudo = true
    #end
     #end
  # fluentd forwarder server
  config.vm.define "fluentdfw" do |fluentdfw|
    fluentdfw.vm.hostname = "fluentdfw"
  end

  # fluentd aggregator server
  config.vm.define "fluentdag" do |fluentdag|
    fluentdag.vm.hostname = "fluentdag"
  end

  # redis server.
  #config.vm.define "redis" do |redis|
    #redis.vm.hostname = "redis"
    #webs.vm.network :private_network, ip: "192.168.9.91"
  #end

  # elasticsearch server.
  config.vm.define "elasticsearch" do |elasticsearch|
    elasticsearch.vm.hostname = "elasticsearch"
    #webs.vm.network :private_network, ip: "192.168.9.91"
  end
  # kibana server.
  config.vm.define "kibana" do |kibana|
    kibana.vm.hostname = "kibana"
    #webs.vm.network :private_network, ip: "192.168.9.91"
  end
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
      config.vm.provision "ansible" do |ansible|
      #ansible.ask_vault_pass = true
      ansible.playbook = "site.yml"
      end 
   #end

end
