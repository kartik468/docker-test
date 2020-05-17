give permission to folder
$ sudo chmod -R 777 test-input

to check permission
$ ls -la


list groups
$ groups

list users 
$ cut -d: -f1 /etc/passwd


extract tar file
$ tar -xvf abc.tar



## Linux: List all members of a group using /etc/group file
Use the grep command as follows:

```
$ grep 'grpup-name-here' /etc/group
$ grep 'ftponly' /etc/group
$ grep -i --color 'ftponly' /etc/group

Sample outputs:

ftponly:x:1001:raj,vivek,archana,sai,sayali
To get just a list of all members of a group called ftponly, type:

awk -F':' '/ftponly/{print $4}' /etc/group
```

## Display group memberships for each user
The syntax is as follows for the groups command:

```
groups
groups vivek
```