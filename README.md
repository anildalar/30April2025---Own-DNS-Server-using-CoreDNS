# 30April2025---Own-DNS-Server-using-CoreDNS
30April2025 - Own DNS Server using CoreDNS

1. How to setup our own DNS server using CoreDNS So we don't need any Domain Panel to create Zone Records like "A Record"?

root -> 65.21.145.81:53 (Open)   (Own DNS Server)
Windows OS
telnet 65.21.145.81 53  -> Black Screen -> Port Open

65.21.145.81:53 (Open/Close)  ?????

Which Port No is very import for DNS Server
53

Amazon Route53 
Oklabs Route53

DNS server Linux
1. BIND9
2. PowerDNS
3. CoreDNS  -> K8s


account/imageName:tagName
coredns/coredns:latest


docker run -d --name coredns -p 53:53/udp -p 53:53/tcp -v ~/coredns/config:/etc/coredns coredns/coredns:latest  -conf /etc/coredns/Corefile


docker run -d \
  -p 53:53/udp \
  -p 53:53/tcp \
  -v ./coredns:/etc/coredns \
  coredns/coredns:latest \
  -conf /etc/coredns/Corefile

-d - detached Mode/Background mode
-v - volume Mounting

sudo systemctl stop systemd-resolved
sudo systemctl disable systemd-resolved


Docker

id_rsa

https://primarydomain.com
https://vishalmahawar.shop

https://subdomain.primarydomain.com

subdomain -> DNS Panel (GUI) -> A Record
GUI = Graphical User Interface

https://april30-2025.vishalmahawar.shop

ping april30-2025.vishalmahawar.shop -t
