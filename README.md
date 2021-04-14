# pi-init
Some scripts to initialise a pi

See https://www.raspberrypi.org/documentation/configuration/wireless/headless.md

## Notes for Mac

### copy the sup file to the boot disk on SSD
`cp wpa_supplicant.conf /Volumes/boot`

### add an ssh file to the boot disk on SSD, remember to insert a single space
`vi /Volumes/boot/ssh`

### create an ssh key pair for the mac, this is compatible with Github
`ssh-keygen -t ed25519 -C karl.fenwick@gmail.com`

### set the newly generated key as the Mac's default
`ssh-add -K ~/.ssh/id_rsa`

### copy the Mac Public Key to the PI, so the PI can trust it. 
`cat ~/.ssh/id_rsa.pub | ssh pi@192.168.1.*** 'mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys'`

