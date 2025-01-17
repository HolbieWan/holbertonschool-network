What Really Happens When You Type https://www.google.com and Press Enter
Cédric Tobie
Cédric Tobie

5 min read
·
2 hours ago






Whether you’re a seasoned developer or just starting your coding journey, you’ve likely been asked the famous interview question:

“What happens when you type a URL into the browser and press Enter?”

This question tests a fundamental understanding of the web stack and how different systems communicate over the internet.

In this blog post, we’ll walk through the key steps of the journey, from the moment you hit Enter to the final page rendered on your screen.

Specifically, we’ll focus on:

1. DNS Request

2. TCP/IP

3. Firewall

4. HTTPS/SSL

5. Load Balancer

6. Web Server

7. Application Server

8. Database

Let’s get started!

1. DNS (Domain Name System) Request
The first step in our journey happens when you type https://www.google.com into your browser.

Domain Name: www.google.com
Protocol: HTTPS (port 443)
Your computer doesn’t directly know which IP address corresponds to www.google.com. It consults a DNS resolver to translate the human-friendly domain into a machine-friendly IP address.

The browser checks its cache for a DNS entry. If it’s not there, it queries your operating system’s local DNS cache.
If no entry is found, the system contacts the configured DNS server (often provided by your ISP or a public DNS service like Google DNS at 8.8.8.8).
The DNS server either returns the IP address directly or queries other DNS servers up the chain (root, TLD, authoritative) until it obtains the correct IP address.
Finally, your computer receives the IP address and is able to move on to the next step.
DNS is like the internet’s phonebook — without it, humans would have to memorize all numbers for every server…

2. TCP/IP
After your machine has the correct IP address for www.google.com, it needs to establish a connection to Google’s servers. This is done through the TCP/IP (Transmission Control Protocol / Internet Protocol) stack.

TCP 3-Way Handshake: Your computer (the client) sends a SYN packet to the server. The server replies with a SYN-ACK, and then your computer sends an ACK back to the server. This handshake ensures both ends are ready to communicate reliably.
IP: The IP protocol is responsible for getting your packets from your computer to Google’s server using the IP address obtained from DNS.
The TCP/IP stack forms the backbone of all internet communication, ensuring data is broken down, transmitted, and reassembled correctly.

3. Firewall
Before your requests even leave your network, they might pass through firewalls — software or hardware systems that monitor and filter incoming and outgoing traffic based on predefined security rules.

Client-Side Firewall: Personal firewalls or corporate network firewalls can block or restrict outgoing connections if they look suspicious.
Server-Side Firewall: Google’s infrastructure will also have robust firewall rules that allow legitimate traffic to pass while filtering out malicious traffic.
Firewalls protect both the client and server from unauthorized or malicious traffic.

4. HTTPS/SSL
Since you typed https://www.google.com, the communication is encrypted using TLS/SSL (commonly just referred to as SSL, although TLS is the modern standard).

SSL Handshake: After the TCP handshake, your browser and the server initiate an SSL handshake, which involves exchanging certificates and agreeing on encryption parameters.
Encryption & Integrity: Once the handshake is successful, all data transferred between your browser and Google is encrypted, ensuring privacy and data integrity.
HTTPS is crucial for securing web traffic, protecting against eavesdropping (intercepting or monitoring a private communication), and validating the authenticity of the website.

5. Load Balancer
Google, like many large-scale services, uses load balancers to handle massive amounts of traffic efficiently.

Traffic Distribution: When your request reaches Google’s data center, a load balancer decides which backend server should handle your request based on rules such as server health, geographical proximity, or current load.
High Availability: Load balancers help prevent any single server from being overloaded and enable Google to handle traffic spikes seamlessly.
Load balancers ensure that no single machine handles all the requests and that users get fast, reliable responses, preventing failures.

6. Web Server
Once the load balancer routes your request, it typically arrives at a web server — commonly Nginx, Apache, or Google’s own specialized front-end servers.

Static Content: If you request any static resources (e.g., images, CSS, JavaScript files), the web server may serve them directly from a cache or file system.
Reverse Proxy: Often, the web server acts as a reverse proxy, forwarding requests to downstream services or application servers.
Web servers handle HTTP requests, serve static content, and delegate dynamic content tasks to application servers.

7. Application Server
Next, for anything requiring logic beyond simple file serving, the request hits an application server.

Business Logic: The application server applies the core functionality of the application: whether searching an index, customizing search results, or running AI-driven suggestions.
Scalability: Companies like Google deploy many application servers in parallel, each capable of handling thousands of requests per second.
Application servers are where the real “brains” of the system reside, handling data processing and complex computations.

8. Database
For many applications, data needs to be stored, retrieved, or updated. This is where the database comes into play.

Distributed Systems: Large-scale systems like Google use highly distributed, specialized databases to provide quick searches and near-instant access to results.
Caching: Caching layers (e.g., in-memory caches like Redis or Memcached) are often used to speed up repeated queries.
Whether using SQL or NoSQL, the database layer is responsible for storing and retrieving the information that powers dynamic content.

9. The Response Journey Back
After the application logic executes and (if needed) queries the database, the response travels back up the chain:

Application Server → Web Server → Load Balancer → Client
SSL encryption is applied to ensure security as the data travels over the network.
Upon reaching your browser, the HTML/CSS/JS is rendered and displayed as the familiar Google Search homepage.
Final Thoughts
Understanding what happens behind the scenes when you type a URL into a browser is a critical skill for any aspiring software engineer.

Whether you’re a front-end developer focused on how the browser displays a page, or an SRE (Site Reliability Engineering) concerned with load balancing and uptime, this blog will hopefully give you a clearer picture of the essential communication principles that make the internet work!

Here is a simple diagram to summarize the main steps of the process:

https://i.imgur.com/k9Y8Kty.png

Thanks for reading! If you found this helpful, feel free to leave a comment or share this blog post with your network.