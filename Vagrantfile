Vagrant.configure("2") do |config|

  config.vm.define "controlpanel" do |controlpanel|
    controlpanel.vm.hostname = "control-panel.home.local"
    controlpanel.vm.box = "centos/7"
    controlpanel.vm.box_check_update = false

    controlpanel.vm.network "public_network", ip: "172.16.0.250", netmask: "255.255.0.0", bridge: "en0: Wi-Fi (AirPort)"

    controlpanel.vm.provision :ansible do |ansible|
      ansible.playbook = "control-panel.yml"
    end

    controlpanel.vm.provider "virtualbox" do |vm|
      vm.cpus = "2"
      vm.memory = "512"
      vm.gui = true
    end
  end
end