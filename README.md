Docker on DigitalOcean by Vagrant
=================================

`vagrant-digitalocean-docker` contains a Vagrant file for running Docker on DigitalOcean.

Features:

* Docker on Ubuntu
* Enable swap


Prepare
-------

Sign up [DigitalOcean](https://www.digitalocean.com/?refcode=05617a2b5246).

Install [Vagrant](https://www.vagrantup.com).

Install [Digital Ocean Vagrant Provider](https://github.com/smdahlen/vagrant-digitalocean) as following.

```sh
vagrant plugin install vagrant-digitalocean
```


Run
---

After setting up your `Vagrantfile` with SSH key name and DigitalOcean API key,
you may create an new droplet as follows:

```sh
vagrant up --provider=digital_ocean --provision
vagrant ssh
```

