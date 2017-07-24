# Prerequisites
- For Raspberry Pi use Raspbian Jessie Lite and configure hostname and network.
- On remote machine, copy public rsa key :
```
ssh-copy-id -i ~/.ssh/id_rsa.pub pi@hostname
```



# Usage

# On Raspbian
run raspi-config utility to :
- enable SSH server
- change hostname
- activate I2C and SPI buses
