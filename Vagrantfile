Vagrant.require_version '>=1.6.0'

Vagrant.configure("2") do |config|
    config.vm.box = "centos/7"

    config.vm.define :develop do |develop|
        develop.vm.hostname = 'develop'
        develop.ssh.forward_agent = true
        develop.vm.provider :virtualbox do |vb|
            vb.customize ['modifyvm', :id, '--memory', '1024', '--cpus', '1', '--ioapic', 'on']
        end
    end

    # Run Ansible from the Vagrant VM
    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook.yml"
    end
end

