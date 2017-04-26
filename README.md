# CIS for Centos 6

## 说明

1. Centos 6安全加固，编写playbook时测试的操作系统是Centos 6.8，其他Centos6版本的操作系统未测试，但应该好用。  
2. 执行过程中会自动设置root和centos用户的密码，密码设置参见***变量说明***章节。
3. 这个playbook是参见github上[cis-rhel-ansible](https://github.com/major/cis-rhel-ansible.git)

![http://media.giphy.com/media/7U1XfwZ94okRW/giphy.gif](http://media.giphy.com/media/7U1XfwZ94okRW/giphy.gif)

## 版本  

Aansible：2.3

## 使用

1. 编辑hosts文件，修改ansible_ssh_host、ansible_ssh_user  
2. 编辑group_vars/all，设置变量。 
3. 运行playbook。
```
ansible-playbook -i hosts site.yml -k
SSH password:   # 输入ansible_ssh_user密码
```

## 变量说明

modify_root_password: True  # 如果设置为```True```，就会修改操作系统密码。密码为```root_password```设置的值。
root_password:  # 设置root用户密码。
root_password_grub  # grub 密码。
centos_password:  # Centos 用户密码。
