# local-ansible
Ansible files to install RootIO client on a debian machine (Small tweaks should make this work for more Linux distros). 

To install the RootIO client on a debian machine, first install and enable an SSH server e.g OpenSSH, and a 1.8+ JDK

1) Clone this 

```
git clone https://github.com/rootio/local-ansible.git
```

2) cd into the directory

``` 
cd local-ansible
```

3) customise variables in the vars/rootio_vars.yml file to your taste

4) Define target hosts in the hosts.yml file

5) Install MySQL server

```
ansible-playbook -i hosts.yml -u <ssh_username> -k deploy-mysql.yml
```

6) Install other components

```
ansible-playbook -i hosts.yml -u <ssh_username> -k install-components.yml
```

7) Install the rootio app

```
ansible-playbook -i hosts.yml -u <ssh_username> -k rootio-components.yml
