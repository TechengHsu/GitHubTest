# Introduction to Computer Networks

> This handout only deals with the most basic topics about Computer Networks,
> please refer to EE3650/COM5310 for further information.
> If there's any problem with this file, please note me. Thank you.

## Prerequisites
* basic knowledge about HTML/JavaScript and better how they're executed on browsers
* knowing how to let files available on your own server/website
* (optional) programming language: C/C++
* (optional) hub/switch, router, port
* (optional) experience in PHP/MySQL, or setting up XAMP/LAMP, etc.


## Abstract 
This handout gives an introductory version of Computer Networks,
which is a useful subject/knowledge of great importance.
We'll first talk about the historical perspective of WWW,
giving us more insight into this interesting field,
and thus it provide us with the reason why we need this and how we do it.
We then turn our interest to Open System Interconnection (OSI), which is a very important concept
that results in today's TCP/IP and other network frameworks.
The main topic is IP and the overall structure of Internet (connections).
Finally, this handout will end up in something about UDP, DNS, TCP, etc.

> Additional information is provided <a href="Presentation_20150708.pdf">here</a> for further references.
> Note that this PDF is only for students in this club.
> You can also visit vBird's website for tons of information relating to this topic.

#### Contents

* Topic 1 -- Historical Perspective
  * Origination of World-Wide Web (WWW)
  * "A Patch Server" -- Apache 
  * IEEE Standards
* Topic 2 -- Introduction to Open System Interconnection (OSI)
  * Components Comprising the Web
  * Over View of OSI Layers
  * Simplification of OSI and Relating Motivation
* Topic 3 -- Transmission Control Protocol (TCP)
  * Three-Way Handshake
  * User Datagram Protocol (UDP)
  * (optional) Sockets
* Topic 4 -- Hypertext Transmission Protocol (HTTP) and HTTPS
  * Introduction to HTTP
  * Ports Commonly Used
  * Localhost
* Topic 5 -- Internet Protocol (IP)
  * IPv4 and IPv6
  * Domain
  * Netmask
  * Gateway/Router
  * Domain Name Server (DNS)
  * Dynamic Host Configuration Protocol (DHCP)
* Topic 6 -- Netwrok Hardwares
  * Switch/Hub/Router
  * Sample Network Structure: as a Company
* Topic 7 -- Other Relating Topics
  * Multiple Sense Multiple Access with Collision Detection (CSMA/CD)
  * (Reverse) Address Resolution Protocol (RARP/ARP)
  * Internet Control Message Protocol (ICMP)


## Topic 1 -- Historical Perspective
> Opening Questions: </br>
> What's the origin of "web"? </br>
> Why we have these networks protocol now? </br>
> What is a "server"? </br>
> Are there any standards regarding with various protocols? </br>


#### 1.1 Origination of World-Wide Web (WWW)
We now can see Internet everywhere in our lives, it may be surprising that
this is created/invented for military purposes during cold war times.
In the 1980's, incorporating TCP/IP protocols, a "net" of computers are able to communicate with each other.
The world-wide web (WWW) is then introduced to improve science researches.
That's the same time when HTTP is created to share researches among scientists.
Moreover, WWW and E-mail back in the 1980's and 1990's, respectively, made TCP/IP famous.
Interested reader can google "APARNET" for further information.

#### 1.2 "A Patch Server" -- Apache 
See HTTPd (HTTP daemon): https://en.wikipedia.org/wiki/Httpd . 
Back then, in order to actuate the HTTP protocol,
NCSA designed HTTPd to use as server, and then Netscape initiated its own server and browser for users.
However, since the server of Netscape's was too expensive, the mainstream was HTTPd server.
As time went by, due to lack of update of HTTPd server,
a society issued a project to enhance/improve it, named it "A Patch Server",
nicknamed "Apache", meaning this is a server with lots of modification.

#### 1.3 IEEE Standards
Thanks to hakers, the standard for Internet and Ethernet was established by IEEE, remaining as the standard.
To look at more details, please visit http://linux.vbird.org/linux_server/0360apache.php .

## Topic 2 -- Introduction to Open System Interconnection (OSI)
> Opening Questions: </br>
> What's the prototype of TCP/IP protocols?　</br>
> What elements make up to a basic but complete network? </br>
> Why OSI and its "descendants" are of great importance? </br>

#### 2.1 Components Comprising the Web
* Node: devices with IP
* Server: response
* Client: e.g. workstation
* Router/Gateway: connecting between two different interfaces, combining different groups of devices

#### 2.2 Over View of OSI Layers
At the beginning, we devide the networking application into seven layers,
with Layer 1 closest to the hardware and Layer closest to software, so to speak.
The overall structure is shown below.</br>
<img src="OSI.gif"/></br>
We're not going into details of these seven scray layers, 
please visit http://www.webopedia.com/quick_ref/OSI_Layers.asp for further reference.

#### 2.3 Simplification of OSI and Relating Motivation
The complicated seven-layer OSI model was simplified to a four-layer structure.
Basically, some similar functioning layers are combined, </br>
1. Network Layer: data transmitted into devices </br>
2. Internet Layer: IP header, routing information </br>
3. Transport Layer: TCP/UDP, data flow </br>
4. Application Layer: interfaces </br>

These four-layer structure forms the consisting TCP/IP protocols,
which greatly simplifies programming efforts. (less "rigorous")
With the addition of WWW and E-mail, this has become our current Internet structure.

## Topic 3 -- Transmission Control Protocol (TCP)
> Opening Questions: </br>
> How to define the way of communication?
> What's a "packet"?
> What information is needed for the packages to be transferred to the correct destinations?

#### 3.1 Three-Way Handshake
How's data transmitted from one place to another? Definitely, the source and destination "address" is needed.
(the concept of "address" will be clear when we talk about IP) 
Some additional controling codes are also needed for advanced functionalities.
Furthermore, when the data is transferred from one place to another,
there will definitely be some bits being contaminated, i.e., revesed or even missing.
As a result, some correcting mechanisms should be implemented inside the packet.
These additional bits resembles the concept of Error Correcting Codes (ECC),
more on ECC: http://www.qrstuff.com/blog/2011/12/14/qr-code-error-correction .
For more information about the bits added, please google "TCP Header".

Three way handshake is the concept of data transfer based on "both aggreement".
One initiates the sending request with a specific "Sequence Numner".
Then the server will send a packet with special bits added and a new Sequence Number embedded back to the user.
If the user send another packet back to the server and it's received by the server, connection's established.

#### 3.2 User Datagram Protocol (UDP)
UDP is faster in terms of data transfer since it does not have sever/response check.
This is applicable in LIVE media streams.

#### 3.3 (optional) Sockets
Here comes the interesting part. Once you set up your own server on your PC/laptop,
you can try out "BSD Unix Socket": https://en.wikipedia.org/wiki/Berkeley_sockets .
Some other comparision between TCP, Sockets, and Internet Sockets (not really that important):
http://stackoverflow.com/questions/22897972/unix-vs-bsd-vs-tcp-vs-internet-sockets .
You can use socket to build your own chat room!
Here are the facts that you need to know:
* two programs needed: one as client and the other acts as server
* programming language used: C/C++, Java, PHP, etc.
* to construct multi-user server, you need to know mutex and pthread (for example, in C)
To start chatting, you need to specify the IP address and the port that the server will listen to (to be discussed),
and transfer data by pairs of read() and write(). Here's some code abstracted from my project:

Server.c (return 1 on error for now)
```
	// creating TCP socket
	iSockFD=socket(AF_INET,SOCK_STREAM,0);
	if (iSockFD<0)  return 1;

	setsockopt(iSockFD,SOL_SOCKET,SO_REUSEADDR,(const char*)&n,sizeof(n));
	memset((char*)&sLocalAddr,0,sizeof(sLocalAddr));
	sLocalAddr.sin_family=AF_INET;
	//sLocalAddr.sin_len=sizeof(sLocalAddr);
	sLocalAddr.sin_port=htons(5050);
	sLocalAddr.sin_addr.s_addr=htonl(INADDR_ANY);
	iAddrSize=sizeof(sLocalAddr);

	// binding to Server
	iStatus=bind(iSockFD,(struct sockaddr*)&sLocalAddr,iAddrSize);
	if (iStatus<0)  return 1;
	//printf("Bind Success\n");

	// start listening to port 5001
	iStatus=listen(iSockFD,20);  // 5 or SOMAXCONN
	if (iStatus!=0)  return 1;
	printf("Listening to Port 5050\n");
```

For beginners, it's better to start with PHP sockets since they're much easier: 
http://php.net/manual/en/book.sockets.php .

## Topic 4 --  Hypertext Transmission Protocol (HTTP) and HTTPS
> Opening Questions: </br>
> What's the difference between HTTP and HTTPS? </br>
> What is 80/8080 port? </br>

#### 4.1 Introduction to HTTP
This protocol was established to improve scientific research, and it belongs to the application layer.
Detail information: https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol .

#### 4.2 Ports Commonly Used
What is port: https://en.wikipedia.org/wiki/Port_(computer_networking) .
* 80: HTTP
* 8080: tomcat likes it (?)
* 20, 21: FTP

More on port numbers: http://www.webopedia.com/quick_ref/portnumbers.asp .

#### 4.3 Localhost
Localhost represents the computer/server itself with IP address 127.0.0.1. 
If you're familiar with SQL-PHP manipulations, then you must have seen it before.

## Topic 5 -- Internet Protocol (IP)
> Opening Question: </br>
> What is IP? And why we need IPv6? </br>
> What does those number sequences set in 網路共和中心 mean when I applied for 宿網 ? </br>
> What's the difference between "http://www.google.com.tw" and "74.125.203.94"? </br>
> Do I have IP when I use WiFi in the MRT station? </br>

#### 5.1 IPv4 and IPv6
IPv4 is a 32-bit sequence, representing a specific device connected to the Internet. 
We ususally divide them into four segments, and represent them in decimals, e.g. 140.114.24.31.
IPv6 has more bits (128 bits) than IPv4, pointing out the dramatic increase of web-connected devices,
including laptops, smart phones, and even Internet of Things (IoT).

We can Imagine IP as your home address. We divide IP into "classes": </br>
1. Class A:   0.xxx.xxx.xxx </br>
2. Class B: 128.xxx.xxx.xxx </br>
3. Class C: 192.xxx.xxx.xxx </br>
4. Class D: 224.xxx.xxx.xxx </br>
5. Class E: 240.xxx.xxx.xxx </br>
We now are able to go on for other facts. 

#### 5.2 Domain
Domain acts as the size of your house, many people (IPs) live inside.
For instance, we're using IPs starting with 140.114.

#### 5.3 Netmask
This is the most amazing part in IP division.
Netmask can divide IPs in a certain domain into smaller parts, according to user needs.
We can divide the whole IP address into two parts: NetID and HostID.
* NetID = IP address & Netmask: smaller room separated inside a certain house (domain)
* HostID = IP address & (^Netmask): number of students (IP) in this dorm (subnet)

However, we need "broadcasting IP" and "server IP" in every subnet,
so the minimum size of HostID is 2 bits. More about IP broadcasting will be discussed in later sections.
If you are really interested in this topic, please visit: http://linux.vbird.org/linux_server/0110network_basic/0110network_basic-centos4.php#ipandmac_netmask .

#### 5.4 Gateway/Router
Gateway/Router is your front door, connecting your house to the outside world.
Usually a "switch" is utilized to make full and efficient use of the IPs.
Some issues relating to broadcasting is also done with the help of routers.

#### 5.5 Domain Name Server (DNS)
You will probably ask, "Do people really memorize those IP address and then get access to the website?".
Well, you can just type "www.google.com.tw" to get there instead of typing "74.125.203.94".
Thanks to DNS, they do the interpretation from words to IPs.

#### 5.6 Dynamic Host Configuration Protocol (DHCP)
Whenever you get your device connected to the Internet, it must have an IP.
Imaging in free WiFi zone somewhere inside the MRT station, 
if we only divide the subnet such that only 6 people (3-bit HostID) can have access to the WiFi router,
and now I have the 7th person wanting to connect to the WiFi too, what should we do?
Don't worry, we can dynamically allocate IPs: http://linux.vbird.org/linux_server/0340dhcp.php#theory .

## Topic 6 -- Netwrok Hardwares
#### 6.1 Switch/Hub/Router
#### 6.2 Sample Network Structure: as a Company

## Topic 7 -- Other Relating Topics
#### 7.1 Multiple Sense Multiple Access with Collision Detection (CSMA/CD)
#### 7.2 (Reverse) Address Resolution Protocol (RARP/ARP)
#### 7.3 Internet Control Message Protocol (ICMP)
