# Ubuntu 64 bit 14.04 LAMP stack with Vagrant and docker.

## Preparation

### Some python tools
```
sudo apt-get install python-setuptools
sudo easy_install pip
```

### Ansible
I use the devel branch of ansible. [And I follow this guide to install](http://docs.ansible.com/intro_installation.html#running-from-source)

### SSH key

Yes, vagrant comes with an insecure SSH key you can use with 'vagrant up'.

I don't care. I want my own in there and then ansible can use it to run outside of the Vagrantfile
provisioner workflow.

Create the ssh key we will use to talk to the vagrant box. Do not add a password.

```
ssh-keygen -t rsa -C "devboxes"
```

## Setup the vagrant box

Start up the vagrant box

```
vagrant up
```

You should be able to ssh into the box without providing a password simply by running

```
ssh vagrant@192.168.33.10
```

The first time you log in it will ask you to save the key. If you have already done this and
destroyed the box and are unable to login this time around you may need to remove the key from your
known hosts.

```
ssh-keygen -f "/home/YOUR_USERNAME/.ssh/known_hosts" -R 192.168.33.10
```

## Provisioning your machine with docker

You will need docker-py
```
pip install docker-py
```

```
ansible-playbook -i hosts playbook.yml
```

Todo
* Run the dockerfile with Ansible.
* Docker install PHP, MySQL and APACHE.
* Docker install a test page and view in browser.
