# Nmap

Nmap is a powerful network scanning tool used for network discovery and security auditing. Here is a guide to installing and using Nmap and its associated tools.

### Other Tools of Nmap

- **ncrack**: Network authentication cracking tool.
- **ncat**: Versatile command-line networking utility.
- **nping**: Network packet generation tool.
- **zenmap**: Graphical user interface for Nmap.
- **man-nse**: Manual for Nmap Scripting Engine.

### Installation

Follow these steps to install Nmap and its dependencies:

1. Install dependencies:
```sh
sudo apt install libssl-dev autoconf make g++ subversion
```

## Nmap

Nmap is a powerful network scanning tool used for network discovery and security auditing. Here is a guide to installing and using Nmap and its associated tools.

### Other Tools of Nmap

- **ncrack**: Network authentication cracking tool.
- **ncat**: Versatile command-line networking utility.
- **nping**: Network packet generation tool.
- **zenmap**: Graphical user interface for Nmap.
- **man-nse**: Manual for Nmap Scripting Engine.

### Installation

Follow these steps to install Nmap and its dependencies:

Install dependencies:
```sh
sudo apt install libssl-dev autoconf make g++ subversion
```

Check out the Nmap source code:

```sh
svn co https://svn.nmap.org/nmap/
```
Navigate to the Nmap directory:

```sh
cd nmap
```
Configure the build system (for more options, use ./configure --help):

```sh
./configure
```
Install setuptools for Python:

```sh
sudo pip install setuptools==62.0.0
```
Build and install Nmap:

```sh
sudo make install
```
Launch Zenmap:

```sh
cd zenmap
sudo ./zenmap
```
## Basic Nmap Usag
Check Nmap version:

```sh
nmap -V
```

Scan a single IP address with verbosity:

```sh
nmap -v 192.168.13.4
nmap -vv 192.168.13.4
```
Scan multiple IP addresses:

```sh
nmap 192.168.13.4
nmap 192.168.13.1 192.168.13.4 192.168.13.10
```
## Advanced Nmap Usage

CIDR Notation: Scan a subnet.

```sh
nmap 192.168.56.4/24
```
Range of IPs:

```sh
nmap 192.168.13.1-111
```
Input from File:

```sh
nmap -iL filename.txt
nmap -F -iL ip.txt
```
Exclude Specific Targets:

```sh
nmap 192.168.13.1 192.168.13.2 192.168.13.4 --exclude 192.168.13.4
nmap -F 192.168.13.0/24 --excludefile ip.txt
```
Specify Network Interface:

```sh
nmap -e wlan0 192.168.13.4
```
IPv6 Scanning:

```sh
nmap -6 {IPv6 targets}
```
Random Internet Hosts:

```sh
nmap -iR 3
```
Display Open Ports:

```sh
nmap --open 192.168.13.4
```
Packet Trace:

```sh
nmap --packet-trace 192.168.13.4
```
Fast Scan:

```sh
nmap -F 192.168.13.4
```
Specific Ports:

```sh
nmap -p 139 192.168.13.4
nmap -p 80,139,50-1000 192.168.13.4
nmap -p "*" 192.168.13.4
```
UDP and TCP Ports:

```sh
nmap -sU -sT -p U:53, T:25 192.168.13.4
```
Top Ports:

```sh
nmap --top-ports 10 192.168.13.4
```
Scan without Randomization:

```sh
nmap -r 192.168.13.4
nmap -v -r 192.168.13.4
```
## Foundational Scanning Techniques

No Ping Scan:

```sh
nmap -PN 192.168.13.4
```
Ping Scan:

```sh
nmap -sP 192.168.13.4
nmap -sP 192.168.13.0/34
```
TCP SYN Ping:

```sh
nmap -PS 192.168.13.4
```
TCP ACK Ping:

```sh
nmap -PA 192.168.13.4
nmap -PA 433 192.168.13.4
```
UDP Ping:

```sh
nmap -PU 192.168.13.4
nmap -PU 80 192.168.13.4
```
SCTP Init Ping:

```sh
nmap -PY 192.168.13.4
nmap -PY 433 192.168.13.4
```
ICMP Echo Ping:

```sh
nmap -PE 192.168.13.4
```
### References

[Nmap Download](https://nmap.org/download.html)<br />
[Nmap Port Scanning Basics](https://nmap.org/book/man-port-scanning-basics.html)
