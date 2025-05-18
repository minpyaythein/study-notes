# General Knowledge

#### Latency is about how fast a system responds to a single request while throughput is about how many requests a system can handle every second.

Latency is usually inversely proportional to throughput i.e. optimizing latency results in killing throughput and vice versa. For example, caching in database layer for better latency results in lower memory available for other tasks, reducing the amount of what a system can handle. Finding the right balance is very important.

#### IOPS vs. Throughput

The Disk IOPS Describes the count of input/output operations on the disk per seconds, regardless block size.

The disk throughput describes how many data may be transferred per second, so the block size play a huge role upon calculating the throughput required by app.

Let's consider as the sample the 3000 IOPS and SQL database engine, the block size in terms of db engine is called the page size and for SQL Server it's equal to 8 KB. If you wish to calculate the actual throughput, if the IOPS defined, you will end up with the formula below:

throughput = [IOPS] _ [block size] = 3000 _ 8 = 24 000 KB/s = 24 MB/s

#### While IOPS tell us how many actual operations we can perform per second, throughput tells us how much data can be transferred in the same time. Latency, however, tells us how long we have to wait for this operation to be performed (or finished, depending on what type of latency you're looking for)

#### Monitoring

Collecting and visualizing data about systems regularly so the system's health can be viewed and tracked

Three questions of monitoring
1. Is the service on?
2. Is the service functioning as expected?
3. Is the service performing well?

DevOps Measure of Success
MTTD (Mean Time to Detect) and MTTR (Mean Time to Resolve)

#### Method Monitoring

RED Method happens on Application side.
Rate or throughput: request per second
Errors: Failed requests i.e., HTTP 500
Duration: Latency or Transaction Response Time

USE Method happens on Infrastructure side.
Utilization i.e., CPU, Memory, Disk Usage
Saturation: Network queue length i.e., when network is fully utilized and no space for the next one, the network packets would queue up the length of that queue.
Errors i.e., Disk write error

Four Golden Signals Method (RED+S)

Core web vitals are also called frontend part of a web app.

#### Monitoring is not equal to Observability.

Observability tells you why an issue occurred and better suited for modern, complex and distributed systems.

Monitoring lets you decide what to keep an eye on before collecting data and better suited for monolithic architecture and only tells when an issue occurred.

#### Types of Telemetry Data

MELT: Metric, Event, Log and Trace.

Traces show exactly where the request has gone through and then where it may have failed.

#### OSI 7 Layers

The OSI (Open Systems Interconnection) model is a conceptual framework used to understand how different networking protocols interact in a network. It divides networking into seven distinct layers, each responsible for specific functions.

1. Physical Layer: This layer deals with the transmission of raw data bits over a physical medium. It includes the hardware technologies involved, like cables and switches.

2. Data Link Layer: The primary role here is to handle the transfer of data between adjacent network nodes within the same local network. This includes protocols like Ethernet and handling error detection and correction.

3. Network Layer: Responsible for routing packets across the network. It manages logical addressing (like IP addresses) and determines the best path for data to travel.

4. Transport Layer: This layer ensures complete data transfer. It manages the segmentation of data, flow control, and error recovery. Common protocols include TCP (Transmission Control Protocol) and UDP (User Datagram Protocol).

5. Session Layer: It establishes, manages, and terminates connections or sessions between applications. It handles the exchange of information and can manage multiple sessions simultaneously.

6. Presentation Layer: Sometimes called the "syntax layer," this stage transforms data to be presented to the application layer. It can involve translating between different data formats or encrypting and compressing data.

7. Application Layer: The top layer where end-user software applications operate. Protocols here include HTTP, FTP, and SMTP. It provides services directly to user applications.

The OSI model helps standardize networking protocols to promote interoperability among different systems. Understanding these layers is crucial for network engineers and IT professionals to troubleshoot and design networks effectively.

TLDR: The OSI model is a 7-layered model used to understand how data is transferred between computers in a network, with each layer having a specific function to enable efficient and secure data transmission.

1. 00:00 💻 The OSI model is a 7-layered model used to understand how data is transferred between computers in a network.
	1.1 The OSI model is a 7-layered model used to understand how data is transferred between computers in a network, with each layer containing protocols needed for successful communication.

2. 01:31 💻 Application layer protocols enable network services like file transfer, web surfing, emails, and virtual terminals, while data compression and encryption enhance security and speed up transmission.
	2.1 The application layer protocols enable various functions for network services such as file transfer, web surfing, emails, and virtual terminals.
	2.2 Data compression reduces file size for faster transmission and encryption enhances security, with the presentation layer performing translation, compression, and encryption/decryption.

3. 03:57 💻 Session layer manages connections and enables data transfer with authentication and authorization.
	3.1 Session layer manages connections and enables sending and receiving of data, performing functions such as authentication and authorization.

4. 05:25 📥 The session layer manages file downloads and assists in session management, authentication, and authorization.
	4.1 Session layer manages the files being downloaded by tracking data packets and their corresponding files, while also assisting in session management, authentication, and authorization.

5. 06:58 📲 The transport layer regulates data transmission and provides error control and two types of services, TCP and UDP, for maintaining system performance on mobile devices.
	5.1 The transport layer in our mobile device can regulate the data transmission rate from the server to maintain system performance.
	5.2 The transport layer adds a checksum to each segment for error control and provides two types of services, connection-oriented via TCP and connectionless via UDP, with TCP providing feedback for retransmission of lost data, while UDP is used for applications where full data delivery is not necessary, and the network layer works to transmit data packets between computers in different networks.

6. 09:18 🌐 The network layer assigns unique IP addresses and uses routing to move data packets based on logical address format.
	6.1 The network layer assigns unique IP addresses to each computer in a network and uses routing to move data packets from source to destination based on the logical address format of IPv4 or IPv6.
	6.2 Data packets are delivered to their unique IP address through routing decisions made by layer 3 devices using protocols such as OSPF and BGP.

7. 11:32 💻 IP addresses are assigned at the network layer and MAC addresses at the data link layer for data transfer and media access.
	7.1 Data is transferred between computers through logical and physical addressing, with IP addresses assigned at the network layer and MAC addresses assigned at the data link layer, which controls data transfer and access to media.

8. 12:47 💻 📡 Data is transferred between devices through various layers of the OSI model, with the data link layer controlling how data is placed and received from the media using media access control.
	8.1 Two hosts, a laptop and a desktop, connected to different networks, communicate using network layer protocols and data link layer adds data to the head and tail of IP packets.
	8.2 Data is transferred between devices through various layers of the OSI model, with the data link layer providing access to media and controlling how data is placed and received from the media using media access control.
	8.3 Data link layer prevents collisions by using carrier sense multiple access and detects errors in received frames using tail bits.
	8.4 The physical layer converts binary sequences into signals and transmits them over local media, while also receiving signals and passing them to the data link layer, ultimately allowing for the transfer of data between distant hosts through the 7 layers of the OSI model.

(1. 00:00  Hey guys this is dg. Today. We are going to learn about osi model or open system interconnection model. So let's start osi model defines and is used to understand how data is transferred from one computer to another in a computer network in the most basic form. Two computers connected to each other with lan cable and connectors sharing data with the help of network. Interface cards forms a network but if one computer is based on microsoft windows and the other one has mac os installed then how these two computers are going to communicate with each other in order to accomplish successful communication between computers or networks of different architectures. 7-layered osi model or open system interconnection model was introduced by international organization for standardization in 1984 containing application layer presentation layer session layer transport layer network layer data link layer and physical layer. Note that each layer is a package of protocols if I say application layer then it does not mean that it includes computer applications like chrome firefox etc. But it includes application layer protocols that are needed to make these applications work correctly in a network or internet. Let's start with the topmost layer application layer application layer is used by network applications. Network application means computer applications that use internet like google chrome firefox outlook skype etc.
2. 01:31  Web browser is a network application running in your pc. It does not reside in the application layer but it uses application layer protocols http or https to do web surfing not only web browser but all network applications including outlook skype etc. All are dependent on application layer protocols to function. There are dozens of application layer protocols that enable various functions. At this layer. All these protocols collectively form application layer. These protocols form the basis for various network services like file transfer web surfing emails virtual terminals etc. File transfer is done with the help of ftp. Protocol. Web surfing is done with the help of http or https protocol for emails. Smtp protocol is used and for virtual terminals telnet is used so application layer provides services for network applications with the help of protocols to perform user activities next to application layer is presentation. Layer presentation layer receives data from application layer. This data is in the form of characters and numbers. Presentation. Layer converts these characters and numbers to machine understandable binary format for example conversion of ascii to fcd code. This function of presentation layer is called translation before data is transmitted. Presentation layer reduces the number of bits that are used to represent the original data.
This bit reduction process is called data compression and it can be lossy or lossless. Data compression reduces the amount of space used to store the original file as the size of file is reduced. It can be received at destination in a very less time that is data transmission can be done faster. Thus data compression is very helpful in real time video and audio streaming to maintain the integrity of data before transmission data is encrypted. Encryption enhances the security of sensitive data at center side. Data is encrypted and at receiver side data is decrypted ssl protocol or secure sockets. Layer protocol is used in presentation layer for encryption and decryption. So presentation layer performs three basic functions. Translation compression and encryption decryption.
3. 03:57  Now session layer suppose you have planned for a party. You have hired a few helpers ensuring that each activity runs smoothly. Helpers will help you in setting up assisting cleaning and then closing the party same is the case with session layer session. Layer helps in setting up and managing connections enabling sending and receiving of data followed by termination of connections or sessions. Like you hired some helpers for your party session. Layer 2 has its own helpers called apis or application programming interfaces. Netbios or network basic input output system is an example of apis which allows applications on different computers to communicate with each other just before a session or a connection is established with the server server performs a function called authentication. Authentication is a process of verifying who you are for. This server uses a username and a password. Once entered username and password are matched a session or a connection is established between your computer and the server. After authenticating the user authorization is checked. Authorization is the process used by server to determine if you have permission to access a file if not you will get a message saying you are not authorized to access this page. Both of these functions authentication and authorization are performed by session layer session.
4. 05:25  Layer keeps a track of the files that are being downloaded. For example. A web page contains text images etc. These text and images are stored as separate files on the web server when you request a website in your web browser. Your web browser opens a separate session to the web server to download each of these text and image files. Separately. These files are received in the form of data packets. Session. Layer keeps a track of which data packet belongs to which file either text file or image file and tracks where the received data packet go. In this case it goes to web browser that is session layer helps in session management so session layer helps in session management authentication and authorization. Your web browser performs all functions of session presentation and application layer. Layer below session layer is transport. Layer transport layer controls the reliability of communication through segmentation flow control and error control in segmentation. Data received from session layer is divided into small data units called segments. Each segment contains a source and destinations port number and a sequence number port number helps to direct each segment to the correct application and sequence number helps to reassemble segments in the correct order to form correct message at the receiver in flow control transport layer controls the amount of data being transmitted.
5. 06:58  Consider our mobile is connected to a server. Suppose. Server can transmit data maximum at 100 mbps and our mobile can process data maximum at 10 mbps. Now we are downloading a file from the server but server starts sending data at 50 mbps which is greater than the rate. Our mobile can process so mobile phone with the help of transport layer can tell the server to slow down data transmission rate up to 10 mbps so that no data gets lost similarly if server is sending data at 5 mbps. Mobile phone tells the server to increase data transmission rate to 10 mbps to maintain system performance.
Transport layer also helps in error control if some data does not arrive. The destination transport layer uses automatic repeat request schemes to re-transmit the lost or corrupted data. A group of bits called checksum is added to each segment by the transport layer to find out received. Corrupted segment. Protocols of transport layer are transmission control protocol or tcp and user datagram protocol or udp transport layer performs two types of services connection oriented transmission and connectionless transmission connection. Oriented transmission is done via tcp while connectionless transmission is done via udp. Odp is faster than tcp because it does not provide any feedback whether data was really delivered whereas tcp provides a feedback. Therefore lost data can be retransmitted in tcp. Udp is used where it does not matter whether we have received all data for example online streaming movies songs games voice over ip tftp dns etc. On the other hand tcp is used where full data delivery is must for example world wide web email ftp etc. So transport layer is involved in segmentation flow control error control connection oriented and connectionless transmission transport layer passes data segments to the network layer network layer works for the transmission of the received data segments from one computer to another located in different networks. Data units in the network layer are called packets.
6. 09:18  It is the layer where routers recite. The function of network. Layer are logical addressing routing and path determination. Ip addressing done in network layer is called logical. Addressing. Every computer in a network has a unique. Ip address network layer assigns sender and receiver's ip address to each segment to form an ib packet. Ip. Addresses are assigned to ensure that each data packet can reach the correct destination routing is a method of moving data packet from source to destination and it is based on the logical address format of ipv4 or ipv6 suppose computer.
A is connected to network 1 and computer b is connected to network 2. From computer b we have requested to access facebook.com and now there is a reply from facebook server for computer b in the form of packet. This packet needs to be delivered to computer b only since in a network. Each device has a unique ip address so these both computers will be having a unique ip address as well. Network layer of the facebook server has already added sender and receivers ip address in the packet. Suppose mask used is 225.225.225.0. This mask tells that the first three combination represents network while the last combination represents host or computer b so based on ip address format received data packet will move first to network 2 and then to computer b so based on ip address and mask. Routing decisions are made in a computer network now path determination. A computer can be connected to internet server for a computer in a number of ways choosing the best possible path for data. Delivery from source to destination is called passive determination. Layer 3 device devices use protocols such as open shortest path first border gateway protocol intermediate system to intermediate system to determine the best possible path for data. Delivery. Data link layer receives data packet from network. Layer data packets contain ip addresses of sender and receiver.
7. 11:32  There are two kinds of addressing logical addressing and physical addressing. Logical addressing is done at network layer where sender and receivers ip addresses are assigned to each segment to form a data packet. Physical addressing is done at data link layer where mac addresses of sender and receiver are assigned to each data packet to form a frame. Mac. Address is a 12 digit alphanumeric number embedded in network. Interface card of your computer by your computer manufacturer data unit in data link layer is called frame. Data link layer is embedded as software in network. Interface card of a computer and provide means to transfer data from one computer to another via a local media. Local media includes copper wire optical fiber or air for radio signals. Please. Note here media does not correspond to audio video or animation. It refers to the physical links between two or more computers or networks. Data link layer performs two basic functions. It allows upper layers of osi model to access media using techniques such as framing. It controls how data is placed and received from media using techniques such as media access.
8. 12:47  Control and error detection consider two distant hosts. A laptop and a desktop communicating with each other as laptop and desktop are connected to different networks so they will be using network layer protocols ip for example to communicate with each other. In this example desktop is connected to router r1 via an ethernet cable router. R1 and r2 are connected via a satellite link and laptop is connected to router r2 via a wireless link. Now desktop wants to send some data to laptop based on the medium used to connect desktop and router. R1 data link layer adds some data in the head and tail of ip packet and converts it to a frame ethernet frame.
In this case router. R1 receives this ethernet frame decapsulate it to an ip packet and then encapsulate it again to a frame so that it can cross satellite link to reach router. R2 router. R2 will again decapsulate the received frame and encapsulate it again to form a wireless data link frame laptop receives this wireless data link. Frame decapsulate it and then forward ip packet to network layer. Finally data arrives application layer application. Layer protocols then make the received data visible on computer screen so network layer or higher level. Layers are able to transfer data over media with the help of data link layer that is data. Link layer provides access to media for higher layers of osi model. Data link layer also controls how data is placed and received from the media. The technique used to get the frame on and off the media is called media access control.
There may be a number of devices connected to a common media if two or more devices connected to same media send data. At the same time. Then there may be a possibility of collision of the two messages resulting in a useless message that neither recipient can understand to avoid these situations. Data link layer keeps an eye on when the shared media is free so that device can transmit data for the receiver. This is called carrier sense multiple access so data link layer with its media access. Control methods controls data transmission tail of each frame contains bits which are used to detect errors in the received frame errors occur due to certain limitations of the media used for transmitting data.
The last layer is physical layer till now data from application layer has been segmented by transport layer placed into packets by network layer and framed by data link layer which is a sequence of binary zeros and ones. Physical layer converts this binary sequence into signal and transmit over local media. It can be an electrical signal in case of copper cable or lan cable light signal in case of optical fiber and radio signal in case of air so signal generated by physical layer depends on the type of media used to connect two devices at the receiver. Physical layer receives signals convert it to bits and pass it to data link layer as a frame frame is further decapsulated as data moves through higher layers. Finally data is moved to application layer application layer protocols makes the sender's message visible in the application in the receiver's computer screen. In this way osi model is helping to transfer data between distant hosts. So these 7 layers of osi model are lying behind the smooth functioning of internet if you have learnt something from this video. Then please like this video share this video so that more people can learn subscribe to tech terms if you want to learn more and turn the notification icon on thanks for watching.

Summary for https://youtu.be/vv4y_uOneC0 by https://eightify.app)


#### CSRF

CSRF Protection Doesn't Block Requests from OTHER SITES, But Ensures They Fail
Other sites can still send requests to your site.
However, CSRF protection ensures that unauthorized requests fail by requiring additional security checks.
🔹 How CSRF Protection Ensures Failure?
1️⃣ CSRF Tokens – The server expects a valid token that the attacker cannot generate.
2️⃣ SameSite Cookies – Prevents cookies from being sent in cross-site requests.
3️⃣ Origin/Referer Checks – Ensures the request is coming from the correct site.

#### CORS

CORS prevents JavaScript from reading another site's responses, unless explicitly allowed. ✅

The server will still process the request, even if it's from another site.
The browser enforces the restriction, preventing JavaScript from reading the response unless CORS headers allow it.

🔹 What CORS Actually Does
CORS (Cross-Origin Resource Sharing) is a browser security feature that controls which origins (websites) can access resources (responses) from another site.
It does not block requests from being sent but prevents JavaScript from reading responses if the request is not allowed by the server.

#### Timezones

The best advice I've heard (and I share) about TZs is this:

Do all your business logic in UTC timestamps only, using your language's best library for time logic.

Under no circumstances do you *ever* try to do time-based math/logic yourself. No, not even if it's "simple".

In Java 8+ that's "java.time", not "Dates" and "Calendars".

Whenever possible, store all your timestamps in the datastore in ISO-8601 formatted strings, in UTC. They're still sortable, searchable, but also human readable.

Transmit your timestamps across wires as ISO-8601 formatted strings, in UTC.

The only place that may know anything about time zones is the front-end, who convert it for the current user in the appropriate way for them, using a library that does it correctly.

There are edge cases, of course ("I need this to run at midnight local time in New York every Sunday"), but for 95% of cases the above system handles most bugs pretty nicely.

#### Database design

##### Normalization
1NF: A cell must not contain more than one value and each data (row and column) must be unique.
2NF: All data (columns) must depend on the whole primary key (not on the part of the composite key). (Look at the DATA (non-primary key)!)
    No partial dependencies.
    All non-key attributes depend on the whole primary key (or are in their own table).
3NF: The primary key must fully define all non-key columns. (Look at the PRIMARY key!)
    Transitive dependencies are removed — attributes that depend on something that's not a key.


##### Composite Key
Composite Key = A key made of more than one column to uniquely identify a row.
・Can employee_id alone uniquely identify each row?
・No, because one employee (like E001) can have multiple jobs.

・Can job_code alone identify each row?
・No, because many employees can have the same job (e.g., E001 and E002 both have J02).

So what uniquely identifies a row here・・
✅ The combination of:
employee_id + job_code
Together, these two columns uniquely identify each row.
That’s a composite key.

## Data Structures and Algorithms

##### Heap and Stack Memory

| Aspect           | Stack                                              | Heap                                             |
|------------------|----------------------------------------------------|--------------------------------------------------|
| **Who uses it?** | Functions/methods (for local vars, calls)          | You (developer/program), Java (GC)               |
| **What is it?**  | Memory for function calls & local vars             | Memory for dynamic object storage                |
| **When used?**   | When a function is called                          | When you use `new` or dynamic structures         |
| **Where stored?**| RAM (main memory, stack segment)                   | RAM (main memory, heap segment)                  |
| **Why used?**    | Fast allocation & auto-cleanup                     | For data that needs flexible/larger life         |
| **How works?**   | LIFO: push/pop frames automatically                | Manual allocation, cleaned by GC (e.g., in Java) |

・Stack is fast, but small and temporary.
・Heap is slower, but flexible and can store large or complex objects.
・In Java, the Garbage Collector (GC) frees memory on the heap automatically.
・Stack memory is automatically freed when functions return.

##### List, Set and Map

| Feature                                   | List                              | Set                              | Map                                  |
|-------------------------------------------|----------------------------------|---------------------------------|-------------------------------------|
| Allows duplicate elements                  | Yes                              | No                              | No (keys must be unique)             |
| Maintains insertion order                  | Yes                              | No (depends on implementation)  | No (depends on implementation)       |
| Allows null values                         | Any number                      | At most one null value           | One null key at most, many null values |
| Access elements by index                   | Yes (`get(index)`)               | No                              | No                                  |
| Best use case                             | Access by index, ordered data   | Unique elements                  | Key/value pair storage               |
| Traversal method                          | `ListIterator`                   | `Iterator`                      | `keySet()`, `values()`, `entrySet()`|

When to use Set, List, and Map
Set:
Use a Set when you only care about unique elements and don’t care about order or position.
Example: Checking if an item exists, storing unique IDs, removing duplicates.
List:
Use a List when you want to maintain order and allow duplicates, or when you need to access elements by index.
Example: Maintaining a playlist, ordered tasks, or any collection where position matters.
Map:
Use a Map when you want to store key-value pairs for fast lookup by key. Keys are unique, but values can be duplicated.
Example: Storing user profiles by user ID, caching data, or dictionary-like data.