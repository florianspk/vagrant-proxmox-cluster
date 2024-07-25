require "yaml"
settings = YAML.load_file "settings.yaml"

Vagrant.configure("2") do |config|
  current_dir = __dir__
  config.vm.box = "castor/proxmox"
  config.vm.box_version = "8.2.2"
  config.vm.box_check_update = true

  config.vm.synced_folder current_dir, "/vagrant", type: "nfs", mount_options: ['rw', 'tcp', 'nfsvers=4']
  (1..2).each do |i|
    config.vm.define "pv0#{i}" do |pve|
      pve.vm.hostname = "pve0#{i}"
      pve.vm.provider "libvirt" do |libvirt|
        libvirt.cpus = settings["pve"]["cpu"]
        libvirt.memory = settings["pve"]["memory"]
        libvirt.nested = true
      end
      pve.vm.provision "shell", inline: <<-SHELL
        echo "root:root" | sudo chpasswd
      SHELL
    end
  end
end
