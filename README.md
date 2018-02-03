# HW1 - Configuration Management

## Screencast
+ [Demo](https://youtu.be/E_2X09Q8ozc)

## Steps to run

  ### Folder layout:
```
- group_vars/
  - all/
    - vars.yml
- roles/
  - common/
    - tasks/
      - main.yml
  - coffee/
    - tasks/
      - main.yml
    - vars/
      - main.yml
  - selenium/
    - tasks/
      - main.yml
    - vars/
      - main.yml
- main.yml
- inventory
```
+ Clone the repo.
+ Set up two servers (one for CoffeeMaker [Remember to add provision for 2048 Memory] and another for Selenium) and note the IP addresses.
+ Update the [`inventory`](https://github.ncsu.edu/pbhanda2/HW1-Configuration-Management/blob/master/inventory) file with the IP addresses and create the `private_key` files. [Follow](https://github.com/CSC-DevOps/CM/blob/master/Ansible.md).
+ Change the permission of both the key files using `chmod 600 keys/node0.key`.
+ Generate the [GitHub Token](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/) and paste it in `group_vars/all/vars.yml` file. The file is encrypted.
+ Also enter the mysql password and use the command to decrypt and edit the file :

```
ansible-vault edit group_vars/all/vars.yml
```
**password for ansible-vault:** qwerty  

![](https://github.ncsu.edu/pbhanda2/HW1-Configuration-Management/blob/master/Images/token.yml.png)
+ Run the ansible script

```
ansible-playbook -i inventory main.yml --ask-vault-pass
```
+ Head over to the `http://<CoffeeMaker_IPAddress>:8080` to verify the Server is up and running.

## Screenshots
+ **CoffeeMaker**

  ![](https://github.ncsu.edu/pbhanda2/HW1-Configuration-Management/blob/master/Images/CoffeeMaker.gif)

+ **Ansible Script**

  ![](https://github.ncsu.edu/pbhanda2/HW1-Configuration-Management/blob/master/Images/AnsibleScriptRunning.gif)
## Sources
+ [Installing Java 8](https://coderwall.com/p/4ogyuw/ansible-install-java-8)
+ [Installing MySQL 5.7](http://mysql.freeideas.cz/subdom/mysql/2017/07/26/install-latest-mysql-5-7-on-remote-instance-using-ansible/)
+ [Setting Environment](https://docs.ansible.com/ansible/latest/playbooks_environment.html)
+ [Understanding Roles in Ansible](https://docs.ansible.com/ansible/latest/playbooks_best_practices.html)
