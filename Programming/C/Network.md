
### Transport Layer

Protocols (TCP, UDP, etc.) that provide services: 
- delivery to applications
-  connected or not
- same or different order delivery
- reliability or unreliability
- flow control



| TCP| UDP |
|--- |--- |
| **Stream** oriented | **Datagram** oriented|
|Connected|Not connected|
|Acknowledgement|No reception check|
|Retransmissions|Fire and forget|
|Packets ordering|No ordering|
|Timeouts| 

---


### Ports
 - ports are 16 bit undigned integer (from 0 to 65,535)
 - All TCP/UDP communications use ports
 - A connection is identified by the double pair ` (IP1,port1),(IP2,port2)) `
 - Port 80 is used for HTTP

