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
ex1
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
ex2
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
ex3
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
ex4
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
ex5
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
ex 6
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
ex 7
from scapy.all import*
target = ["www.google.com"]
result, unans = traceroute(target,maxttl=32)
print(result,unans)
~~~
~~~ python
ex 8
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
ex 9
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
ex 10
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



