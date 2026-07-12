# Domain, DNS and TLS Certificates with Let's Encrypt  

## Lab Setup and Tasks  

1. Launch Ubuntu VM using Microsoft Azure  

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/680d8dc6-3e1c-49e7-b6dc-bf985ea5c9a9" />
     
    Ensure the inbound ports: 22 (SSH), 80 (HTTP) and 443 (HTTPS) are open.    

2. Install Apache2 by using command 'sudo apt install apache2'  

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/bb80ecff-e9a8-483a-ace6-a920fb8e122d" />  
   
3. Check in Browser to confirm Apache page by using the public IP address
   
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/d4a3a3a6-f24e-4eca-8a7e-6cebafe4ede9" />  

4. Register account on DuckDNS - https://www.duckdns.org/
   
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/72d45a50-9dff-4274-9d61-e4d0023e7c48" />  

5. Register a domain name
   
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ddf45083-a6a5-4d3d-b579-88e2b9ae0431" />  

6. Create an A record pointing domain to the public IP of the server
    
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/2c6923ac-24d1-4e48-ae13-babd81e77f6c" />  

7. Wait for DNS propagation and test with PING
    
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/01c5f996-d5e2-4249-8db3-834775e4ea04" />  

8. Install certbot by using the command 'sudo apt install certbot python3-certbot-apache`.  
   The newer version istransitioned to snap package manager  

   So To ensure snap core is up to date by using command : sudo snap install core; sudo snap refresh core  
   <img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/d6af3c31-5613-4493-b433-7a4927af1c69" />  

   Install the certbot by using the command 'sudo snap install -classic certbot'  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/944426ce-7156-49b6-a1b1-08ee4d3edcc7" />  

   Create a symlink so the system knows where the certbot command is by using the command 'sudo ln -s /snap/bin/certbot /usr/bin/certbot'  
   <img width="500" height="100" alt="image" src="https://github.com/user-attachments/assets/54bd0a4e-e37f-46d1-a084-45059dc699a7" />  

   Generate and install the certificate by running the command 'sudo certbot --apache'  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/09937cdb-4b67-45fc-920a-41ef4587f6d2" />  

   Ensure the HTTPS is created under inbound port rules in VM launch by Azure cloud and also the ufw managed by Ubuntu server itself.  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f67fad01-b186-4e5f-b04b-078f743452c2" />    
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/bc7e80ba-8386-444b-909b-3241a8df3bef" />  

   Final result, HTTP to HTTPS  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/15802f13-653e-4fa5-9b78-63551f0185fc" />  

   We can check for certificates status by using the command 'sudo certbot certificates'  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e2ba8d5e-3264-41cf-9dd6-d303bf8e08bf" />  

   The certificates has a validity period of 90 days, to renew the certificate, we can run the command : sudo certbot renew --dry-run  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f7607a4f-053e-4d3d-abf4-553673c72f00" />  

## Advanced Tasks  

•	Who issued the SSL certificate for murdoch.edu.au and csn.murdoch.edu.au?  

There’s two way :  

1)	The browser method, navigate to https://murdoch.edu.au or https://csn.murdoch.edu.au , click the padlock in the address bar, View the certicate details and look for Issuer
   
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/4259ed79-ed1b-4be8-a7a1-d6482cb113cd" />

2)	The CLI method, check straight from Ubuntu terminal, use the openssl tool to pull the certificate data : echo | openssl s_client -connect Murdoch.edu.au:443 2>/dev/null | grep “issuer”
   
   <img width="500" height="60" alt="image" src="https://github.com/user-attachments/assets/6c730393-b29c-4212-9a23-1b16fbb56197" />  

Echo = prints text to the screen. When run completely empty like this, it just outputs a single blank line (a newline character)
The openssl s_client command normally opens an interactive session that stays open, waiting for you to type commands to the server. By passing a blank         line into it, we tell the connection to instantly close as soon as it succeeds so it doesn’t hang your terminal.  
  	
| (The Pipe) = The Pipe operator takes the output of the command on its left and feeds it directly as the input to the command on its right. The first         pipe takes the blank line from the echo and feeds it into openssl. The second pipe takes the massive mountain of text that openssl outputs and feeds it        into grep
  	
openssl = This invokes the OpenSSL toolkit, which is the standard open-source cryptographic software library used for handling SSL/TLS connections,            certificates and encryption keys in Linux.
  	
S_client = It stands for SSL/TLS Client. It implements a generic SSl/TLS client that can initiate a secure connection to a remote server
  	
-connect = This is a flag or argument telling the s_client command that the very next piece of information will be the specific host and port address it        needs to dial out to
  	
Murdoch.edu.au:443 = This is the target destination, which consist of the domain name and the destination port number which belongs to HTTPS.
  	
2>/dev/null = This redirects errors into the digital void, 2 represents the standard error stream 9stderr) in Linux, > is the redirection operator,             /dev/null is a special virtual file in Linux that acts like a black hole, anything written to it disappear completely.  
  	
grep = This stands for Global Regular Expression Print. It is a powerful search tool that scans text line by line and only displays lines that match a         specific keyword.
  	
“issuer” = This is the search term handling to grep  





•	Can you use a subdomain to point to another student’s server?  
  Yes, absolutely, DNS record do not care who owns the server or where it is hosted. A domain name is simply a routing table. If you create a subdomain example like friend.tanjunlimlab3a.duckdns.org, and point its ‘A Record’ to other’s Azure Public Ip address, anyone who visits that subdomain will be routed to that person’s Apache server.  



•	Create two A records with different IPs. Observe failover behaviour.  
  This tasks introduce a concept called DNS Round-robin. If I assign two different IP addresses to the exact same domain name, the DNS server will hand out the first IP. When the next user requests it, it will handout the second IP, and so on.  



•	Shutdown server and observe DNS delay in failover. Discuss why.  
  If two servers are running in a DNS Round-robin setup and one of them example, Server A is completely shut down, the half of the web traffic still fails for a period of time. Because of DNS Caching and TTL (Time to Live). When a visitor’s internet service provider or their local computer looks up to your domain, they save the IP address for a specific amount of time to speed up future requests. Even if your server is dead, the visitor’s computer will keep trying to connect to the dead IP address until that cached TTL timer expires.  This is why DNS is generally not used for instantaneous high-availability failover. For true high availability, enterprise use dedicated “Load Balancers” rather than rely on DNS.  



•  Reflect on DNS load balancing, round-robin, and high-availability use cases.  
   When you configure multiple A Records with different public IP addresses for a single domain, the DNS server shifts into a Round-Robin bahavior. When a client browser asks the DNS server for your website’s IP, the DNS server returns the netire list of Ips but rotates the order each time. Browser A gets [Server 1, Server 2] while Browser B gets [Server 2, Server 2] and so on. It distributes incoming traffic across multiple servers without requiring an expensive, dedicated hardware load balancer.  
High availability meaning your system will still runs when one of the server dies. We cannot rely only on DNS Round-Robindue to DNS caching and TTL (Time To Live). If lets say Server 1 completely dies, the DNS server might eventually notice or we might manually remibe it’s a record. Client browsers and ISPs don’t ask the DNS server for the IP address on every single click. To speed up the internet, they save the answer locally for the duration of the TTL timer example: 60 seconds or sometimes hours. So for any visitor whose browser cached the dead server’s IP address, their request will continue to hit the dead server and time out until their local TTL clock counts down to zero and forces a fresh DNS lookup.  


## Relection Questions  

•	What is the role of DNS in Internet presence?  

DNS (Domain Name System) translate human readable domain names into the raw, public IP addresses that computers use to route traffic across the internet. It acts as the internet’s phonebook, ensuring visitors can reach your server without needing to memorize a string of numbers.  

•	Why does DNS propagation take time?  

When a DNS record is updated, the change doesn’t happen globally at once. ISPs and local computers cache DNS records for a specific duration knows as the TTL (Time To Live) to speed up the web browsing. Propagation is simple the delay while you wait for these global caches to expire so they fetch the newly updated IP address.  

•	How does Let’s Encrypt validate domain ownership?  

Let’s Encrypt validates ownership by issuing an automated “challenge” to your ACME client, such as certbot. The most common methos, the HTTP-01 challenge requires certbot to place a specific file containing a unique token inside a hidden directory on your web server. Let’s Encrypt then attempts to download this file over Port 80. If the token matches, it proves that you have administrative control over the server that the domain points to.  








   













   



