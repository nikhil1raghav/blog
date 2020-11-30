+++
title="Sockets"
date="2020-10-26"
+++
In UNIX everything is a file, i.e. when programs do any kind of I/O they do it by reading or writing to a file descriptor. But when a program has to communicate with some file over internet it uses a socket descriptor using `send()` and `recv()`.

### Types of Sockets
* SOCK_STREAM (Stream Sockets)
* SOCK_DGRAM (Datagram Sockets)
* Others which I don't know yet

### SOCK_STREAM
- Data is shared in a sequential and error-free manner.
- Uses TCP to ensure data integrity.

### SOCK_DGRAM 
- Slap an IP header on a data packet and send it out.
- Also called __connectionless sockets__ as there is no need to maintain open connections.
- Uses UDP(User datagram protocol) for transfer, faster than TCP as it doesn't ensure the sequence and there is no problem if some packets get lost in between. Used when TCP is not available.
- Used in games, videoconferencing, tftp etc. but they also use their own protocol along with UDP.
- In tftp to prevent packets loss at receiver's end, recipient has to send and `ACK` an acknowledgement packet for every packet it receives, if sender doesn't receives an `ACK` in a fixed interval of time it sends the packet again.
