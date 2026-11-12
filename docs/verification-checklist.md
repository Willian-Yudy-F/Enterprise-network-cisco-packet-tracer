# Network verification checklist

Use this checklist when the original Packet Tracer file becomes available. Record the
device, command, expected result and actual result instead of relying only on successful
green link indicators.

## 1. Physical and interface state

On every router:

```text
show ip interface brief
```

- Confirm each required interface is `up/up`.
- Confirm the configured addresses match the address plan.
- Investigate administratively down or protocol-down interfaces before testing routing.

## 2. Address allocation

On each representative end device:

```text
ipconfig /all
```

- Confirm the host received an address from the correct subnet.
- Confirm subnet mask, default gateway and DNS server values.
- Repeat the test after releasing and renewing the DHCP lease.

On routers providing DHCP:

```text
show running-config | section dhcp
show ip dhcp binding
show ip dhcp conflict
```

## 3. Routing

On every router:

```text
show ip route
show ip protocols
```

- Confirm connected networks are present.
- Confirm remote LANs have a valid next hop.
- Confirm the intended routing method is active on the expected interfaces.
- Check that no required department network is missing.

## 4. End-to-end connectivity

From one representative host in every LAN:

1. Ping its own default gateway.
2. Ping a host on a directly connected neighbouring site.
3. Ping a host on the most distant site.
4. Run `tracert` to a remote host and record the path.

Keep a matrix with source LANs as rows and destination LANs as columns. A failure should
record the last reachable hop, not only “ping failed”.

## 5. DNS and web service

From at least one host at each site:

```text
nslookup <internal-hostname>
ping <internal-hostname>
```

- Confirm the hostname resolves to the intended server address.
- Open the internal website by hostname, not only by IP address.
- Record the expected page title or response.

## 6. Evidence to publish

- Sanitised `.pkt` file and Packet Tracer version.
- VLSM table with network, prefix, usable range, gateway and broadcast address.
- Router and switch configuration exports.
- DHCP and DNS records.
- Completed connectivity matrix.
- Screenshots of one successful route, DNS lookup and HTTP request.

Do not publish real company addresses, credentials or assessment-only confidential data.
