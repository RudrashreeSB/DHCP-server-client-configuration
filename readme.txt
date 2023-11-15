Software used:
CISCO Packet Tracer.

Description: This lab exercise demonstrates DHCP server configuration and DHCP client configuration on two routers and also shows the verification commands both on the server and the client.

Given Instructions:
Instructions

1. Issue service dhcp command on router R1 that enables DHCP server feature on router
2. Create an addressing pool for dhcp called pool1.
3. Isssue network command that specifies the range of IP addresses to be assigned to clients. Use 192.168.4.0 255.255.255.0 in this lab.
4. Assign the domain-name "sample.com" to the client.
5. Assign the IP Address of the DNS-server and Default-router, say 192.168.4.2 and 192.168.4.5 respectively
7. Set the duration of the lease to 4 days.
8. On router R2 and R3, enter into interface confiuration mode and issue the command "ip address dhcp" that configures the interfaces to acquire IP Addresses from the DHCP server.
9. Use "show interfaces" or "show ip interface brief" command on R2 and R3 to verify the addresses acquired from the server.
10. Use "show ip dhcp binding" command on router R1 i.e, server, to view the addresses assigned to clients.
11. Use "clear ip dhcp binding <client_address>" on the server R1 to clear the specific address assigned to client or "clear ip dhcp binding *" to remove all the addresses assigned to clients.
12. Use "no ip address dhcp"  command on clients R2/R3 in interface configuration mode to unconfigure an address assigned on it by the DHCP server.

Note: DHCP provides dynamic addressing information to hosts on a network. It allows devices to dynamically acquire their addressing information. The main purpose of the DHCP server is to provide IP configuration parameters to hosts such as the default gateway, domain name, Domain Name System – DNS.  

DHCP uses UDP protocol. Port 67 for requests and 68 for replies. 

Note that as per cisco 12.2 release, only ethernet interfaces are supported for DHCP.



NETWORKS:
NETWORK 0 – 192.168.4.0 
NETWORK 1 -  192.168.5.0
NETWORK 2 -  192.168.6.0


Default network addresses for the three networks:
N0 R0-192.168.4.5			
N1 R1 – 192.168.5.5		           
N2 R2 – 192.168.6.5


Instructions:
1.Connect the DHCP server to the switch of the network 0 where we have set up 2 PCs. Make the other two clients out of PCs and switches and routers appropriately. 
2.Set the default Gateway to 192.168.4.5 and the DNS SERVER as 192.168.4.2 as per the given requirement in the problem statement, in the server0.
3.In the Fastethernet 0, set port status ON, and set the unique IPv4 address and subnet mask, where the IPv4 address here, is used for the DHCP client server communication.
4.In the services of server, in the DHCP service, set the server pools and IPv4 address for all three networks(client) in the server similarly. 


5.Set the default gateway as usual in the PC 0.
6.In the fastEthernet0 , Set the port status ON. Give the IPv4 address as a unique address of class C i.e, 192.168.4.6 and set the subnet mask appropriately as per the IPv4 address.
7.Similarly do the above steps for all the PCs connected in the other two networks of the client.
8.In the router 0, Set the port status and in the fastethernet0 set the default gateway to be the IPv4 address and the appropriate mask also.
9.Similarly for  all the other routers. For router 1 the IPv4 address is said to be , 192.168.5.5 and for router 2 it is 192.168.6.5.


10.Dynamic Routing is then made for the establishment of connection between the routers and the switches.
11.Now to connect the routers to each other, let us give serial connections.


R0 – R1 -> Se2/0
R1- R2 ->Se 2/0
R1 - R2 ->Se 3/0
R2- R1 -> Se 3/0
R0 – R2 ->Se 3/0
R2 – R0 – Se 2/0

12.For instance, in router0, in the serial connection 2 set the unique IPv4 address of 192.168.8.5 and the corresponding mask.

13.set the unique ipv4 addresses for all the connections ,mentioned in the serial connections.
14.In the Router0, in the Routing information protocol(RIP), add the IPV4 addresses for all the connected devices’s network’s IP. 
15. R0 is connected to two additional paths except the 192.168.4.0, which are the paths from R0 – R1 and R0-R2. Add the ip addresses in the RIP.

16.Similarly add the connected paths to the other routers namely R1, R2.
17.send messages from client to server and receive message from the client for DHCP connection.
In the CLI of R0





