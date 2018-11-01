---
title: SomeStuff
---

# Networking
**Networking** (n): the establishment or use of a computer network.
## Why isn't this normal DMX?
Well, normal DMX is what the light board uses to communicate with intelligent light fixtures. This would involve going from one of the two DMX outputs on our ETC Ion light board to some DMX fixtures, possibly through the intermediary of an opto or other DMX device.

This is different from what we're doing here in a very important way: In the first case, the board is directly outputting DMX and the fixtures are receiving the DMX from the board. Here is a terrible drawing of normal dmx:
![my image](/assets/networking_dmx_only.png)

In the second case, using ethernet to communicate between the board and the sACN box, and the sACN box outputs the DMX rather than the board. Instead, the board tells the sACN box what addresses to turn on or off over the same protocols that most computer networks use, called "the tcp/ip protocol stack." Wired networks at home use this, and so do wifi networks.

This is totally different from normal DMX cabling and we need to think of them as totally separate concepts. There is almost zero crossover in knowledge from one to the other. So, that's why you need to know about it and why I'm writing this thing.

## What's the TCP/IP protocol stack? Heck, what's the internet?

The TCP/IP protocol stack is a set of protocols by which computers on the internet talk to eachother.
