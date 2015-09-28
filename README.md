## vagrant-ansible-centos7-lamp
These are Vagrant file to make LAMP environment using Ansible.

## Required tools
Install these tools on your environment.

* Vagrant
* Virtual Box
* Ansible

## How environment can you make with the Vagrantfile.
* CentOS 7
* PHP 5.6
* Apache 2.4
* MariaDB 15.1
* Composer
* Create database * optional

## How can you make the VM enviroment.
Change directory to the layer which have Vagrantfile and Type this command on your console.  
`$ vagrant up `

## Making database.
If you want to make database, please comment out these line in `ansible/roles/mariadb/main.yml` before you run `$ vagrant up ` command.
  
    #- name: mariadb | Create databases
    #  sudo: yes
    #  mysql_db: name={{ database.db }} state=present
    #  with_items: mariadb
    
    #- name: mariadb | Create users
    #  sudo: yes
    #  mysql_user: name={{ database.user }} password={{ database.pass }} priv={{ database.db }}.*:ALL state=present
    #  with_items: mariadb

And please edit databasename, username and password in `ansible/vars/mariadb.yml`
  
    database:
        db: sample_db
        user: sample_user
        pass: sample_pass
  
  