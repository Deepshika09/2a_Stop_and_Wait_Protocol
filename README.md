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
### Client
```
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
    else:
        c.close()
        break
```
### Server
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT
### Client

<img width="757" height="257" alt="Screenshot 2026-08-20 231329" src="https://github.com/user-attachments/assets/65ffe27a-0bae-4b71-82e6-5416755b3f89" />


### Server

<img width="735" height="155" alt="image" src="https://github.com/user-attachments/assets/76767a3b-d324-4f7d-b74b-147db3518cc1" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
