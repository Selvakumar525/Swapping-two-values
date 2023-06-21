# Swapping-two-values

## AIM:
To write a python program for swapping of two values

## EQUIPEMENT'S REQUIRED: 
PC
Anaconda - Python 3.7

## ALGORITHM: 

### Step 1:
Get the two values from the user
### Step 2: 
Assign the value of second variable to a temporary variable 
### Step 3: 
Assign the value of the first variable to the second variable.
### Step 4:  
Assign the value in temporary variable to the first variable
### Step 5: 
Print both the values it would be interchanged
### Step 6: 
End the program

## PROGRAM:
```python
ex1 Stop and Wait Protocol
ALGORITHM:
1. Start the program. 2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side. 
5. If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
6. Stop the program
#Program to swap two values.
#Developed by: Selva Kumar
#RegisterNumber:22009007
### CLIENT:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5) c,addr=s.accept()
while True:
  i=input("Enter a data: ")
  c.send(i.encode())
  ack=c.recv(1024).decode()
  if ack:
    print(ack)
    continue
  else:
    c.close()
    break
### SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("Acknowledgement Recived".encode()
```
~~~ python
ex2 Sliding window Pr
ALGORITHM:
1. Start the program. 
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side. 
5. If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
6. Stop the program
### CLIENT:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
  while(i<len(l)):
    st+=s
    c.send(str(l[i:st]).encode())
    ack=c.recv(1024).decode()
    if ack:
      print(ack)
      i+=s
### SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("acknowledgement recived from the server".enc
~~~
~~~ python
ex3 Study ofsocket programming with client serve
ALGORITHM:
Server:
1. Create a server socket and bind it to port.
2. Listen for new connection and when a connection arrives, accept it.
3. Send server‟s date and time to the client. 
4. Read client‟s IP address sent by the client.
5. Display the client details. 
6. Repeat steps 2-5 until the server is terminated.
7. Close all streams. 
8. Close the server socket.
9. Stop.
  Client:
1. Create a client socket and connect it to the server‟s port number.
2. Retrieve its own IP address using built-in function.
3. Send its address to the server.
4. Display the date & time sent by the server.
5. Close the input and output streams. 
6. Close the client socket.
7. Stop.

### CLIENT:
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").en
code()) ack=c.recv(1024).decode()
if ack:
  print(ack)
c.close()
### SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
~~~
~~~ python
ex4 Simulating ARP
ALGORITHM:
Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address. 
4. Send this IP address to server.
5. Server returns the MAC address to client.
  Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client
CLIENT:
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
### SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  ip=input("Enter logical Address : ")
  s.send(ip.encode())
  print("MAC Address",s.recv(1024).decode())
~~~
~~~ python
ex5 Simulating RARP
ALGORITHM:
Client
1. Start the program
2. Using datagram sockets UDP function is established.
3. Get the MAC address to be converted into IP address.
4. Send this MAC address to server. 
5. Server returns the IP address to client.
Server
1. Start the program.
2. Server maintains the table in which IP and corresponding MAC addresses are stored.
3. Read the MAC address which is send by the client. 
4. Map the IP address with its MAC address and return the IP address to client
CLIENT:
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
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
  ip=input("Enter MAC Address : ")
  s.send(ip.encode())
  print("Logical Address",s.recv(1024).decode())
~~~
~~~ python
ex 6 Simulating PING command
ALGORITHM:
Step 1: start the program. 
Step 2: Include necessary package in java. 
Step 3: To create a process object p to implement the ping command. 
Step 4: declare one Buffered Reader stream class object. 
Step 5: Get the details of the server
5:1: length of the IP address.
5:2: time required to get the details.
5:3: send packets, receive packets and lost packets.
5.4: minimum, maximum and average times.
Step 6: print the results.
Step 7: Stop the program
CLIENT:
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
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  ip=input("Enter the website you want to ping ")
  s.send(ip.encode()) print(s.recv(1024).decode())
  ~~~
~~~ python
ex 7 Simulating TRACERO
1. Start the program.
2. Get the frame size from the user. 
3. To create the frame based on the user request. 
4. To send frames to server from the client side.
5. If your frames reach the server, it will send ACK signal to client otherwise it will send NACK signal to client.
6. Stop the program
### program 
from scapy.all import*
target = ["www.google.com"]
result, unans = traceroute(target,maxttl=32)
print(result,unans)
~~~
~~~ python
ex 8 Application using TCP Sockets Creation for Echo client and echo server
ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in server
.4. Send and receive the message using the send function in socket
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  msg=input("Client > ")
  s.send(msg.encode())
  print("Server > ",s.recv(1024).decode())
SERVER:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
  ClientMessage=c.recv(1024).decode()
  c.send(ClientMessage.encode())
~~~
~~~ python
ex 9 Application using TCP Sockets Creation for C
ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in server
4. Send and receive the message using the send function in socket.
CLIENT:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  msg=input("Client > ")
  s.send(msg.encode())
  print("Server > ",s.recv(1024).decode())
SERVER:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
  ClientMessage=c.recv(1024).decode()
  print("Client > ",ClientMessage)
  msg=input("Server > ")
  c.send(msg.encode())
  ~~~
~~~ python
ex 10 Application using TCP Sockets Creation for
ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module. 
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it                                                                                     
CLIENT:
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))
s.send("Hello server!".encode())
with open('received_file', 'wb') as f:
  while True:
    print('receiving data...')
    data = s.recv(1024)
    print('data=%s', (data))
    if not data:
      break
  f.write(data)
f.close()
print('Successfully get the file')
s.close()
print('connection closed')
SERVER:
importsocket
port = 60000
s = socket.socket()
host = socket.gethostname()
s.bind((host, port))
s.listen(5)
while True:
  conn, addr = s.accept()
  data = conn.recv(1024)
  print('Server received', repr(data))
  filename='mytext.txt' f = open(filename,'rb')
  l = f.read(1024)
  while (l):
    conn.send(l)
    print('Sent ',repr(l))
    l = f.read(1024)
f.close()
print('Done sending')
conn.send('Thank you for connecting'.encode())
conn.close()

~~~
## OUTPUT:
file:///home/sec/Pictures/Screenshots/Screenshot%20from%202023-01-12%2020-43-33.png![image](https://user-images.githubusercontent.com/120643262/212104996-969fac1c-9c28-48ff-849b-f8cb5ed0437e.png)

## RESULT:
Thus the swapping of two values are successfully executed



