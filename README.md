# 2c.SIMULATING ARP /RARP PROTOCOLS
## NAME: KABILAN V
## REGISTER NO: 212222100018
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
## PROGRAM - ARP
## client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
## server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```
## OUPUT - ARP
## client
![306675378-c78526fd-72aa-4148-8720-a434d59bb917](https://github.com/kabilan22000284/2c.ARP_RARP_PROTOCOLS/assets/123469171/12919bbc-97e4-4cba-9a81-fde210dd3361)

## server
![306675524-474cbff5-3e2e-4ba3-b2c0-78f49c1d93e2](https://github.com/kabilan22000284/2c.ARP_RARP_PROTOCOLS/assets/123469171/93d461e0-dad7-4140-be62-3592cf7f95dc)

## PROGRAM - RARP
## client
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
 ip=c.recv(1024).decode()
 try:
   c.send(address[ip].encode())
 except KeyError:
   c.send("Not Found".encode())
```
## server
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
## client
![306676373-3fc4b1a3-600f-4955-8a36-0a6510b73c43](https://github.com/kabilan22000284/2c.ARP_RARP_PROTOCOLS/assets/123469171/e880afd6-374c-46dc-b00d-cfd6e765d731)

## server
![306676522-1f9f139d-7eb5-4a16-bf0e-32b6aa9b867f](https://github.com/kabilan22000284/2c.ARP_RARP_PROTOCOLS/assets/123469171/275dcb9a-c5e3-44ca-a15c-289eea332a6d)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
