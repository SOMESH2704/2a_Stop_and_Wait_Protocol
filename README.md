# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
<h3>client.py
  
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
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
```
<h3>server.py

```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode()) 
```

## OUTPUT
<img width="1709" height="292" alt="image" src="https://github.com/user-attachments/assets/bc0bc689-72fd-4c57-b706-70f28d15bfed" />

<br>

<img width="1711" height="185" alt="image" src="https://github.com/user-attachments/assets/3d7bb244-2d1c-4bdd-97dc-9836de415cda" />



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
