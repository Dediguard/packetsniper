# packetsniper
Network pattern analyzation &amp; response daemon

# what is this?

In short packetsniper's job is to recognize patterns in application-layer network traffic and act accordingly when it deems that the traffic is likely to be an attack of some sort. It achieves this by communicating with various firewall solutions, depending on which one it is configured to use.

## packetsniper is **not** a firewall

Packetsniper will **not** handle the denial of network traffic itself, neither will it let you manually block specific packet types and e.t.c. For that you have actual firewalls, whether that be the operating system's in-built firewall or a hardware firewall of some sort. When packetsniper decides to block specific types of packets from reaching the application it is protecting it will use the system's firewall or routing service to send blocked packets to a null-route server we appropriately named `sponge`.

## packetsniper is **not** ddos protection

Although it might seem like it, packetsniper still isn't DDoS protection. All it does is recognize patterns in network traffic and respond to those patterns accordingly. When you set up packetsniper you have to tell it what it is meant to be recognizing and what do to when it does recognize that traffic. For our usage we've "trained" it to recognize packets sent from the same source repeatedly, as well as other generally harmful packets, and then block them. The sponge null-routing service is built-in to packetsniper so you can use it yourself right away but no recognition models are included by default.
