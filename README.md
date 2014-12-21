Docker on DigitalOcean by Vagrant
=================================

`vagrant-digitalocean-docker` contains a Vagrant file for running Docker on DigitalOcean.

Features:

* Docker on Ubuntu
* Enable swap


Prepare
-------

Sign up [DigitalOcean](https://www.digitalocean.com/?refcode=05617a2b5246) and get your API key.

Install [Vagrant](https://www.vagrantup.com).

Install [Digital Ocean Vagrant Provider](https://github.com/smdahlen/vagrant-digitalocean) and [Vagrant Dotenv](https://github.com/johnbellone/vagrant-dotenv).

```sh
vagrant plugin install vagrant-digitalocean
vagrant plugin install vagrant-dotenv
```

Check out the project and set up `.env` file.

```sh
git clone https://github.com/int128/vagrant-digitalocean-docker.git
cd vagrant-digitalocean-docker
echo "DIGITALOCEAN_SSH_KEY_NAME='my'" >> .env
echo "DIGITALOCEAN_API_KEY='xxxxxxxx'" >> .env
```


Run
---

Create an new droplet as follows:

```sh
vagrant up
vagrant ssh
```

Destroy the droplet as follows:

```sh
vagrant destroy
```

