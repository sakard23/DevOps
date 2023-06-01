- how to sudo-login into the root:
  - sudo su OR sudo -s :
    - non-login shell
    - sets HOME dir to /root
  - sudo -i OR sudo su -l :
    - login shell
    - sets HOME dir to /root

- to ssh: ```ssh username@host/port/IPaddress```

- to add user, login to root account and then type: ```useradd sakard```
- to create a group, login to root account and then type: ```groupadd AWSCloudGroup```
- to give user access to administrator level to control access to su command, use 'wheel': ```usermod -g wheel sakard```
- to see what groups user is in: ```id sakard```
- to add users into group: ```usermod -aG AWSCloudGroup sakard```
- to lock user account: ```usermod -L sakard```

- to create elevated/sudo user: ```sudo useradd -m sakard```
- to create sudo user and assign 'wheel': ```sudo useradd -G wheel -m drkas```
- to create password for new sudo user: ```sudo passwd sakard```
- to verify the /etc/sudoers file will allow the wheel group access to run all cmds with sudo: ```sudo visudo```
  NOTE: There should not be comment(#) on this line of file:
    - %wheel  ALL=(ALL)       ALL
- to switch to another sudo user use (-) dash: ```sudo su - drkas```
- to verify you can read the /etc/shadow file form this user: ```cat /etc/shadow```
  - again rerun the commands with sudo: ```sudo cat /etc/shadow```
  - after verifying new user can read /etc/shadow file, exit out: ```exit``
