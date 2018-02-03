# HW1 - Configuration Management
## Steps to run
+ Clone the repo.
+ Set up two servers and note the IP addresses.
+ Update the `inventory` file with the IP addresses and create the `private_key` files.
+ Change the permission of both the key files using `chmod 600 keys/node0.key`.
+ Generate the GitHub Token and paste it in `group_vars/all/vars.yml` file. The file is encrypted.
+ Also enter the mysql password and use the command to decrypt and edit the file :

```
ansible-vault edit group_vars/all/vars.yml
```
**password for ansible-vault:** qwerty  

![](https://github.ncsu.edu/pbhanda2/HW1-Configuration-Management/blob/master/token.yml.png)
+ Run the ansible script

```
ansible-playbook -i inventory main.yml --ask-vault-pass
```
## Screencast
+ [Demo](https://youtu.be/E_2X09Q8ozc)
