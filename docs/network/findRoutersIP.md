# Get IP of Router

This document explains how to obtain the IP address of a router using three different commands in a Linux-based system: `route -n`, `ip route show`, and `netstat -rn`.

## Table of Contents
- [Introduction](#introduction)
- [Commands](#commands)
  - [route -n](#route--n)
  - [ip route show](#ip-route-show)
  - [netstat -rn](#netstat--rn)
- [Examples](#examples)
- [Troubleshooting](#troubleshooting)

## Introduction

In networking, it's often necessary to determine the IP address of your router. The router's IP address is typically the default gateway for your local network. This README explains how to use three different commands to find this information on a Linux-based system.

## Commands

### route -n

The `route -n` command displays the routing table of your system. The `-n` flag ensures that the addresses are shown in numeric format rather than resolving hostnames.

#### Syntax
```bash
route -n
```
Explanation

- Destination: The destination network or IP address.
- Gateway: The gateway address, which is your router's IP.
- Genmask: The subnet mask for the destination network.
- Flags: Various flags indicating the route's status (e.g., U for up, G for gateway).
- Iface: The interface over which the destination is reachable.

ip route show

The ip route show command is part of the iproute2 package and displays the current routing table.
Syntax

```bash
ip route show
```
Explanation

- The output shows routes to various networks.
- The line starting with default via indicates the default route, pointing to your router's IP address.

netstat -rn

The netstat -rn command also displays the routing table in numeric format. netstat is a versatile networking tool.
Syntax

```bash
netstat -rn
```
Explanation

- Similar to route -n, the output includes Destination, Gateway, Genmask, Flags, and Iface.
- The Gateway column will show the router's IP address for the default route.

Examples
route -n Example

```bash
$ route -n
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
0.0.0.0         192.168.1.1     0.0.0.0         UG    100    0        0 eth0
192.168.1.0     0.0.0.0         255.255.255.0   U     0      0        0 eth0
```
In this example, 192.168.1.1 is the router's IP address.
ip route show Example

```bash
$ ip route show
default via 192.168.1.1 dev eth0
192.168.1.0/24 dev eth0 proto kernel scope link src 192.168.1.100
```
Here, 192.168.1.1 is the default gateway, which is the router's IP address.
netstat -rn Example

```bash
$ netstat -rn
Kernel IP routing table
Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface
0.0.0.0         192.168.1.1     0.0.0.0         UG        0 0          0 eth0
192.168.1.0     0.0.0.0         255.255.255.0   U         0 0          0 eth0
```
Again, 192.168.1.1 is identified as the router's IP address.
Troubleshooting

- No default route: If there is no default route in the routing table, the device may not be properly connected to a network, or the network configuration may be incorrect.
- Permission denied: Running these commands might require root or sudo privileges. Try prepending sudo to the command, e.g., sudo route -n.
- Command not found: Ensure that the net-tools package (for route and netstat) and iproute2 package (for ip route show) are installed on your system.
