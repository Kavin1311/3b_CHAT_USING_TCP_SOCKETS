# NAME:T.KAVINAJAI
# REGISTER NO: 212223100020
# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
# CLIENT.PY:
```
import socket

client = socket.socket()
client.connect(('localhost', 8000))

while True:
    message = input("Client > ")
    client.send(message.encode())

    reply = client.recv(1024).decode()
    print("Server >", reply)

```
# SERVER.PY:
```
import socket

server = socket.socket()
server.bind(('localhost', 8000))
server.listen(1)
print("Waiting for client...")

client, address = server.accept()
print("Connected to", address)

while True:
    message = client.recv(1024).decode()
    print("Client >", message)

    reply = input("Server > ")
    client.send(reply.encode())

```
## OUPUT
# CLIENT:
![image](https://github.com/user-attachments/assets/91d5ca1a-4026-4623-9ed4-f240765244cd)
# SERVER:
![image](https://github.com/user-attachments/assets/77a9931c-ac5f-40ab-9588-c105069dc902)

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
