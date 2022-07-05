# Network

List and modify interface in the host
`ip link`

See the IP addresses assigned to these interfaces
`ip addr`

Assign IP addresses to the interfaces (will reset on reboot). To change it permanently, add entry on `/etc/network/interfaces`
`ip addr add 192.168.1.10/24 dev eth0`

Communicate System A (Network 1) to Network 2
`ip route add 192.168.2.0/24 (Network 2 Switch IP) via 192.168.1.1 (Router IP connected to Network 1)`

Communicate Network 2 to Internet
`ip route add 0.0.0.0 (All unknown IP or default) via 192.168.2.1 (Router IP connected to Network 2)`