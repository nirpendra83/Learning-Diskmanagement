###
```yaml
- name: Copy file at a specific time
  hosts: all
  become: true

  tasks:
    - name: Get current time
      ansible.builtin.command: date +%H:%M
      register: current_time
      changed_when: false

    - name: Copy file at 3 PM
      ansible.builtin.copy:
        src: hello.txt
        dest: /tmp/hello.txt
      when: current_time.stdout == "15:00"
```

```sh
- name: Run 10 tasks at the same time
  hosts: all
  become: true

  tasks:

    - name: 1. Ping server
      ansible.builtin.ping:

    - name: 2. Create directory
      ansible.builtin.file:
        path: /tmp/mydir
        state: directory

    - name: 3. Create file
      ansible.builtin.file:
        path: /tmp/hello.txt
        state: touch

    - name: 4. Write text to file
      ansible.builtin.copy:
        content: "Hello from Ansible!"
        dest: /tmp/hello.txt

    - name: 5. Install nginx
      ansible.builtin.apt:
        name: nginx
        state: present
        update_cache: true

    - name: 6. Start nginx
      ansible.builtin.service:
        name: nginx
        state: started

    - name: 7. Create user
      ansible.builtin.user:
        name: john
        state: present

    - name: 8. Copy a file
      ansible.builtin.copy:
        src: hello.txt
        dest: /tmp/copied-hello.txt

    - name: 9. Run date command
      ansible.builtin.command: date
      register: current_date
      changed_when: false

    - name: 10. Delete file
      ansible.builtin.file:
        path: /tmp/hello.txt
        state: absent
```




---
- name: Beginner Ansible Practice - 30 Tasks
  hosts: all
  become: true

  tasks:

    # 1
    - name: 1. Ping server
      ansible.builtin.ping:

    # 2
    - name: 2. Create directory
      ansible.builtin.file:
        path: /tmp/ansible
        state: directory

    # 3
    - name: 3. Create file
      ansible.builtin.file:
        path: /tmp/ansible/test.txt
        state: touch

    # 4
    - name: 4. Write text to file
      ansible.builtin.copy:
        content: "Hello from Ansible"
        dest: /tmp/ansible/test.txt

    # 5
    - name: 5. Create another directory
      ansible.builtin.file:
        path: /tmp/ansible/data
        state: directory

    # 6
    - name: 6. Create user
      ansible.builtin.user:
        name: testuser
        state: present

    # 7
    - name: 7. Create group
      ansible.builtin.group:
        name: testgroup
        state: present

    # 8
    - name: 8. Install Git
      ansible.builtin.apt:
        name: git
        state: present

    # 9
    - name: 9. Install Curl
      ansible.builtin.apt:
        name: curl
        state: present

    # 10
    - name: 10. Install Nginx
      ansible.builtin.apt:
        name: nginx
        state: present

    # 11
    - name: 11. Start Nginx
      ansible.builtin.service:
        name: nginx
        state: started

    # 12
    - name: 12. Enable Nginx
      ansible.builtin.service:
        name: nginx
        enabled: true

    # 13
    - name: 13. Create HTML page
      ansible.builtin.copy:
        content: |
          <html>
          <body>
          <h1>Hello Ansible</h1>
          </body>
          </html>
        dest: /var/www/html/index.html

    # 14
    - name: 14. Copy file
      ansible.builtin.copy:
        src: test.txt
        dest: /tmp/ansible/test-copy.txt

    # 15
    - name: 15. Change file permissions
      ansible.builtin.file:
        path: /tmp/ansible/test.txt
        mode: '0644'

    # 16
    - name: 16. Change file owner
      ansible.builtin.file:
        path: /tmp/ansible/test.txt
        owner: testuser

    # 17
    - name: 17. Run hostname command
      ansible.builtin.command: hostname
      register: hostname_output
      changed_when: false

    # 18
    - name: 18. Show hostname
      ansible.builtin.debug:
        var: hostname_output.stdout

    # 19
    - name: 19. Check disk space
      ansible.builtin.command: df -h
      register: disk_space
      changed_when: false

    # 20
    - name: 20. Show disk space
      ansible.builtin.debug:
        var: disk_space.stdout

    # 21
    - name: 21. Check memory
      ansible.builtin.command: free -h
      register: memory
      changed_when: false

    # 22
    - name: 22. Show memory
      ansible.builtin.debug:
        var: memory.stdout

    # 23
    - name: 23. Create log file
      ansible.builtin.file:
        path: /tmp/ansible/app.log
        state: touch

    # 24
    - name: 24. Add log message
      ansible.builtin.lineinfile:
        path: /tmp/ansible/app.log
        line: "Ansible task completed"

    # 25
    - name: 25. Create configuration file
      ansible.builtin.copy:
        content: |
          APP_NAME=MyApp
          ENVIRONMENT=TEST
        dest: /tmp/ansible/app.conf

    # 26
    - name: 26. Check operating system
      ansible.builtin.debug:
        var: ansible_distribution

    # 27
    - name: 27. Check IP address
      ansible.builtin.debug:
        var: ansible_default_ipv4.address

    # 28
    - name: 28. Restart Nginx
      ansible.builtin.service:
        name: nginx
        state: restarted

    # 29
    - name: 29. Remove temporary file
      ansible.builtin.file:
        path: /tmp/ansible/test-copy.txt
        state: absent

    # 30
    - name: 30. Show completion message
      ansible.builtin.debug:
        msg: "All 30 Ansible tasks completed successfully!"
