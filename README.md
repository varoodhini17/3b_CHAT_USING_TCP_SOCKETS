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
# server.py
```
import socket

server = socket.socket()
server.bind(('127.0.0.1', 12345))
server.listen(1)

print("Server is listening...")
conn, addr = server.accept()
print("Connected with", addr)

while True:
    message = conn.recv(1024).decode()
    print("Client:", message)

    reply = input("Server: ")
    conn.send(reply.encode())
```
# client.py
```
import socket

client = socket.socket()
client.connect(('127.0.0.1', 12345))

print("Connected to server")

while True:
    message = input("Client: ")
    client.send(message.encode())

    reply = client.recv(1024).decode()
    print("Server:", reply)
```

## OUPUT
<img width="1108" height="333" alt="image" src="https://github.com/user-attachments/assets/defa02db-cbbc-4bc9-bca5-c70c440b26fb" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
