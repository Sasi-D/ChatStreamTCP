# ChatStreamTCP
ChatStreamTCP is a real time chat room application featuring both server and client components, built with multithreading to handle concurrent user interactions efficiently.

## Quick Info
The client requests a TCP connection from the server, which then prompts for a unique username. Once logged in, the client can send messages, which the server broadcasts to all users except the sender. Inactive clients are automatically kicked out after a set time.

The server supports the following commands from the client side:
- `\list` – Lists all logged-in users.
- `\bye` – Removes the client from the server and closes the connection.


## Server application
The server application is multi-threaded, enabling it to send messages in real time. It requires three command line arguments: the port number (P) on which it will listen, the max number of streams(M) to be supported at once, and the timeout(T) in seconds that will automatically disconnects client after period of inactivity respectively. To run Server use the following commands:
```sh
gcc -o server tcp_chat_server.c
./server <port> <M> <T>
```

## Client application
Client application won't take any command-line arguments. Multiple instances of client's can be instantiated from same end-host.  To run Client use the following commands :
```sh
gcc -o client tcp_chat_client.c
./client
```
