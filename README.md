# EX-6 IMPLEMENTATION OF PING COMMAND
## DATE :13.04.2023
## AIM :
To write the python program for simulating ping command.
## ALGORITHM :
Step 1: start the program.
Step 2: Include necessary package in java.
Step 3: To create a process object p to implement the ping command.
Step 4: declare one Buffered Reader stream class object.
Step 5: Get the details of the server
5:1: length of the IP address.
5:2: time required to get the details.
5:3: send packets, receive packets and lost packets.
5.4: minimum, maximum and average times.
Step 6: print the results. Step 7: Stop the program.
## CLIENT PROGRAM :
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
## SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
## CLIENT OUTPUT :

![241625436-fae4f95b-1f83-471a-a17a-46393c7ad575](https://github.com/Amruthavarshnibs/EX-6/assets/119103704/71e1eecb-1be5-406f-8af9-406df24bad24)

## SERVER OUTPUT :
![241625447-f33480cb-93b3-481a-b016-874dfe9eb821](https://github.com/Amruthavarshnibs/EX-6/assets/119103704/8e35414c-9f30-446d-955c-9b29d53032bb)


## RESULT :
Thus, the python program for simulating ping command was successfully executed.
