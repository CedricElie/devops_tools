# DevOps Tools install
This is just a basic repo to automate some basic devops tools install on a new RHEL/CentOS/Fedora Host

## Jenkins
This was done using the steps presented on jenkins official documentation

> https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos

```
- name: "Install Jenkins on a RedHat/CentOS/Fedora Host"
  become: True
  hosts: "{{ nodes | default('tools') }}"  #Because I have a node called tools
  tasks:
    - name: "Put SELinux in permissive mode" #Not a good practice
      selinux:
        policy: targeted
        state: permissive
```

## SonarQube

> upcomming: https://www.fosstechnix.com/how-to-install-sonarqube-on-centos-8/