# Vagrantfile for Docker on DigitalOcean

Dotenv.load
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'digital_ocean'

Vagrant.configure('2') do |config|
  config.vm.provider :digital_ocean do |provider, override|
    provider.image = 'docker'
    provider.region = 'sfo1'
    provider.size = '512mb'
    provider.ssh_key_name = ENV['DIGITALOCEAN_SSH_KEY_NAME']
    provider.token = ENV['DIGITALOCEAN_API_KEY']

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
