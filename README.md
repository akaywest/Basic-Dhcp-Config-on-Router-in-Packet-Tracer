Basic DHCP Lab in (on a Router) Packet Tracer

This topology will includes a router, a switch, and end devices like PCs and Laptops

Configs on Router
--------------------------------------------
en
config t
hostname Main-Router
int g0/0/0  (configuring IP Add the interface that connects to the switch)
ip add 192.168.1.1 255.255.255.0
ip dhcp pool Main-Network  (config dhcp on the router)
network 192.168.1.0 255.255.255.0   (the network id)
default-router 192.168.1.1  (this is the default Gateway, it is the Ip Add that we used in the "g0/0/0" interface that connects to the switch)
dns-server 8.8.8.8   (config for the dns server)
ip dhcp excluded-address 192.168.1.1  192.168.1.5(this is used to reserve or exclude some certain IP Addresses e.g our gateway) 
sh run | sec Main-Network   (to show the Dhcp config)


After the configurations we navigate to the end devices and set them to recieve DHCP allocated IP Addresses.
