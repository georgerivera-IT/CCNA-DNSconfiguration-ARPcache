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
Although R1 can ping R2 and R3, the IOS is broadcasting the DNS query to the entire subnet, rather than sending it to the dedicated DNS server. This is because by default Cisco IOS routers broadcast DNS requests to 255.255.255.255 when attempting to ping a hostname, as evident in the screenshot. 
<img width="486" height="198" alt="image" src="https://github.com/user-attachments/assets/7d13daf2-2075-423c-8f4f-38f2bb0be73e" />  
<br><br>

#### Initializing DNS Clients
After configuring all routers to use 10.10.10.10 as their DNS server with the command 'ip name-server', DNS resolution will go directly to the server rather than broadcasting to 255.255.255.255. 
<img width="501" height="187" alt="image" src="https://github.com/user-attachments/assets/f1e07df2-a40b-41f4-9ac7-da50ce31ddf3" />
<img width="491" height="185" alt="image" src="https://github.com/user-attachments/assets/9397fbf3-3efd-4a31-a92d-5ad01b448a4a" />
<img width="495" height="186" alt="image" src="https://github.com/user-attachments/assets/2b4d98d0-440b-436f-a16e-435d6e2a82b7" />
<br>
This objective was to learn how real networks function as you want to prevent routers blindly broadcasting DNS requests.

### ARP Cache

<img width="707" height="138" alt="image" src="https://github.com/user-attachments/assets/85103d6e-b3d7-43e7-9ebf-ac4e3f46c61c" />
<img width="547" height="93" alt="image" src="https://github.com/user-attachments/assets/8c97c966-c993-4e20-8169-c4a0787a3b3a" />
<br>
<img width="544" height="54" alt="image" src="https://github.com/user-attachments/assets/ee46d619-cf89-49b8-9bea-b915296ec2ee" />
<br>
ARP requests only exist at Layer 2 in which hosts must be directly connected. Because R1 (10.10.10.1) isn't directly connected to R3 (10.10.20.1), it does not have an entry in its ARP cache, and vice versa. R1 can reach R3 via R2's IP address 10.10.10.2, which is included in R1's arp cache.
Because R2 is directly connected to both R1 and R3, both entries show up in its arp cache.
