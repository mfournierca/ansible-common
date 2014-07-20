#README

##What is this? 

This directory is an ansible project containing common code / plays / tasks / etc used for setting up webservers. 

Playbooks / tasks for configuring servers, installing blog software, etc are found here. 

The point of this is that we want to be able to set up our different websites on different servers, or the same server, or any combination, while not duplicating code. Therefore the common server setup, software installation, etc code is found here so that all sites may use it. 

Also, since this is common code, there are no ansible inventory files in this directory. This directory is designed to be used across different projects / hosts / inventories, so it contains no explicit information about any hosts. 

The directory structure follows that laid out in the [ansible documentation](http://www.ansibleworks.com/docs/playbooks_roles.html). Please read that documentation before using this project. 

##Running Ansible

Before running ansible, you must add some paths to the PYTHONPATH and PATH environment variables, and set the ansible inventory file in the ANSIBLE_HOSTS environment variable. 

In a shell, type:

	PYTHONPATH=$PYTHONPATH:<path to ansible install folder>/lib
	PATH=$PATH:<path to ansible install folder>/bin
	ANSIBLE_LIBRARY=<path to ansible install folder>/library
	MANPATH=<path to ansible install folder>/docs/man

If you don't want set the inventory manuall or use the `-i` option when running ansible, you can also set the ANSIBLE_HOSTS file:

	export ANSIBLE_HOSTS=<path to your inventory file>

The above steps should also be accomplished by running `<path to ansible install folder>/hacking/env-setup` but that doesn't always work, for some reason. 

The above steps can also be done in the shell .profile. They might be already, in fact. Maybe you should check. 

Finally, don't forget to use the -K option when running ansible-playbook so you can provide the sudo password when necessary. 