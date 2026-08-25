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
### Server.py
```.py
# echo_server.py

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

### Client.py
```.py
# echo_client.py

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
## OUPUT

<img width="1831" height="295" alt="Screenshot 2026-08-25 102516" src="https://github.com/user-attachments/assets/43580a5b-9e6e-4413-932e-2269c3a0be35" />
<img width="1821" height="230" alt="Screenshot 2026-08-25 102537" src="https://github.com/user-attachments/assets/2380726a-e9e0-4604-8942-b2c0d2946f0f" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
