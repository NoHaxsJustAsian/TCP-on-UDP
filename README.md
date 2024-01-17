*Tunwa Tongtawee & Joseph Pierre-Louis - CS3700 - 03/11/2024*
# Project 4 - Reliable Transport Protocol

## Introduction
In Project 4 for our CS3700 course, we've developed a reliable transport protocol on top of UDP, akin to TCP. The goal is to reliably transfer files between two nodes (a sender and a receiver) over an unreliable network, ensuring data delivery is in order, without duplicates, missing data, or errors.

## Project Overview

Our implementation comprises two main components:
1. **3700send:** A sending program that accepts data from STDIN and sends it across the network.
2. **3700recv:** A receiving program that captures data sent by 3700send and prints it to STDOUT in the correct order and without errors.

Both programs use UDP as the underlying transport layer protocol and include custom mechanisms for packet handling and acknowledgements.

### Key Features

- **Custom Packet Format:** We designed our own packet format with fields for packet type, acknowledgment number, advertised window, and data.
- **Reliable Data Transmission:** Implemented algorithms to ensure reliable transmission over UDP, handling dropped, duplicated, and delayed packets.
- **Flow and Congestion Control:** Incorporated mechanisms similar to TCP to manage flow control and congestion, optimizing for network conditions.
- **Error Checking:** Added robust error-checking to ensure the integrity of each packet received.

## Usage

To use our reliable transport protocol, run the sending program and the receiving program on two separate machines or processes:

1. **Starting the Receiver:**
   ```bash
   
   $ ./3700recv
   ```
2. Starting the Sender:
```bash
$ ./3700send <recv_host> <recv_port>
```

Replace <recv_host> and <recv_port> with the appropriate values for the receiving machine.
## Testing Environment

We utilized a network simulator provided by the course to test our protocol under various network conditions, including packet loss, delay, and reordering. The simulator emulates an unreliable network environment to validate the reliability and efficiency of our transport protocol.

## Performance and Optimization

- **Efficiency:** Our protocol is designed to minimize the overhead, reducing the amount of data exchanged over the network.
- **Speed:** We optimized our algorithms to require minimal time to transfer files under different network conditions.

## Future Enhancements

- Further optimization for high-latency networks.
- Improved algorithms for dynamic network conditions.

## Acknowledgments

- Professor Alden Jackson and TAs of the CS3700 course for their guidance and support.
- Northeastern University for providing the resources and environment conducive to practical learning in networks and distributed systems.

---

*Note: This project was developed for educational purposes, aiming to demonstrate the design and implementation of reliable transport protocols over unreliable networks.*

