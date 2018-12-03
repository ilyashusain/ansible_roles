# ansible_roles

Here we utilize ansible roles to make life easier. In this session, we will attempt to install docker, jenkins, nexus and git on four separate vms, using ansible roles.

To create roles, cd into ```/etc/ansible``` and execute in the shell:

```sudo ansible-galaxy init roles```

This will create a new directory in the current directory called ```roles```. We must execute the above command in ```/etc/ansible``` else ansible will not find the roles.
