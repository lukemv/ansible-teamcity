## Basic CI/CD Environment for a Start-Up

This repo creates a basic continuous integration environment using Team City. This type of deployment would be suitable for a start-up in the very early stages of prototyping.



**Control Machine Requirements:**

Ansible > 2.2 is required to run the tasks included in this repo. See [Installation Instructions](http://docs.ansible.com/ansible/intro_installation.html) for details.



**Deployment Requirements:**

You will need to provision at least 3 servers. A somewhat beefy computer running 3 virtual machines will suffice, for such a scenario the included `Vagrantfile` might provide some guidance. In a production scenario you would likely use a platform like AWS or GCE.



**Server Summary:**

1. A database server *(used to run postgresql)*
2. A server to run the Team City server on
3. A server to run the Team City agent on

You could run additional Team City agents if you desire.



**Usage Overview:**

1. After building all of your servers, update the `inventory` file with appropriate information to allow ansible to SSH into each. If you're new to ansible you'll find information relating to the inventory file [here](http://docs.ansible.com/ansible/intro_inventory.html#list-of-behavioral-inventory-parameters). As a minimum you will likely need to update:
   1.  The server addresses/hostnames 
   2. The `ansible_user` used to ssh. 
   3. The `ansible_ssh_private_key_file` used to ssh. 
2. Edit `playbook.yml` file adding a new `teamcity_password` and an appropriate `internal_network_cidr` for your network. The chosen password will be assigned to the teamcity database user. You will require this string when setting up the teamcity database via the GUI for the first time *(Note: not used to log in, used to set up the database)*.
3. Run `1.provision_database.sh`
4. Run `2.provision_server.sh`
5. Navigate to the URL of the TeamCity server in your browser e.g. `http://<ipaddress>:8111` and perform the initial set up. When prompted for database information choose `postgresql` as the database engine, use the IP address of your database server and use `teamcity` as the name of the database and use the password that you chose in step 2 above.
6. Once the TeamCity server initial set up is complete; run `3.provision_agent.sh`