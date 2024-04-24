# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

##  Program


CLIENT:
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```

SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
TRANCEROUTE COMMAND:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output

CLIENT:


![Screenshot 2024-04-24 205214](https://github.com/pragachellapillai/4.Execution_of_NetworkCommends/assets/148254952/5a2b4417-2e82-4c51-9d46-be7c40e8cec9)


SERVER:

![Screenshot 2024-04-24 205224](https://github.com/pragachellapillai/4.Execution_of_NetworkCommends/assets/148254952/c0416350-a96a-4c24-af10-534774eb8f05)


TRANCEROUTE COMMAND:

![Screenshot 2024-04-24 205237](https://github.com/pragachellapillai/4.Execution_of_NetworkCommends/assets/148254952/a35c016a-312d-47f9-bb0f-6180000ccbee)


## Result
Thus Execution of Network commands Performed 
