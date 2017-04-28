# BESS APLOMB

Documentation on how to replicate [APLOMB](http://people.eecs.berkeley.edu/~justine/fp150-sherry.pdf) architecture with [BESS](https://github.com/NetSys/bess)

## Files
| Files         | Usage                  |
| ------------- |:----------------------:|
| Vagrantfile   | Vagrant VM config file |
| dev.yml       | Ansible Playbook file  |

## Set up
1. Install Vagrant
2. Install VirtualBox

## Building
3. clone this repository

	```
	git clone https://github.com/c2tonyc2/bess_aplomb.git
	```

4. Inspect the Vagrantfile and confirm that it is properly configured for the environment.
	*Bring up public network with a static IP that is publicly routable on the network
5. Boot and SSH into the vagrant machine
	*`vagrant up`
	*`vagrant ssh`
6. Install ansible
	*`sudo apt-get install ansible`
7. Change to the playbook directory
	*`cd /vagrant/`
8. Run the playbook
	*`ansible-playbook dev.yml`
9. Build BESS
	*`~/bess/build.py`
10. Start BESS daemon
	*`~/bess/bessctl/bessctl`
11. Run Port script
	*`daemon run <Script_Path>`
12. Install OpenVPN
	* Follow procedure documented [here](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-16-04#step-7-configure-the-openvpn-service)
	* If setting up a bridge between a BESS VPort and the OpenVPN interface you will need to setup a tap interface for ethernet bridging following procedures documented [here](https://openvpn.net/index.php/open-source/documentation/miscellaneous/76-ethernet-bridging.html)

Bugs or suggestions please send me a message at <c2tonyc2@berkeley.edu>.