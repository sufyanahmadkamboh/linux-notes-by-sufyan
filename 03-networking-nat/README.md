# Networking: NAT & Host-Only

VirtualBox network modes

NAT: VM has outbound internet via host.

Host-Only: VM reachable from host on a private network.

Bridged: VM sits on same LAN as host.

Check IPs

bash
Copy code
ip a
ip r
ping -c2 8.8.8.8
Troubleshoot

DNS: check /etc/resolv.conf

Default route: ip r | grep default
