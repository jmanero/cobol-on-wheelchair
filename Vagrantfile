# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.hostname = 'devportal-vagrant'
  config.vm.box = 'ubuntu-14.04-provisionerless'
  config.vm.box_url = 'https://cloud-images.ubuntu.com/vagrant/trusty/'\
    'current/trusty-server-cloudimg-amd64-vagrant-disk1.box'


  config.vm.provider :virtualbox do |vb|
    vb.memory = 2048
  end

  config.vm.network :forwarded_port, :guest => 80, :host => 8080
  config.vm.synced_folder './', '/var/www/wheelchair'

  config.vm.provision :shell,
    :inline => 'apt-get update', :privileged => true

  config.vm.provision :shell,
    :inline => 'apt-get install -y apache2 open-cobol', :privileged => true

  config.vm.provision :shell,
    :inline => "cp /var/www/wheelchair/apache.conf /etc/apache2/sites-available/000-default.conf", :privileged => true

  config.vm.provision :shell,
    :inline => 'a2enmod cgid rewrite && service apache2 restart', :privileged => true

  config.vm.provision :shell,
    :inline => 'cd /var/www/wheelchair && ./downhill.sh'
end
