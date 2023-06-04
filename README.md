# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

## DATE:16-03-2023

# AIM :
 To write a python program to perform stop and wait protocol

# ALGORITHM :

 1. Start the program.
 2. Get the frame size from the user
 3. To create the frame based on the user request.
 4. To send frames to server from the client side.
 5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
 6. Stop the program


# SERVER PROGRAM :
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
# CLIENT PROGRAM:
```py
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

# SERVER OUTPUT :

![server2](https://github.com/BALUREDDYVELAYUDHAMGOWTHAM/EX-2/assets/119559905/21463ba1-d7a5-4cc9-9745-be104459400a)


# CLIENT OUTPUT:

![client2](https://github.com/BALUREDDYVELAYUDHAMGOWTHAM/EX-2/assets/119559905/3e468ce8-fd8d-4b1c-9976-e4ac2e0168ad)


# RESULT :
### Thus, python program to perform stop and wait protocol was successfully executed.
