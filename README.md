# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
## SERVER.PY
```
import socket 
# Create socket object 
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
# Bind the socket with host and port 
host = '127.0.0.1' 
port = 5000 
server_socket.bind((host, port)) 
# Listen for incoming connections 
server_socket.listen(1) 
print("Echo Server is waiting for connection...") 
# Accept client connection 
client_socket, addr = server_socket.accept() 
print("Connected to:", addr) 
while True: 
# Receive message from client 
 data = client_socket.recv(1024).decode() 
 if not data: 
  break 
 print("Client:", data) 
# Send same message back to client 
client_socket.send(data.encode()) 
# Close sockets 
client_socket.close() 
server_socket.close() 
```
## CLIENT.PY
```
import socket 
# Create socket object 
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
# Connect to server 
host = '127.0.0.1' 
port = 5000 
client_socket.connect((host, port)) 
while True: 
# Input message 
 message = input("Enter message: ") 
# Send message to server 
 client_socket.send(message.encode()) 
 if message.lower() == 'exit': 
    break 
# Receive echoed message 
 data = client_socket.recv(1024).decode() 
 print("Server echoed:", data) 
# Close socket 
client_socket.close()
```
## OUTPUT
## SERVERSIDE

<img width="1693" height="159" alt="image" src="https://github.com/user-attachments/assets/a937f957-88f6-4aa4-8ee6-416d30357aad" />

## CLIENTSIDE

<img width="1807" height="130" alt="image" src="https://github.com/user-attachments/assets/694d0ec9-c74b-48b3-b3e0-d6ad889239c7" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
