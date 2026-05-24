# 4.Execution_of_NetworkCommands
## AIM :
Use of Network commands in Real Time environment
## Software : 
Command Prompt And Network Protocol Analyzer
## Procedure: 
To do this EXPERIMENT- follows these steps:
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
## Program:
**server**
```python
import socket
from pythonping import ping

s = socket.socket()

s.bind(('localhost', 8000))

s.listen(5)

print("Server waiting...")

c, addr = s.accept()

print("Connected with", addr)

while True:
    hostname = c.recv(1024).decode()

    try:
        result = ping(hostname, verbose=False)
        c.send(str(result).encode())

    except:
        c.send("Not Found".encode())
```
**client**
```python
import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:
    ip = input("Enter the website you want to ping: ")

    s.send(ip.encode())

    print(s.recv(1024).decode())
```
## Output
**server side**

<img width="720" height="393" alt="{0ABAE3B5-8B1B-4B7E-8402-9ABEDC9E231D}" src="https://github.com/user-attachments/assets/42c49a9e-8ca1-4560-9a27-723ab6ba1161" />

**client side**

<img width="784" height="654" alt="{62680390-FA13-4D0A-84F9-AEE5F83A8001}" src="https://github.com/user-attachments/assets/b6537969-6320-4612-8ed9-fda2aeacf8c4" />

## Result
Thus Execution of Network commands Performed .
