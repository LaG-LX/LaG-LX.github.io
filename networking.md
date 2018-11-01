---
layout: default
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

The TCP/IP protocol stack is a set of protocols by which computers on the internet talk to eachother. It relies on 2 different addresses, your **MAC address** and your **IP address**.

### What's a MAC address?

A MAC address is a unique identifier that every network interface has, be it the etherent port in the light board or the wifi chip in your laptop or the antenna in your wifi router or the ethernet port in your computer. It looks something like ba:d7:57:16:49:e7. It's a set of randomly generated hexidecimal numbers which is unique to every networking device created. This is also called the hardware address.

This address is used for TCP, the lowest level of the TCP/IP stack. Most of the time, you won't need to ever care about this, but it's important for learning about IP addresses and DHCP.

**TL;DR**

MAC addresses are a way to uniquely identify any wireless interface. They only matter for assigning IP addresses. They are used in TCP.

### What's an IP address?

An IP address is the address that you will be using for the most part. It is used for the IP part of the TCP/IP stack. This is the layer that you'll be interacting with most. IP addresses look like this: 231.34.1.34. It will be 4 numbers less than 255 separated by periods.

Typically, an IP address is hierarchical. This means that each segment of the IP address represents a layer of the network. The most significant layer is on the left, least significant on the right.

## How do things get IP addresses?

There are two ways a device on a network can get an IP address. It can either claim an address, or be assigned one.

When a device claims an IP address, that's called a "Static IP." These can be useful, but they can also cause issues. For example, if your network is using 123.45.67 and the device assigns itself 98.76.54.32, it likely won't be able to communicate with the rest of the network.

I recommend using a "Dynamic IP." This means that something has to exist on the network called a DHCP server. This DHCP server assigns IP addresses to devices in a way which ensures that all the addresses will start with the same set of segments and that no two devices will attempt to claim the same IP address.

To learn about how to apply these ideas to the ETC Ion, see [Ion networking](/ion_networking).
