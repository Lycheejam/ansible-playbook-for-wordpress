Vagrant.configure("2") do |config|
  config.vm.box = "gbailey/amzn2"

  config.vm.define "vg-web" do |vg_web|
    vg_web.vm.hostname = "vg-web"
    vg_web.vm.network :private_network, ip: "192.168.50.10"

    vg_web.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.inventory_path = "./inventories/vagrant/hosts.yml"
      ansible.limit = 'all'
      ansible.become = true
    end
  end
end
