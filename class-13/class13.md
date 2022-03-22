# Socket :
WebSocket
The WebSocket object provides the API for creating and managing a WebSocket connection to a server, as well as for sending and receiving data on the connection.

To construct a WebSocket, use the WebSocket() constructor.

Note: This feature is available in Web Workers

EventTarget
WebSocket
Constructor
WebSocket()
Returns a newly created WebSocket object.

Properties
WebSocket.binaryType
The binary data type used by the connection.

WebSocket.bufferedAmount Read only
The number of bytes of queued data.

WebSocket.extensions Read only
The extensions selected by the server.

WebSocket.protocol Read only
The sub-protocol selected by the server.

WebSocket.readyState Read only
The current state of the connection.

WebSocket.url Read only
The absolute URL of the WebSocket.

Methods
WebSocket.close()
Closes the connection.

WebSocket.send()
Enqueues data to be transmitted.

Events
Listen to these events using addEventListener() or by assigning an event listener to the oneventname property of this interface.

close
Fired when a connection with a WebSocket is closed. Also available via the onclose property

error
Fired when a connection with a WebSocket has been closed because of an error, such as when some data couldn't be sent. Also available via the onerror property.

message
Fired when data is received through a WebSocket. Also available via the onmessage property.

open
Fired when a connection with a WebSocket is opened. Also available via the onopen property.

Examples
// Create WebSocket connection.
const socket = new WebSocket('ws://localhost:8080');

// Connection opened
socket.addEventListener('open', function (event) {
    socket.send('Hello Server!');
});

// Listen for messages
socket.addEventListener('message', function (event) {
    console.log('Message from server ', event.data);
});


************

# Servers :
A server is a computer or system that provides resources, data, services, or programs to other computers, known as clients, over a network. In theory, whenever computers share resources with client machines they are considered servers. There are many types of servers, including web servers, mail servers, and virtual servers.

An individual system can provide resources and use them from another system at the same time. This means that a device could be both a server and a client at the same time.

Some of the first servers were mainframe computers or minicomputers. Minicomputers were much smaller than mainframe computers, hence the name. However, as technology progressed, they ended up becoming much larger than desktop computers, which made the term microcomputer somewhat farcical.

Initially, such servers were connected to clients known as terminals that did not do any actual computing. These terminals, referred to as dumb terminals, existed simply to accept input via a keyboard or card reader and to return the results of any computations to a display screen or printer. The actual computing was done on the server.

Later, servers were often single, powerful computers connected over a network to a set of less-powerful client computers. This network architecture is often referred to as the client-server model, in which both the client computer and the server possess computing power, but certain tasks are delegated to servers. In previous computing models, such as the mainframe-terminal model, the mainframe did act as a server even though it wasn’t referred to by that name.

As technology has evolved, the definition of a server has evolved with it. These days, a server may be nothing more than software running on one or more physical computing devices. Such servers are often referred to as virtual servers. Originally, virtual servers were used to increase the number of server functions a single hardware server could do. Today, virtual servers are often run by a third-party on hardware across the Internet in an arrangement called cloud computing.

A server may be designed to do a single task, such as a mail server, which accepts and stores email and then provides it to a requesting client. Servers may also perform several tasks, such as a file and print server, which both stores files and accepts print jobs from clients and then sends them on to a network-attached printer.


How a server works

To function as a server, a device must be configured to listen to requests from clients on a network connection. This functionality can exist as part of the operating system as an installed application, role, or a combination of the two.

For example, Microsoft’s Windows Server operating system provides the functionality to listen to and respond to client requests. Additionally installed roles or services increase which kinds of client requests the server can respond to. In another example, an Apache web server responds to Internet browser requests via an additional application, Apache, installed on top of an operating system.

When a client requires data or functionality from a server, it sends a request over the network. The server receives this request and responds with the appropriate information. This is the request and response model of client-server networking, also known as the call and response model.

A server will often perform numerous additional tasks as part of a single request and response, including verifying the identity of the requestor, ensuring that the client has permission to access the data or resources requested, and properly formatting or returning the required response in an expected way.


Types of servers
 

There are many types of servers that all perform different functions. Many networks contain one or more of the common server types:

File servers
File servers store and distribute files. Multiple clients or users may share files stored on a server. In addition, centrally storing files offers easier backup or fault tolerance solutions than attempting to provide security and integrity for files on every device in an organization. File server hardware can be designed to maximize read and write speeds to improve performance.

Print servers
Print servers allow for the management and distribution of printing functionality. Rather than attaching a printer to every workstation, a single print server can respond to printing requests from numerous clients. Today, some larger and higher-end printers come with their own built-in print server, which removes the need for an additional computer-based print server. This internal print server also functions by responding to print requests from a client.

Application servers
Application servers run applications in lieu of client computers running applications locally. Application servers often run resource-intensive applications that are shared by a large number of users. Doing so removes the need for each client to have sufficient resources to run the applications. It also removes the need to install and maintain software on many machines as opposed to only one.

DNS servers

Domain Name System (DNS) servers are application servers that provide name resolution to client computers by converting names easily understood by humans into machine-readable IP addresses. The DNS system is a widely distributed database of names and other DNS servers, each of which can be used to request an otherwise unknown computer name. When a client needs the address of a system, it sends a DNS request with the name of the desired resource to a DNS server. The DNS server responds with the necessary IP address from its table of names.

Mail servers

Mail servers are a very common type of application server. Mail servers receive emails sent to a user and store them until requested by a client on behalf of said user. Having an email server allows for a single machine to be properly configured and attached to the network at all times. It is then ready to send and receive messages rather than requiring every client machine to have its own email subsystem continuously running.

Web servers
One of the most abundant types of servers in today’s market is a web server. A web server is a special kind of application server that hosts programs and data requested by users across the Internet or an intranet. Web servers respond to requests from browsers running on client computers for web pages, or other web-based services. Common web servers include Apache web servers, Microsoft Internet Information Services (IIS) servers and Nginx servers.

 

Web Server

Database servers
The amount of data used by companies, users, and other services is staggering. Much of that data is stored in databases. Databases need to be accessible to multiple clients at any given time and can require extraordinary amounts of disk space. Both of these needs lend themselves well to locating such databases on servers. Database servers run database applications and respond to numerous requests from clients. Common database server applications include Oracle, Microsoft SQL Server, DB2, and Informix.

Virtual servers
Virtual servers are taking the server world by storm. Unlike traditional servers that are installed as an operating system on machine hardware, virtual servers exist only as defined within specialized software called hypervisor. Each hypervisor can run hundreds, or even thousands, of virtual servers all at once. The hypervisor presents virtual hardware to the server as if it were real physical hardware. The virtual server uses the virtual hardware as usual, and the hypervisor passes the actual computation and storage needs onto the real hardware beneath, which is shared among all the other virtual servers.

Proxy servers
A proxy server acts as an intermediary between a client and a server. Often used to isolate either the clients or servers for security purposes, a proxy server takes the request from the client. Instead of responding to the client, it passes the request on to another server or process. The proxy server receives the response from the second server and then replies to the original client as if it were replying on its own. In this way, neither the client nor the responding server needs to directly connect to each other.

Monitoring and management servers
Some servers exist to monitor or manage other systems and clients. There are many types of monitoring servers. Several of them listen to the network and receive every client request and server response, but some do not request or respond to data themselves. In this way, the monitoring server can keep track of all the traffic on the network, as well as the requests and replies of clients and servers, without interfering with those operations. A monitoring server will respond to requests from monitoring clients such as those run by network administrators watching the health of the network.


Server structures
 

The concept of servers is nearly as old as networking itself. After all, the point of a network is to allow one computer to talk to another computer and distribute either work or resources. Computing has evolved since then, resulting in several types of server structures and hardware.

Mainframe or minicomputer (AS/400)
You could say that the original servers, mainframe computers, and later, minicomputers, handled almost all computing tasks except the interaction with the user through a screen and keyboard, which was left to the client system.

Computer hardware server
The next major wave of servers included computer-based servers. In many respects, these servers were nothing more than larger, more powerful desktop computers. Such servers were generally more expensive and held far more memory and disk space than most client computers. Each server was still a self-contained unit with its own motherboard, processor, memory, disk drives, and power supply. Servers like this were often warehoused in air-conditioned rooms called server rooms, and were later bolted into racks for better storage and accessibility.

Blade servers
The original computer server hardware was large and stored in racks that could hold hundreds of pounds. Over time, however, faster means of connecting hardware resulted in parts of the server being extracted from a single self-contained device. By removing hard drives, eliminating internal cooling, and the ongoing miniaturization of computing parts, servers were eventually reduced to a single thin server known as a blade server. While still stored in racks in server rooms, blade servers are smaller and can be replaced more easily.

Combining servers
Even before virtualization, servers were being extracted from the standard model of a single server operating system installed on a hardware machine. Technology, such as network-attached storage, removed the need for a server to have its own storage. Other technologies, such as mirroring and clustering, enabled pieces of hardware to be combined into larger, more powerful servers. Such a server might consist of several blades, several attached storage devices, and an external power supply, and each piece could be swapped out for another while the server was still running.

Virtual servers
Virtual Servers still require hardware, but that hardware now runs a different process known as a hypervisor. In some cases, such as Microsoft’s Hyper-V, a full operating system continues to run on the hardware itself. In other cases, so-called bare-metal hypervisors can be installed directly onto server hardware. In both instances, the hardware itself is often spread across an array of blade servers, networked storage, and power supply, resulting in an environment where it is impossible to tell where any individual server ends and another begins.