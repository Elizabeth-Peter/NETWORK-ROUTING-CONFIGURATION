## Static-Routing
Definition

Static routing is a network routing technique in which routes are manually configured on a router by a network administrator. These routes define fixed paths that data packets must follow to reach specific destination networks. Once configured, static routes remain in the routing table and do not change automatically unless they are manually modified or removed.


## How Static Routing Works — Step by Step

**1. The Destination**

The network administrator identifies the network that needs to be reached. For example, the network
`192.168.2.0/24` .


**2. Specify the Path**

The administrator chooses how to reach the destination—either by specifying:

- **Next-hop IP address:** The IP of the next router on the path

- **Exit interface:** The router’s physical or logical port through which traffic will leave

**3. Add the Route to the Router**

Using router commands (like Cisco’s `ip route`), the administrator manually enters the route into the router’s routing table.

**4. Router Forwards Packets**

When a data packet arrives, the router checks its routing table. If the destination matches the static route, it forwards the packet along the defined path.

**5. Maintain the Route Manually**

Since static routes do not update automatically, any network change—like a link going down or a new network being added—requires manual updates to the routing table.



**Example Command (Cisco)**
``` bash
ip route 192.168.2.0 255.255.255.0 192.168.1.1
```

- `192.168.2.0` → Destination network

- `255.255.255.0` → Subnet mask

- `192.168.1.1` → Next-hop router IP


## Components of a Static Route

- **Destination Network:** Specifies the network the router is trying to reach.

- **Subnet Mask:** Determines the size and range of the destination network.

- **Next-Hop IP Address:** The IP address of the neighboring router to which packets are forwarded.

- **Exit Interface:** The physical or logical interface through which traffic leaves the router.


## Types of Static Routes

- **Standard Static Route:** A manually defined route to a specific destination network.

- **Default Static Route:** Used when no specific route exists for a destination; commonly written as 0.0.0.0/0.

- **Floating Static Route:** A backup route configured with a higher administrative distance to take over if the primary route fails.


## Advantages of Static Routing

- Simple to configure and understand

- Uses minimal router resources

- More secure (routes not advertised)

- Provides predictable traffic flow

## Disadvantages of Static Routing

- Not suitable for large or changing networks

- Requires manual updates

- No automatic failover for link failures


## Use Cases

Static routing is commonly used in small or stable networks, stub networks with a single exit point, and as backup routing solutions alongside dynamic routing protocols.

## Administrative Distance

Static routes have an administrative distance of 1, giving them higher priority over most dynamic routing protocols.

## Conclusion

Static routing is a fundamental and reliable routing method that provides simplicity, control, and efficiency. When used in appropriate environments, it ensures stable network communication and serves as a strong foundation for understanding advanced routing technologies.


