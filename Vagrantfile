Vagrant.configure('2') do |config|
  config.vm.provider :digital_ocean do |provider, override|
    provider.image = 'Docker 1.3.2 on 14.04'
    provider.region = 'sfo1'
    provider.size = '512mb'
    provider.ssh_key_name = 'DIGITAL_OCEAN_SSHKEY'
    provider.token = 'DIGITAL_OCEAN_APIKEY'

    override.ssh.private_key_path = '~/.ssh/id_rsa'
    override.vm.box = 'digital_ocean'
    override.vm.box_url = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"
  end

  config.vm.provision :shell, :inline => <<-EOB
    fallocate -l 4G /swapfile
    chmod -v 600 /swapfile
    mkswap /swapfile
    echo '/swapfile none swap sw 0 0' >> /etc/fstab
    swapon -a
    free
  EOB
end
