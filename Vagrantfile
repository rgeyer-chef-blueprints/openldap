require 'berkshelf/vagrant'
require "rs_vagrant_shim"

Vagrant::Config.run do |config|
  config.vm.define :producer do |prod_config|
    prod_config.berkshelf.berksfile_path = "Berksfile"

    prod_config.vm.host_name = "openldap-producer"

    prod_config.vm.box = "ri_centos6.3_v5.8.8"
    prod_config.vm.box_url = "https://s3.amazonaws.com/rgeyer/pub/ri_centos6.3_v5.8.8_vagrant.box"

    prod_config.vm.network :hostonly, "192.168.128.2"

    prod_config.ssh.max_tries = 40
    prod_config.ssh.timeout   = 120

    prod_config.vm.provision Vagrant::RsVagrantShim::Provisioners::RsVagrantShim do |chef|
      chef.run_list_dir = "runlists/openldap-producer"
      chef.shim_dir = "rs_vagrant_shim/openldap-producer"
    end

    hdd_file = "producer_storage.vdi"
    unless File.exists?(hdd_file)
      prod_config.vm.customize [
        "createhd",
        "--filename", hdd_file,
        "--size", 10240
      ]
    end
    prod_config.vm.customize [
      "storageattach",
      :id,
      "--storagectl", "SATA Controller",
      "--port", 1,
      "--type", "hdd",
      "--medium", hdd_file
    ]
  end

  config.vm.define :consumer do |cons_config|
    cons_config.berkshelf.berksfile_path = "Berksfile"

    cons_config.vm.host_name = "openldap-consumer"

    cons_config.vm.box = "ri_centos6.3_v5.8.8"
    cons_config.vm.box_url = "https://s3.amazonaws.com/rgeyer/pub/ri_centos6.3_v5.8.8_vagrant.box"

    cons_config.vm.network :hostonly, "192.168.128.3"

    cons_config.ssh.max_tries = 40
    cons_config.ssh.timeout   = 120

    cons_config.vm.provision Vagrant::RsVagrantShim::Provisioners::RsVagrantShim do |chef|
      chef.run_list_dir = "runlists/openldap-consumer"
      chef.shim_dir = "rs_vagrant_shim/openldap-consumer"
    end

    hdd_file = "consumer_storage.vdi"
    unless File.exists?(hdd_file)
      cons_config.vm.customize [
        "createhd",
        "--filename", hdd_file,
        "--size", 10240
      ]
    end
    cons_config.vm.customize [
      "storageattach",
      :id,
      "--storagectl", "SATA Controller",
      "--port", 1,
      "--type", "hdd",
      "--medium", hdd_file
    ]
  end
end
