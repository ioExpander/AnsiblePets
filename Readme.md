# General Usage
You don't really need to create a hosts file to run on a single machine :
```
ansible-playbook <Name>-playbook.yml -i "targethost," [--tags=current]
```
To run on localhost you can run :
```
ansible-playbook <Name>-playbook.yml -i "localhost," -c local [--tags=current]
```

# Usage for Raspbian Jessie

##**BEFORE** connecting the network cable
Run raspi-config utility to :
- set keyboard, timezones and locales
- reboot
- change user pi default password
- enable SSH server
- change hostname
- activate I2C and SPI buses
- overclock if needed
- reboot

##**NOW** Connect network or wifi
1. On remote machine, copy public rsa key :
```
ssh-copy-id -i ~/.ssh/id_rsa.pub pi@hostname
```
2. (optionnal) Add the current machine in your ~/.ssh/config file
3. run chosen playbook

# Usage for desktop Ubuntu or variants

##**Prepare destination machine**
- install openssh-server
- add the following line using sudo visudo :
```
username ALL=(ALL) NOPASSWD:ALL
```

##On control machine
1. (optionnal) Add the destination machine and login in your ~/.ssh/config file
2. Copy ssh key
```
ssh-copy-id -i ~/.ssh/id_rsa.pub username@hostname
```
