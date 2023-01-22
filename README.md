# DEPLOYCCASH
# Ansible

CCash can be deployed to any infrastructure able to run Rocky/Alma Linux 8/9 x86_64 virtual or not, we will be eventually updating it to allow it to run on other OS's but for now RHEL is what works.

As CCash is intended to be run as root, the playbook is run also as root. The playbook also builds CCash from the latest github push, so there may be bugs.

In order to use the ansible playbook, clone the playbook to any pc with the ability to access the server through SSH and with Ansible installed, edit the inventory file to contain the IP address of the target server and run the following commands:
```git clone https://github.com/Expand-sys/DEPLOYCCASH```
```cd DEPLOYCCASH```
```ansible-playbook -i inventory main.ansible.yml -k```
When this is complete the server will have ccash installed to the user dir, this is customizable in the vars/default.yml file along with the admin username and save frequency.
To start CCash you can CD into the directory CCash is installed then run ./build/bank {ADMIN ACCOUNT} {SAVE FREQUENCY} true
replacing {ADMIN ACCOUNT} with your admin account username and {SAVE FREQUENCY} with the amount of minutes you want to wait for the bank to autosave.
true just means that the server will be run in daemon mode and will run as a background process

