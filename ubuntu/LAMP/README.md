# Ubuntu 64 bit 14.04 LAMP stack with Vagrant and docker.

Add this to your ~/.ssh/config file

```
Host lampbox
  HostName 127.0.0.1
  User vagrant
  Port 2222
  UserKnownHostsFile /dev/null
  StrictHostKeyChecking no
  PasswordAuthentication no
  IdentityFile /home/gavin/.vagrant.d/insecure_private_key
  IdentitiesOnly yes
  LogLevel FATAL
```

Start up the vagrant box
```
vagrant up
```

You should be able to ssh into the box without providing a password simply by running

```
ssh lampbox
```

Todo
* Install docker in the lampbox using Ansible.
* Run the dockerfile with Ansible.
* Docker install PHP, MySQL and APACHE.
* Install a test page and view in browser.
