# pi-init
Some scripts to initialise a pi

See https://www.raspberrypi.org/documentation/configuration/wireless/headless.md

## Notes for Mac

`cp wpa_supplicant.conf /Volumes/boot`

`vi /Volumes/boot/ssh`

`cat ~/.ssh/id_rsa.pub | ssh pi@192.168.1.190 'mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys'`
`ssh-add -K ~/.ssh/id_rsa`
