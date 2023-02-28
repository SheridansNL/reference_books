## Sockets

Socket programming is a way of connecting two nodes on a network to communicate with each other. 
One socket(node) listens on a particular **port at an IP**, while the other socket reaches out to the other to form a connection. The server forms the listener socket while the client reaches out to the server.  In simpler terms, there is a server and a client.   
Socket programming is started by importing the socket library and making a simple socket.
```python
# create simple socket
import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```
[^1]: AF_INET: indicates the use of IPv4
[^2]: SOCK_STREAM: indicates that this is a TCP client.

```python
#connect
client.connect((target_host,target_port))

#send data
client.send(b"GET / HTTP/1.1\r\nHost: google.com\r\n\r\n")

#receive data
response = client.recv(4096)

print(response.decode())
client.close()
```
> The connection may not always succeed. 
> The server may want to send data first before receiving
> The server does not always respond (directly)

Simple UDP client
```python
import socket

# Create a UDP socket
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

# Send a message to the server
server_address = ('localhost', 10000)
message = b'This is the message. It will be repeated.'
sock.sendto(message, server_address)

# Receive a response from the server
data, server = sock.recvfrom(4096)

print(f'Received {data} from {server}')

# Close the socket
sock.close()