# Ansible A Automation Tool
-  It works with SSH
-  Ansible controller has ansible package

-  [ ] Create a vm
-  [ ] Create SSH password less connectivity
    -  [ ]  Generate a ssh key
         ```sh
        ssh-keygen
        ```
- [ ] Copy ssh key to trget server
```sh
ssh-copy-id root@192.168.1.19
```

- [ ] Install Ansible
```sh
apt install ansible
yum install ansible
```
- [ ] Generate an Ansible config file
```sh
ansible-config init --disabled > ansible.cfg
```
- [ ] How to list all hosts
```sh
 ansible all --list-host
 ansible all -m shell -a "uptime && free -m"
```
