# Is it all just 1s and 0s? 
The goal of a signal line/wire is to allow some form of communication between two devices. There are a multitude of ways to communicate via a single wire, and even more ways when more a single wire is available.

In digital circuits, our communication medium will also be digital. This means that both the sending and the receiving end can only communicate via 2 states, low or high. As such, both sender and receiver needs to be aware of how they are going to be communicating over this line. This is called a **communication protocol**. 

# Serial 
As you may expected, there are lots of different types of communication protocols, but the most fundament (in my opinion) of all of them is serial communication, also referred to as UART (Universial Asynchronous Receiver-Transmitter). 

It consists of 2 wires, excluding ground. It has a receiver and transmit wire, RX and TX for short, and is wired up as shown in the diagram below: 
![UART_wiring_image](https://www.embedded.com/wp-content/uploads/2021/01/01adi_f01.jpg)
Image courtesy of embedded.com 

A key part of any communication protocol is the data transmission packet; how is the message structured? In human languages, we have grammar rules and punctuation to help us. In communication protocols, the data transmission packet helps in this regard. 

![UART_packet](https://www.embedded.com/wp-content/uploads/2021/01/01adi_f03.jpg)
Image courtesy of embedded.com

The data you want to send across will fit in the data frame. The start bit and stop bits are to signal the start and end of the packet, while the [parity bit](https://en.wikipedia.org/wiki/Parity_bit) is used for error detection.

Now that we have a way to structure our message, the final piece of the puzzle is still missing; how do we what is a bit? Both devices have no common reference point and have no way of knowing when to start or stop reading for a bit. For example, if I were to send 4 1s in a row, how would the receiving end know it received 4 1s and not a single 1? 

This is where the bit rate of the line comes in. If both receiver and transmitter are aware of the bit rate of the line, they know how often to send or check for a bit. 

> In UART, bit rate is commonly referred to as baud, in symbols per second. In digital communication lines, such as UART, baud = bit rate as the number of symbols in a digital line is 2: 1 and 0. If you want to learn more about UART or are still confused, I highly recommend this [video](https://www.youtube.com/watch?v=IyGwvGzrqp8).

# Communication protocol terminology
Communication protocol have the following common characteristics: 
- Synchronous: Does the protocol use a clock? 
- Duplex, Half-Duplex: How many nodes (devices) can transmit information on the same line at the same time? 
- Master-Slave or Peer-to-Peer: Does a single device control the communication line, or are all devices equal?
- Differential signalling: Is [differential signalling](https://en.wikipedia.org/wiki/Differential_signalling) being used? 
> Understanding what these characteristics mean and how they could be implemented can provide quick insight in to the functionality of the underlying protocol. 



