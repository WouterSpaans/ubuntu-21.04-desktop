# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "wouterspaans1/ubuntu-21.04-desktop"
    config.vm.box_version = "1"
    config.vm.network "public_network"
    config.vm.provider "vmware_desktop" do |v|
      v.gui = true
      v.vmx["memsize"] = "4096"
      v.vmx["numvcpus"] = "4"
      v.vmx["vhv.enable"] = "TRUE"
      v.vmx["mks.enable3d"] = "TRUE"
    end
    config.vm.provision "shell", inline: <<-SHELL
      ansible-pull -U https://github.com/WouterSpaans/ubuntu-21.04-desktop.git
      reboot
    SHELL
  end