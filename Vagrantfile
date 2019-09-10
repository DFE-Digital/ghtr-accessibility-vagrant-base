Vagrant.configure("2") do |config|
  config.vm.box = "Microsoft/EdgeOnWindows10"
  config.vm.box_version = "1.0"
  config.vm.guest = :windows
  config.ssh.password = "ENV['VAGRANT_PASS']"
  config.ssh.username = "IEUser"
  config.ssh.insert_key = false
  config.vm.network "forwarded_port", guest: 3389, host: 3389
  config.vm.provision "shell", path: "scripts/provision.ps1", privileged: true
end
