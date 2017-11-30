Vagrant.configure("2") do |config|

  config.vm.define "pxe" do |pxe|
    pxe.vm.hostname = "control-panel.home.local"
    pxe.vm.box = "centos/7"
    pxe.vm.box_check_update = false

    pxe.vm.network "public_network", ip: "172.16.0.253", netmask: "255.255.0.0", bridge: "en0: Wi-Fi (AirPort)"

    pxe.vm.provision :ansible do |ansible|
      ansible.playbook = "provision.yml"
    end

    pxe.vm.provider "virtualbox" do |vm|
      vm.cpus = "1"
      vm.memory = "256"
      vm.gui = true
    end
  end
end