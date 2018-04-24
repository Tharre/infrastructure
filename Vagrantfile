Vagrant.configure(2) do |config|

  config.vm.box = "debian/stretch64"
  config.vm.network :private_network, ip: "192.168.33.99"

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.skip_tags = "dhparam"
    ansible.extra_vars = {
      nginx_disable_ssl: true
    }
    ansible.playbook = "playbooks/borg1.yml"
  end

  config.vm.synced_folder ".", "/vagrant" #, type: "nfs"
end
