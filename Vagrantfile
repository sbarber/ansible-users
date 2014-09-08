# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Setup vagrant-cachier if we have it
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end

  config.vm.define 'example' do |node|
    node.vm.box = "chef/ubuntu-14.04"
    node.vm.hostname = 'example'

    # vmware fusion ;)
    node.vm.provider :vmware_fusion do |v|
      v.vmx['displayName'] = "example"
      v.vmx['memsize']     = 512
      v.vmx['numvcpus']    = 2
    end

    node.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbooks/example.yml"
      #ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
      ansible.sudo = true
      ansible.verbose = 'v'
    end
  end


end
