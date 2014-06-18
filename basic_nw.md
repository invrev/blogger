What happens when u try to connect from your home to internet  
DHCP  
Process:  
1.request encapsulated in UDP,then in IP, then in 802.1 Ethernet  
2.Ethernet frame broadcast to (dest: FFFFFFFFFFFF ) on LAN,  
3.received at router running DHCP server  
4.DHCP server formulates DHCP ACK with <Output>  
encapsulation at DHCP server, frame forwarded (switch learning) through  
LAN, demultiplexing at client.  
Output:  
1.IP address for self client  
2.name & addr of DNS server  
3.IP address of its first-hop router  
  
ARP  
Process:  
ARP query :  
broadcast,received by router.  
Output:  
ARP reply:  
MAC address of router interface.  
  
DNS  
Process :  
IP datagram routed in intranet (RIP, OSPF, IS-IS and/or BGP routing protocols)and internet  
Output :  
IP address of destination server  
  
TCP :  
Process:  
3 way hand shake to server  
Ouput :   
connect to destination server   
  
HTTP (req and reply)  
  
How to send data from end to end: two switching  
methods   
Circuit switching (eg.ISDN)  
Packet switching (e.g. ATM, X.25, Frame Relay, Internet)  
  
Sharing a link : Multiplexing  
To combine multiple signals (analog or digital) for  
transmission over a single line or medium.  
  
E2E (End to End) design principle  
Application-specific functions ought to reside in the end hosts of a network rather than in intermediary nodes – provided they can be implemented "completely and correctly" in the end hosts.  
  
Mux Technologies :  
1.Frequency Division Multiplexing (FDM) : each signal is  
assigned a different frequency range (e.g. FM radio).  
2.Time Division Multiplexing (TDM) : each signal is  
assigned a fixed time slot in a “fixed” rotation.  
3.Statistical Time Division Multiplexing (STDM): time  
slots are assigned to signals dynamically to make better  
use of bandwidth.  
4.Wavelength Division Multiplexing (WDM) : each signal  
is assigned a particular wavelength; used in optical fiber.  
  
Service  
The set of operations provided by the lower layer to  
the upper layer to perform a service  
Example:   
Connection-oriented services:  
connect, send, receive, disconnect  
Connectionless services:  
send, receive  
  
Protocol  
algorithms to implement functions provided by service  
  
Diff Types of protocols  
1.Public protocol  
HTTP for web server and client, SMTP for email clients and server  
BitTorrent,P2P  
2.Proprietary protocol  
Real,Kazza,Skype  
  
Service Access Point  
How do two processes on two computers identify  
themselves to each other ?  
Answer: use a triple  
(protocol, ip_address, port_number) = socket  
e.g. (TCP, 192.168.0.1, 80)  
(Actually a socket is a quintuple, more later)  
In general: each entity of a layer access lower layer’s  
services via Service Access Points  
  
Application(HTTP,telent,DNS,SMTP)  
Supports Network Applications  
Transports applications’ messages  
  
Transport (TCP,UDP,ATM AAL)  
TCP: connection-oriented, reliable  
UDP: connectionless, unreliable  
  
Network(IP,ATM layer)  
Routes data packets from hosts to hosts  
IP: Internet Protocol, and many routing protocols  
  
Data link(CSMA/CD,ATM physical,PPP)  
Deals with algorithms to achieve reliable, efficient  
communication between two adjacent machines  
  
Physical(raw bits)  
Moves raw bits (0/1) between adjacent nodes  
depending on the physical medium used  
  
TCP   
1.Establish connection: 3-way handshake  
2.Data transmission  
  *Byte-stream service  
  *Reliable (retransmission with timer)  
  *In-order delivery (reorder packets if necessary)  
  *Support flow control (fast sender vs slow receiver)  
  *Full-duplex (data transferred both ways)  
3.Close connection  
  
connect : service  
3-way handshake : Protcol  
  
Read/Write : service  
Send Data realiablly and in-order: protcol  
  
how to calculate time required to establish tcp connection ?  
how to determine to which remote process I am communicating ?  
Ans : Socket pair , quadruple (local_IP,  
local_port, remote_IP, remote_port) must be unique  
The quadruple is also called a socket pair  
  
At a time of connection establishment  
Allowing each side to know the other exists  
  
Negotiation of optional parameters   
#Max segment size  
#Initial Sequence Numbers (ISN)  
  
Triggering allocation of transport entity resources  
#Buffer  
#Timers (if any)  
  
Problems  
HAlf-open Connection  
Symptoms :   
- One end quits w/o the knowledge of the other  
 - For example, you turn off your PC while a telnet is  
still on, or your OS freezes and you have to reboot  
  
Solution  
Timing out alone does not work (look at a web browser)  
TCP has the keep alive option  
RST is used to  
Reply to connection requests to some port no-one is  
listening on  
Reply to connection requests within 2MSL after crashing  
In UDP, an ICMP port unreachable is generated  
instead  
  
TCP/IP use big-endian for all its integers   
Serious run-time performance penalties occur when  
using TCP/IP on a little endian processor.  
Thus, it may be unwise to select a little endian  
processor for use in a device, such as a router or  
gateway, with an abundance of network  
functionality.  
  
  
DNS   
Domain Name System  
Distributed database system  
information about names in the domain  
name space  
Maintaining a many-to-many mapping between  
domain name space and IP address space  
Realized by name servers  
  
Domain and Domain name  
domain is a subtree  
domain name is a node in the tree, may point to  
Network addresses (IP address)  
Hardware information  
Mail routing information  
Information about the domain rooted at that node  
  
Name servers are programs storing info. about the  
domain name space, answering queries on it  
  
To query the DNS USE   
dig buffalo.edu a  
dig buffalo.edu cname  
dig buffalo.edu mx  
dig buffalo.edu ns  
  
It gives Resource record with key and value  
Type = A  
Key : hostname  
value : IP address  
  
Type = cname  
Key : domain name    
value : authoritative name server  
  
  
TCP State Diagram  
Channel bit errors require  
Error detecting codes  
Receiver feedback (ACK/NAK)  
Retransmissions (when NAK received or ACK/NAK corrupted)  
  
Retransmissions introduce duplicates  
Need sequence numbers  
  
  
Packet loss requires  
Timeout + retransmission (again introduce duplicates)  
Estimating the “right” timeout is a fundamental problem!  
  
Pipelining improves utilization + throughput  
Needs to enlarge sequence number space  
Needs more buffer space at both sender & receiver  
ACK + retransmission strategies: Go-Back-N & Selective Repeat  
Window size & sequence number range strongly related  
  
  
EXtensions to TCP  
Selective acknowledgements: TCP SACK  
Explicit congestion notification: ECN  
Delay-based congestion avoidance: TCP Vegas  
Discriminating between congestion losses and other losses: cross-layer signaling and guesses  
Randomized drops (RED) and other router-based mechanisms  
  
TCP  
1.Multiplexing and Demultiplexing  
2.Byte-stream service  
Stream of bytes sent and received, not stream of packets  
3.Reliable data transfer  
A combination of go-back-N and selective repeat, and  
performance tuning heuristics  
4.Connection management  
Connection establishment and tear down  
5.Flow control  
Prevent sender from overflowing receiver  
6.Congestion control  
General principles & How TCP does it  
  
AODV:  
Distance vector : count to infinity  
Link state : only link information sharing ,scalable  
AODV : Avoids count to infinity problem :   
Count to infinity : takes infinte ammount of time to converge when topology chages or link breaks  
solution : use AODV that uses PREQ an RREP messges and PERROR when link breaks or topology changes  
Runs periodically   
Unique seq number to avoid flodding of packets in network.  
