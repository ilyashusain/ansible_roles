# ansible_roles

Here we utilize ansible roles to make life easier. In this session, we will attempt to install docker, jenkins, nexus and git on four separate vms, using ansible roles.

To create roles, cd into ```/etc/ansible``` and execute in the shell:

```sudo ansible-galaxy init roles```

This will create a new directory in the current directory called ```roles```. We must execute the above command in ```/etc/ansible``` else ansible will not find the roles. Now ```cd``` into ```roles``` and run:

```sudo ansible-galaxy init docker```

```sudo ansible-galaxy init jenkins```

```sudo ansible-galaxy init nexus```

```sudo ansible-galaxy init git```

These will be our roles, installing the specified programs on to our desired vms. Let us install docker first. ```cd``` into docker and then ```cd``` into tasks, here we will find a ```main.yml``` file. Do not worry about this now. Now, in this ```tasks``` directory run ```sudo vim docker.yml```, this will create a .yml file where the script for docker installation goes. To see this script, refer to: https://github.com/ilyashusain/ansible/blob/master/git.yml. Copy everything in the docker portion of the script excluding ```tasks``` and ```hosts```, so:

```
  - name: Set-up docker
    yum:
      name: docker
      state: latest
    become: true
```

Next, vim the main.yml file as such:

```
---
- import_tasks: docker.yml

```

This will call the docker.yml file we just created. Do this for the jenkins, nexus and git roles. Refer to the above referenced repo for the scripts.

Now we are ready to run ```ansibleRoles.yml```, whereafter the installations will occur without issue.
