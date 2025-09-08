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
## SERVER
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

## CLIENT
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## SERVER
<img width="1481" height="424" alt="EX SERVER" src="https://github.com/user-attachments/assets/40826f0a-1948-4eac-b937-ea9dd0de10f2" />


## CLIENT
<img width="1475" height="373" alt="EX CLIENT" src="https://github.com/user-attachments/assets/209c341b-002d-406f-a41a-918ef683e969" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
