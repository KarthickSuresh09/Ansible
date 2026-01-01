ansible --inventory /etc/ansible/hosts myhosts -m ping

It will list all hosts servers and check the SSH connectivity, Authentication
```
ansible all -m ping
```

Simply prints the list of hosts Ansible would target
```
ansible all --list-hosts
```
ansible all -m shell -a "ls -altr" //list all files on hosts
ansible myhosts[1] -m shell -a "touch newfile" // create file in server at 1st index
ansible all -m shell -a "apt install git" //permission denied since no sudo used
ansible all -m shell -a "sudo apt install git" //will work since we have used sudo
ansible all -m shell -a "apt install git" -b //will work since we have used -b ie become sudo
ansible all -m copy -a "src=hellofile dest=/home/sysops"
ansible all -m apt -a "name=apache2 state=present" -b
ansible all -m service -a "name=apache2 state=stopped" -b
ansible all -m shell -a "free -m"

to create a user in paticualr host like dbservers
```
ansible -m user -a "name=katzy password=1234" dbservers
```
