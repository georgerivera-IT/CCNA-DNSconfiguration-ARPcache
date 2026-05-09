# DNS Configuration

### Overview:
Configuring routers as DNS clients and observing ARP caches.

### What I configured:
3 Routers to be DNS clients.

### Skills demonstrated:
Cisco IOS, DNS, ARP cache

### Screenshots:
#### Topology
<img width="808" height="453" alt="image" src="https://github.com/user-attachments/assets/f2449425-e0db-41e5-8c34-27cca8f6ebd7" />
<br><br>

#### Initial Ping
<img width="486" height="198" alt="image" src="https://github.com/user-attachments/assets/7d13daf2-2075-423c-8f4f-38f2bb0be73e" />  
<br>
Although R1 can ping R2 and R3, the IOS is broadcasting the DNS query to the entire subnet, rather than sending it to the dedicated DNS server. This is because by default Cisco IOS routers broadcast DNS requests to 255.255.255.255 when attempting to ping a hostname, as evident in the screenshot. 
<br><br>
<img width="501" height="187" alt="image" src="https://github.com/user-attachments/assets/f1e07df2-a40b-41f4-9ac7-da50ce31ddf3" />
<img width="491" height="185" alt="image" src="https://github.com/user-attachments/assets/9397fbf3-3efd-4a31-a92d-5ad01b448a4a" />
<img width="495" height="186" alt="image" src="https://github.com/user-attachments/assets/2b4d98d0-440b-436f-a16e-435d6e2a82b7" />

After configuring all routers to use 10.10.10.10 as their DNS server, DNS resolution will go directly to the server (10.10.10.10) rather than broadcasting. 
