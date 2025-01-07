# Networking basics #2

# Networking Basics - Learning Objectives

## Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

### General
+ **What is localhost/127.0.0.1**  
  `localhost` is the hostname that refers to the current machine. `127.0.0.1` is the IP address that points to the local machine.

+ **What is 0.0.0.0**  
  `0.0.0.0` is a non-routable address that represents all IPv4 addresses on the local machine.

+ **What is /etc/hosts**  
  This file maps hostnames to IP addresses, allowing the system to resolve specified hostnames locally without querying DNS.

+ **How to display your machine’s active network interfaces**  
  Use the command `ifconfig` or `ip addr` to display information about the network interfaces on your machine.

### Additional Commands
+ **ifconfig**
  **What**: `ifconfig` is a command-line tool used to configure and display network interface parameters.
  
  **Why**: It helps in viewing the status of network interfaces and their IP addresses, as well as enabling or disabling interfaces.
  
  **How**: Run `ifconfig` in the terminal to view network interfaces. Example:
  ```bash
  ifconfig
  ```
  This will display the IP address, netmask, broadcast address, and status of each interface.

+ **telnet**
  **What**: `telnet` is a command-line tool used for remote login and communication with another host using the Telnet protocol.
  
  **Why**: It is used for testing connectivity to remote servers or for accessing remote systems.
  
  **How**: Use `telnet [hostname] [port]` to connect to a server. Example:
  ```bash
  telnet example.com 80
  ```
  This connects to `example.com` on port 80.

+ **nc**
  **What**: `nc` (Netcat) is a versatile command-line tool used for reading from and writing to network connections using TCP or UDP.
  
  **Why**: It is commonly used for port scanning, transferring files, and creating network connections.
  
  **How**: Example usage to connect to a server:
  ```bash
  nc example.com 80
  ```
  This opens a TCP connection to `example.com` on port 80.

+ **cut**
  **What**: `cut` is a command-line utility used to extract sections of lines from files or input streams.
  
  **Why**: It is useful for processing data and extracting specific columns from structured text.
  
  **How**: Example usage to extract the first column from a file:
  ```bash
  cut -d',' -f1 file.csv
  ```
  This extracts the first column from a CSV file, using `,` as the delimiter.

## Exemple of communication with telnet: 

### Write a Bash script that listens on port 98 on localhost:

```bash
#!/usr/bin/env bash
# This script listens on port 98 on localhost.
nc -l -p 98 -s 127.0.0.1
```

### Terminal 0:
Starting my script.
sylvain@ubuntu$ sudo ./2-port_listening_on_localhost

### Terminal 1:
Connecting to localhost on port 98 using telnet and typing some text:

sylvain@ubuntu$ telnet localhost 98
<br> Trying 127.0.0.2...
<br> Connected to localhost.
<br> Escape character is '^]'.
<br> Hello world
<br> test

### Terminal 0
Receiving the text on the other side:
<br> sylvain@ubuntu$ sudo ./2-port_listening_on_localhost
<br> Hello world
<br> test
