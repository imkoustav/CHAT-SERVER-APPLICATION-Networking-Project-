# CHAT-SERVER-APPLICATION-Networking-Project-
CHAT SERVER  APPLICATION   

INTRODUCTION  
  
Sockets allow communication between two different processes on the same or different machines. To be more precise, it's a way to talk to other computers using standard Unix file descriptors. In Unix, every I/O action is done by writing or reading a file descriptor. A file descriptor is just an integer associated with an open file and it can be a network connection, a text file, a terminal, or something else.   
To a programmer, a socket looks and behaves much like a low-level file descriptor. This is because commands such as read() and write() work with sockets in the same way they do with files and pipes.   
Sockets were first introduced in 2.1BSD and subsequently refined into their current form with 4.2BSD. The sockets feature is now available with most current UNIX system releases.   
  
Where is Socket Used?   
A Unix Socket is used in a client-server application framework. A server is a process that performs some functions on request from a client. Most of the application-level protocols like FTP, SMTP, and POP3 make use of sockets to establish connection between client and server and then for exchanging data.   
Socket Types   
There are four types of sockets available to the users. The first two are most commonly used and the last two are rarely used.   
Processes are presumed to communicate only between sockets of the same type but there is no restriction that prevents communication between sockets of different types.   
•	Stream Sockets − Delivery in a networked environment is guaranteed. If you send through the stream socket three items "A, B, C", they will arrive in the same order − "A, B, C". These sockets use TCP (Transmission Control Protocol) for data transmission. If delivery is impossible, the sender receives an error indicator. Data records do not have any boundaries.   
•	Datagram Sockets − Delivery in a networked environment is not guaranteed. They're connectionless because you don't need to have an open connection as in Stream Sockets − you build a packet with the destination information and send it out. They use UDP (User Datagram Protocol).   
  
  
•	Raw Sockets − These provide users access to the underlying communication protocols, which support socket abstractions. These sockets are normally datagram oriented, though their exact characteristics are dependent on the interface provided by the protocol. Raw sockets are not intended for the general user; they have been provided mainly for those interested in developing new communication protocols, or for gaining access to some of the more cryptic facilities of an existing protocol.   
•	Sequenced Packet Sockets − They are similar to a stream socket, with the exception that record boundaries are preserved. This interface is provided only as a part of the Network Systems (NS) socket abstraction, and is very important in most serious NS applications. Sequenced-packet sockets allow the user to manipulate the Sequence Packet Protocol (SPP) or Internet Datagram Protocol (IDP) headers on a packet or a group of packets, either by writing a prototype header along with whatever data is to be sent, or by specifying a default header to be used with all outgoing data, and allows the user to receive the headers on incoming packets.   
  
  
  
  
  
  
  
  
 SOCKET PROGRAMMING IN JAVA  
  
What is socket programming?   
  
Socket programming is a way of connecting two nodes on a network to communicate with each other. One socket(node) listens on a particular port at an IP, while other socket reaches out to the other to form a connection. Server forms the listener socket while client reaches out to the server.   

OVERVIEW  
  
There are two major parts of this project- The Server Side and The Client Side.   
  
What is a Socket in Java?   
  
A socket in Java is one endpoint of a two-way communication link between two programs running on the network. A socket is bound to a port number so that the TCP layer can identify the application that data is destined to be sent to.   
  
Server :  
  
In computing, a server is a computer program or a device that provides functionality for other programs or devices, called "clients". This architecture is called the client–server model, and a single overall computation is distributed across multiple processes or devices. Servers can provide various functionalities, often called "services", such as sharing data or resources among multiple clients, or performing computation for a client. A single server can serve multiple clients, and a single client can use multiple servers. A client process may run on the same device or may connect over a network to a server on a different device.   
  
Basically, the server will instantiate its object and wait for the client request. Once the client sends the request, the server will communicate back with the response.   
In order to code the server-side application, you need two sockets and they are as follows:   
  
•	A Server Socket which waits for the client requests (when a client makes a new Socket())   
  
•	A plain old socket for communication with the client.   
  
After this, you need to communicate with the client with the response.   
Communication   
  
getOutputStream() method is used to send the output through the 
socket.   
  
Close the Connection   
  
It is important to close the connection by closing the socket as well as input/output streams once everything is done.  
  
Client :  
  
A client is a computer or a program that, as part of its operation, relies on sending a request to another program or a computer hardware or software that accesses a service made available by a server (which may or may not be located on another computer). For example, web browsers are clients that connect to web servers and retrieve web pages for display. Email clients retrieve email from mail servers. Online chat uses a variety of clients, which vary on the chat protocol being used. 
Multiplayer video games or online video games may run as a client on each computer. The term "client" may also be applied to computers or devices that run the client software or users that use the client software.  
  
Client Side Programming   
  
In the case of client-side programming, the client will first wait for the server to start. Once the server is up and running, it will send the requests to the server. After that, the client will wait for the response from the server. So, this is the whole logic of client and server communication. Now let’s understand the client side and server side programming in detail.   
  
In order to initiate a clients request, you need to follow the belowmentioned steps:   
  
1. Establish a Connection   
        The very first step is to establish a socket connection. A socket connection implies that the two machines have information about each other’s network location (IP Address) and TCP port.  
   
You can create a Socket with the help of a below statement:   
Socket socket = new Socket(“127.0.0.1”, 5000)   
  
•	Here, the first argument represents the IP address of Server.   
•	The second argument represents the TCP Port. (It is a number that represents which application should run on a server.)   
  
2. Communication   
  
            In order to communicate over a socket connection, streams are used for both input and output the data. After establishing a connection and sending the requests, you need to close the connection.  
  
3. Closing the connection  
  
           The socket connection is closed explicitly once the message to the server is sent.  
