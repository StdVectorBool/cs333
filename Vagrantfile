Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.cpus = 2
    vb.memory = 2048
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y xfce4 slim qemu gdb openjdk-11-jdk-headless
    curl -s https://web.cecs.pdx.edu/~markem/CS333/xv6/xv6-pdx.tar | tar x
    curl -s http://ftp.osuosl.org/pub/eclipse/technology/epp/downloads/release/2019-03/R/eclipse-cpp-2019-03-R-linux-gtk-x86_64.tar.gz | tar xz
    echo "add-auto-load-safe-path /home/vagrant/xv6-pdx/.gdbinit" > /home/vagrant/.gdbinit
    chown -R vagrant:vagrant eclipse xv6-pdx .gdbinit
  SHELL
end
