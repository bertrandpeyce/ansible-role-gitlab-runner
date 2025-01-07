
Vagrant.configure("2") do |config|
  config.vm.define "test" do |runner|
    runner.vm.box = "generic/ubuntu2204"
    runner.vm.hostname = "test-runner"
    runner.vm.network "private_network", type: "dhcp"

    runner.vm.provider :libvirt do |libvirt|
      libvirt.cpus = 1
      libvirt.memory =  1024
      libvirt.driver = "kvm"
    end

    runner.vm.provision "ansible" do |ansible|
      ansible.playbook = "tests/test.yml.ansible"
      #ansible.verbose = "vvvv"
      ansible.compatibility_mode = "2.0"
    end
  end
end
