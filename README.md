# 2c.SIMULATING ARP /RARP PROTOCOLS
## NAME : Nithish R

## Reg NO : 212223040135
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
P
## PROGRAM - ARP
```import socket 
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
## OUPUT - ARP
![arp](https://github.com/nivethasuresh1408/2c.ARP_RARP_PROTOCOLS/assets/152055927/8996dab6-b9dc-40d7-bd66-7988f9c77290)

## PROGRAM - RARP
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
![rarp](https://github.com/nivethasuresh1408/2c.ARP_RARP_PROTOCOLS/assets/152055927/4812d276-1a5b-4e95-a16d-7f9e56f743e5)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
