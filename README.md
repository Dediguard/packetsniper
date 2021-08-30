# packetsniper
Network pattern analyzation &amp; response daemon

# what is this?

In short packetsniper's job is to recognize patterns in application-layer network traffic and act accordingly when it deems that the traffic is likely to be an attack of some sort. It achieves this by communicating with various firewall solutions, depending on which one it is configured to use.

## packetsniper is **not** a firewall

Packetsniper will **not** handle the denial of network traffic itself, neither will it let you manually block specific packet types and e.t.c. For that you have actual firewalls, whether that be the operating system's in-built firewall or a hardware firewall of some sort. When packetsniper decides to block specific types of packets from reaching the application it is protecting it will use the system's firewall or routing service to send blocked packets to a null-route server we appropriately named `sponge`.
