Vagrant.configure('2') do |config|

  config.vm.provider :digital_ocean do |provider, override|
    provider.image = 'ubuntu-15-04-x64'
    provider.region = 'ams2'
    provider.size = '512mb'

    override.ssh.private_key_path = '~/.ssh/id_rsa'
    override.vm.hostname = 'frf-backup'
    override.vm.box = 'digital_ocean'
    override.vm.box_url = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"

    override.vm.provision "shell", inline: "apt-get update -y"
    override.vm.provision "shell", inline: "apt-get install -y python-pip python-dev"
    override.vm.provision "shell", inline: "pip install --upgrade pip"
    override.vm.provision "shell", inline: "pip install ansible"
    override.vm.provision "shell", inline: "ansible-playbook -i /vagrant/hosts --connection=local /vagrant/playbook.yml"
  end
end