**Switch** — connects wired devices within a network. It learns which MAC addresses are on which ports and forwards frames only where they need to go. Operates at Layer 2 (though L3 switches can also route). It's basically a smart hub that doesn't flood traffic everywhere.

**Gateway/Router** — connects different networks together. Your UDM sits between your internal networks and the internet, handles NAT, firewall rules, and routes traffic between VLANs. Operates at Layer 3. It's the boundary between "inside" and "outside" and between subnets.

**Access Point** — a wireless bridge. It takes your wired network and extends it over WiFi. Clients connect to the AP wirelessly, the AP forwards their traffic onto the wired network. It's essentially a switch port that happens to be radio-based.

**How they fit together in your setup:**

```
Internet
    │
 Gateway (UDM) ← firewall, NAT, inter-VLAN routing
    │
 Switches ← connect wired devices, trunk VLANs between each other
    │
 Access Points ← hang off switch ports, bridge WiFi clients onto VLANs
```

Every packet leaving the building goes through the gateway. Traffic between two devices on the same VLAN only touches switches (and APs if wireless). Traffic between different VLANs goes up to the gateway to be routed and firewalled.