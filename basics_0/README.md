# holbertonschool-network

# Network Basics for Web Developers

## Sommaire
- [holbertonschool-network](#holbertonschool-network)
- [Network Basics for Web Developers](#network-basics-for-web-developers)
  - [Sommaire](#sommaire)
  - [Learning Objectives](#learning-objectives)
    - [1. OSI Model](#1-osi-model)
    - [2. What is a LAN?](#2-what-is-a-lan)
    - [3. What is a WAN?](#3-what-is-a-wan)
    - [4. What is the Internet?](#4-what-is-the-internet)
    - [5. What is an IP address?](#5-what-is-an-ip-address)
    - [6. What is localhost?](#6-what-is-localhost)
    - [7. What is a subnet?](#7-what-is-a-subnet)
    - [8. Why was IPv6 created?](#8-why-was-ipv6-created)
    - [9. TCP/UDP](#9-tcpudp)
    - [10. What is a port?](#10-what-is-a-port)
    - [11. Common Protocols Every Web Developer Should Know](#11-common-protocols-every-web-developer-should-know)
    - [12. DNS Basics](#12-dns-basics)
    - [13. HTTP and HTTPS](#13-http-and-https)
    - [14. What tool/protocol is often used to check if a device is connected to a network?](#14-what-toolprotocol-is-often-used-to-check-if-a-device-is-connected-to-a-network)
  - [Conclusion](#conclusion)

## Learning Objectives
This document provides an in-depth look at essential networking concepts every web developer should understand.

### 1. OSI Model
+ **What it is:** A conceptual model that standardizes communication functions of a network in seven layers.
+ **How many layers it has:** Seven layers.
+ **How it is organized:**
  1. **Physical:** Manages hardware connections and transmission of binary data.
  2. **Data Link:** Handles data frames and error detection (Ethernet, MAC).
  3. **Network:** Routes packets across networks (IP).
  4. **Transport:** Ensures reliable transmission (TCP, UDP).
  5. **Session:** Manages sessions between applications.
  6. **Presentation:** Translates data formats (encryption, compression).
  7. **Application:** Interfaces for end-user services (HTTP, FTP).
+ **Example:** A user accessing a website involves interaction across all seven layers, from sending HTTP requests (Application layer) down to physical transmission over a network cable (Physical layer).

### 2. What is a LAN?
+ **Definition:** A Local Area Network (LAN) connects devices within a small geographical area.
+ **Typical usage:** Offices, homes, schools.
+ **Typical geographical size:** A few meters to a few kilometers.
+ **Example:** Devices connected to the same Wi-Fi router.
+ **Key point:** LANs usually use Ethernet or Wi-Fi.

### 3. What is a WAN?
+ **Definition:** A Wide Area Network (WAN) connects multiple LANs over long distances.
+ **Typical usage:** Connecting branch offices of a company.
+ **Typical geographical size:** Can span cities, countries, or continents.
+ **Example:** The Internet.
+ **Key point:** WANs often use leased lines or satellite links.

### 4. What is the Internet?
+ **Definition:** A global network of interconnected LANs and WANs using standardized protocols like TCP/IP.
+ **Example:** Browsing a website hosted in another country.
+ **Key point:** The Internet is based on open protocols.

### 5. What is an IP address?
+ **Definition:** A numerical label assigned to each device on a network.
+ **2 types of IP addresses:**
  - **IPv4:** 32-bit address (e.g., 192.168.0.1).
  - **IPv6:** 128-bit address (e.g., 2001:0db8::1).
+ **Example:** A server with IP 203.0.113.45.
+ **Key point:** IPv6 solves the problem of IPv4 address exhaustion.

### 6. What is localhost?
+ **Definition:** A special hostname that refers to the current machine (IP: 127.0.0.1 for IPv4, ::1 for IPv6).
+ **Example:** Running a development server locally.
+ **Key point:** Localhost is useful for testing and development.

### 7. What is a subnet?
+ **Definition:** A portion of a network that shares a common address prefix.
+ **Purpose:** Subnetting improves network organization and security.
+ **Example:** A network with IP range 192.168.1.0/24.
+ **Key point:** Subnet masks (e.g., 255.255.255.0) define the subnet.

### 8. Why was IPv6 created?
+ **Reason:** To overcome the limitations of IPv4, mainly address exhaustion.
+ **Key point:** IPv6 provides a larger address space and better routing.

### 9. TCP/UDP
+ **Definition:** Transport layer protocols for data transmission.
+ **Main difference:**
  - **TCP:** Reliable, connection-oriented (ensures data delivery).
  - **UDP:** Fast, connectionless (no guarantee of delivery).
+ **Example:**
  - TCP: Web browsing (HTTP).
  - UDP: Video streaming (Netflix).
+ **Key point:** Use TCP when reliability is critical, UDP when speed matters more.

### 10. What is a port?
+ **Definition:** A numerical endpoint for communication.
+ **Common port numbers:**
  - SSH: 22
  - HTTP: 80
  - HTTPS: 443
  - DNS: 53
  - FTP: 21
+ **Example:** Accessing a secure website on port 443.
+ **Key point:** Ports help differentiate services on the same device.

### 11. Common Protocols Every Web Developer Should Know
+ **HTTP/HTTPS:** Protocols for web communication.
+ **FTP/SFTP:** File transfer protocols.
+ **DNS:** Resolves domain names to IP addresses.
+ **SSH:** Secure shell for remote login.
+ **Example:** Using HTTPS ensures encrypted communication between a browser and a server.

### 12. DNS Basics
+ **Definition:** Domain Name System, which translates domain names (e.g., google.com) to IP addresses.
+ **How it works:**
  1. A user enters a domain name in a browser.
  2. The browser queries a DNS server.
  3. The DNS server returns the IP address of the domain.
+ **Example:** Resolving google.com to 172.217.0.0.
+ **Key point:** DNS caching improves performance.

### 13. HTTP and HTTPS
+ **HTTP:** Hypertext Transfer Protocol, used for transferring web pages.
+ **HTTPS:** HTTP with SSL/TLS encryption for secure communication.
+ **Example:** Accessing a website using `https://example.com`.
+ **Key point:** HTTPS ensures data integrity and confidentiality.

### 14. What tool/protocol is often used to check if a device is connected to a network?
+ **Tool/protocol:** Ping (uses ICMP).
+ **Example:** Running `ping example.com`.
+ **Key point:** Ping checks network connectivity and latency.

## Conclusion
This README provides detailed explanations of key networking concepts for web developers. Understanding these basics will help you build and troubleshoot web applications effectively.

