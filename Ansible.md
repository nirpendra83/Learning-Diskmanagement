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

# 20 Ansible Ad-Hoc Commands

## 1. Ping All Servers

```bash
ansible all -m ping
```

## 2. Check Hostname

```bash
ansible all -m command -a "hostname"
```

## 3. Check Uptime

```bash
ansible all -m command -a "uptime"
```

## 4. Check Current Date

```bash
ansible all -m command -a "date"
```

## 5. Check Disk Space

```bash
ansible all -m command -a "df -h"
```

## 6. Check Memory

```bash
ansible all -m command -a "free -h"
```

## 7. Check Operating System

```bash
ansible all -m setup -a "filter=ansible_distribution*"
```

## 8. Create a Directory

```bash
ansible all -m file -a "path=/tmp/mydir state=directory"
```

## 9. Create a File

```bash
ansible all -m file -a "path=/tmp/test.txt state=touch"
```

## 10. Delete a File

```bash
ansible all -m file -a "path=/tmp/test.txt state=absent"
```

## 11. Copy a File

```bash
ansible all -m copy -a "src=hello.txt dest=/tmp/hello.txt"
```

## 12. Write Content to a File

```bash
ansible all -m copy -a "content='Hello Ansible' dest=/tmp/hello.txt"
```

## 13. Change File Permission

```bash
ansible all -m file -a "path=/tmp/hello.txt mode=0644"
```

## 14. Create a User

```bash
ansible all -m user -a "name=testuser state=present"
```

## 15. Delete a User

```bash
ansible all -m user -a "name=testuser state=absent"
```

## 16. Create a Group

```bash
ansible all -m group -a "name=testgroup state=present"
```

## 17. Install Git

```bash
ansible all -b -m apt -a "name=git state=present"
```

## 18. Install Nginx

```bash
ansible all -b -m apt -a "name=nginx state=present"
```

## 19. Start Nginx

```bash
ansible all -b -m service -a "name=nginx state=started"
```

## 20. Restart Nginx

```bash
ansible all -b -m service -a "name=nginx state=restarted"
```

---

# Common Options

| Option | Meaning |
|---|---|
| `all` | Run command on all hosts |
| `-m` | Specify Ansible module |
| `-a` | Specify module arguments |
| `-b` | Use sudo/root privileges |
| `-i` | Specify inventory file |

# Examples

## Using an Inventory File

```bash
ansible all -i inventory -m ping
```

## Run on a Specific Group

```bash
ansible webservers -m ping
```

## Run with Sudo

```bash
ansible all -b -m command -a "whoami"
```

## Check a Specific Host

```bash
ansible server1 -m ping
```
