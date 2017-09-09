# Prerequisites
- For Raspberry Pi use Raspbian Jessie Lite and configure hostname and network.




# Usage for Raspbian Jessie

##**BEFORE connecting the network cable**
Run raspi-config utility to :
- set keyboard, timezones and locales
- reboot
- change user pi default password
- enable SSH server
- change hostname
- activate I2C and SPI buses
- overclock if needed
- reboot

##**NOW Connect network or wifi**
1. On remote machine, copy public rsa key :
```
ssh-copy-id -i ~/.ssh/id_rsa.pub pi@hostname
```
2. (optionnal) Add the current machine in your ~/.ssh/config file
3. create the appropriate hostfile and run ansible :
```
ansible-playbook <Name>-playbook.yml -i ansible_hosts [--tags=current]
```
