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

CLIENT:
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

SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT

CLIENT:

![Screenshot 2025-03-29 143612](https://github.com/user-attachments/assets/9427b9ff-17d6-491f-9299-70d4c78caa36)

SERVER: 

![Screenshot 2025-03-29 143708](https://github.com/user-attachments/assets/af2b2f36-c3fe-4b7c-8168-0a4c525dc052)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
