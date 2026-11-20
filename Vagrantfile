
# Лабораторна робота №8
# Варіант 16 — Debian 12

Vagrant.configure("2") do |config|
  config.vm.box = "generic/debian12"

  config.vm.hostname = "lab8-vm"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.synced_folder ".", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "lab8-vm"
    vb.memory = 1024
    vb.cpus = 1
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y nginx
    systemctl enable --now nginx
  SHELL
end
