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

## OUTPUT:
file:///home/sec/Pictures/Screenshots/Screenshot%20from%202023-01-12%2020-43-33.png![image](https://user-images.githubusercontent.com/120643262/212104996-969fac1c-9c28-48ff-849b-f8cb5ed0437e.png)

## RESULT:
Thus the swapping of two values are successfully executed



