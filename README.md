# My Home Server

## Overview
My Home server is used to:
* Run a small NAS, 
* Run pihole with the default lighttpd,
* Run our local web server
* Run a web proxy

## Details
This ansible playbook sets all this up.

* cloud-device.yaml - defines the USB SSD used for NAS storage
* cloud-firewall.yaml - Installs and performs basic firewall configuration
* cloud-smb.yaml - Configure the SMB server
* pihole.yaml - Install and configure pihole
* photos.yaml - Install the Single File Photo Gallery (SFPG) software
* webserver.yaml - Modify the lighttpd web server installed with pihole to server our local files and SFPG
* webproxy.yaml - Install and configure a web proxy just in case :)

## Pre-requisistes
*TO DO*

## Considerations
In order to allo access the encrypted samba password, run as follows:

ansible-playbook -e @group_vars/home_servers/secrets.enc --ask-vault-pass site.yaml

ansible-playbook -e @group_vars/home_servers/secrets.enc --ask-vault-pass cloud-smb.yaml