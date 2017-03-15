# Setup guide
This guide contains all steps to setup my personal H/2 webserver. This is basically a step-by-step checklist of how to set up my personal web server on a Raspberry-Pi 3 Model B in case of a crash.

## Raspberry-Pi Setup
* Download the Ubunutu 16.04 image from: https://ubuntu-pi-flavour-maker.org/download/
* Extract the xz package (xz needs to installed via brew) ```unxz ubuntu-16.04-preinstalled-server-armhf+raspi3.img.xz```
* Add the sc cards drive to the Mac and use Apple PiBaker to copy the image to sd card (https://www.tweaking4all.com/software/macosx-software/macosx-apple-pi-baker/)
* The preprovisioned user is ubuntu/ubuntu
* Login to the via ssh in order to change the password

### Network setup
* Find the pi on the network throgth the GUI of the router and bind a static ip address via DHCP to the pi's mac address 

### SSH Setup ###
* Add ip address and ubuntu user name to ~/.ssh/config 
* Copy the ssh key to the authorized_key list of the pi ```ssh-copy-id <host>``` (install ssh-copy-id with brew)

### Ansible Setup ###
* Inventory file for a brew install ansible is located under ```/usr/local/etc/ansible/hosts```
* Run the desired playbooks with ```ansible-playbook -i hosts up.yml```