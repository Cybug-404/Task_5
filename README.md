# # Task_5 Packet Analysis

## 🔍 Objective
 Capture live network packets and identify basic protocols and traffic types.

## 🛠 Tools Used
- Wireshark
- Linux (OS)
- Firefox (Browser)

## 🧪 Steps Performed
1. Installed Wireshark from **https://www.wireshark.org/**
2. Enabled packet capture mode on the interface
3. ping 8.8.8.8
4. Open youtube.com
5. Analyzed http, tcp, dns, icmp protocols
6. Saved the packet to a .pcapng file

## 📊 Output
- Packet information of my personal internet browsing
- Sending and receiving of frames
- Three-way handshake (SYN-ACK)
- Four-Way handshake (FIN-ACK)

  ## 🧠 Learnings

  # Youtube.com
  - DNS Query and Response:
    1) Browser first needs to find the IP address of youtube.com. First checks the cache for availability. If not available, then it sends a DNS (Domain Name System) query to your configured DNS server.
    2) DNS server responds with the IP address(es) associated with youtube.com (UDP)

  - TCP Three-Way Handshake (SYN, SYN-ACK, ACK):
    1) Initiates a TCP (Transmission Control Protocol) connection to YouTube's server on port 443 (for HTTPS) 
    2) Browser sends a SYN packet to the YouTube server (SYN)
    3) YouTube server responds with a SYN-ACK packet, acknowledging the SYN and sending its own SYN
    4) browser sends an ACK packet back to the server, completing the three-way handshake and establishing a reliable TCP connection.

  - TCP Four-Way Handshake (Transport Layer):
    1) Close the end of the connection, sends a TCP segment with the FIN flag set to the YouTube server.
    2) YouTube server receives the client's FIN and acknowledges it by sending a TCP segment with the ACK flag set
    3) YouTube server is also finished sending any remaining data to your browser; it sends its own TCP segment with the FIN flag set. This indicates that the server is now finished sending data.
    4) Browser receives the server's FIN and acknowledges it by sending a final TCP segment with the ACK flag set.
    5) After sending the final ACK, the client typically enters a TIME_WAIT state for a brief period (usually twice the maximum segment lifetime, or 2MSL).

 # ping 8.8.8.8
   - ICMP Echo Request Generation:
     creates a small data packet, specifically an ICMP Echo Request message. Includes sequence number (to keep track of the requests) and an identifier. It often contains a small amount of "payload" data.
   - Packet Transmission:
      ICMP Echo Request packet is encapsulated within an IP. Sends this packet aiming for the destination IP address you specified.
   - Routing Through the Network:
     The packet travels through various network devices, such as routers and switches, across the Internet. Each router that forwards the packet decrements its "Time To Live" (TTL) value. If the TTL reaches zero       before reaching the destination, the packet is discarded, and an ICMP "Time Exceeded" message is sent back to the source.
   - Destination Host Receives Request:
     If the target host is reachable and online, it receives the ICMP Echo Request packet.
   - ICMP Echo Reply Generation:
     Upon receiving the Echo Request, the target host generates an ICMP Echo Reply message. This reply packet typically contains the same payload data that was sent in the request, along with the sequence number.
   - Reply Packet Transmission:
     The ICMP Echo Reply packet is then encapsulated in an IP packet and sent back to your computer along the reverse path.
   - Reply Receipt and Analysis:
     The system receives the ICMP Echo Reply.






  
