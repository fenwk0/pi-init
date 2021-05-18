# pi-init
Some scripts to initialise a pi

For more accurate and detailed instructions see: 
- https://www.raspberrypi.org/documentation/configuration/wireless/headless.md
- https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md
- https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent

# Mac Config

#### copy the sup file to the boot disk on SSD
`cp wpa_supplicant.conf /Volumes/boot`

#### add an ssh file to the boot disk on SSD, remember to insert a single space
`vi /Volumes/boot/ssh`

#### Create an ssh key pair for the mac that can also be used for Github 
`ssh-keygen -t ed25519 -C karl.fenwick@gmail.com`

#### this is compatible with Github, use this to copy to clipboard
`pbcopy < ~/.ssh/id_ed25519.pub`

#### set the newly generated key as the Mac's default
`ssh-add -K ~/.ssh/id_ed25519`

#### copy the Mac Public Key to the PI, so the PI can trust it. 
`ssh-copy-id pi@192.168.1.***`

# Raspberry Pi Config
#### update and fix and missing apt dependancies

`sudo apt-get update --fix-missing`

#### Create an ssh key pair for the mac that can also be used for Github 

`ssh-keygen -t ed25519 -C karl.fenwick@gmail.com`


#### set the newly generated key as the PI's default

`eval $(ssh-agent)`

`ssh-add`

#### install git

`sudo apt-get install git`

#### set my git identity

`git config --global user.email "karl.fenwick@gmail.com"`

`git config --global user.name "fenwk0"`

#### try a pull
`git pull`

#### try a push after editing README
`git add .`

`git commit -m="updated README"`

`git push`

### Add Java and check it

`sudo apt-get install openjdk-8-jdk`

`java -version`

`> openjdk version "1.8.0_212"`

`> OpenJDK Runtime Environment (build 1.8.0_212-8u212-b01-1+rpi1-b01)`

`> OpenJDK Client VM (build 25.212-b01, mixed mode)`

### Git Setup

`git config --global user.email "karl.fenwick@gmail.com"`

`git config --global user.name "Karl"`

`git add .`

`git commit -m "first commit"`

`git push -u origin main`