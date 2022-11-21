# This playbook contains all necessary code to deploy a laravel app on AWS

This code is tested on the AWS ubuntu machine.

### This code covers installation of
+ PHP 8.0
+ APACHE
+ postgresQL
+ COMPOSER
+ CERTBOT
+ postgresQL (**NOTE** :Bash script is saved in template directory)


### Requirements
  - Anisble package installed on local machine or Host server.
  - EC2 Ubuntu Instance on AWS 
  - All variables are declared under **/group_vars/all.yaml**

### Prerequistie
  - Basis knowledge of AWS cloud instance. 
  - Generate the public key for the user ubuntu using `ssh-keygen` on local machine
  - Copy the `id_rsa.pub` from `cd ~./ssh` and paste it on the Server cloud using `sudo nano ~/.ssh/authorized_keys`
  + You can use the priavte key and run this playbook which will automatically copy the public key on the target hosts

### How to use Private key directly

- Copy the private key on the ansible server

```
chmod 600 mykey.pem
scp -r -i /Users/home/Documents/devops4solutions/AWS/mykey.pem /Users/home/Documents/laravelrepo/AWS/mykey.pem ubuntu@18.219.xxx.xxx:~/.

```
  
### How to run playbook with AWS private key

```
cd Ansible-playbook
```
+ then run this code 
```
ansible-playbook main.yml -i inventories/dev/hosts --user ubuntu --key-file /home/download/mykey.pem

```

#

### Access the application

Make sure security group of AWS EC2 Server is open for port 80.

+ open a browser and paste server pulic ip / Domain name.

```
curl http://publicip

```
