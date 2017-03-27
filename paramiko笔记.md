```
>>>import paramiko
>>>ssh=paramiko.SSHClient()
>>>ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())
>>>ssh.connect('172.16.1.181',22,'root','admin1234')
>>>a,b,c=ssh.exec_command('pwd')
>>>d=b.read()
>>>print d
/root
```