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

<img width="1477" height="395" alt="SERVER" src="https://github.com/user-attachments/assets/75c2e3f2-03a1-4d34-9ef3-d654d75d41bf" />

## CLIENT

<img width="1477" height="290" alt="CLIENT" src="https://github.com/user-attachments/assets/0d9ec8dc-003f-46fb-be39-8bc655cf8d26" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
