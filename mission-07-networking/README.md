# Mission 7 - How Computers Communicate

## 1. Task / objective
Explain basic network types and concepts, observe DNS lookup and connectivity
information with Terminal, and describe what happens when a website opens in a browser.

## 2. Work completed
- Explained eight core network concepts (LAN, MAN, WAN, DNS, router, protocol,
  packet switching, client-server) with an example of each.
- Used `ping` to test connectivity to a public example website.
- Used `nslookup` to look up the network address behind a domain name.
- Wrote a numbered 6-step explanation of what happens when a website is opened.
- Redacted any personal network details (own IP, Wi-Fi name, router address).

## 3. Commands / tools used

| Command / tool | Purpose |
|---|---|
| `ping -c 5 example.com` | Send 5 ICMP echo requests to check connectivity and measure round-trip time |
| `nslookup example.com` | Query a DNS server for the IP addresses behind a domain name |

## 4. My understanding

### Task 7.1 - Network concepts

| Concept | Explanation in my own words | Example |
|---|---|---|
| LAN | A network covering a small area, such as a home, lab or office | The Wi-Fi network inside my house |
| MAN | A network covering a city or large campus area | A university campus network spanning several buildings |
| WAN | A network covering large geographical areas | The internet itself |
| DNS | Translates a domain name into an IP address | `example.com` resolves to `104.20.23.154` |
| Router | Connects networks and forwards data between them | The home Wi-Fi router that joins my LAN to my ISP |
| Protocol | A set of rules that devices follow to communicate | HTTP, TCP/IP |
| Packet switching | Data is divided into packets that travel independently across a network and are reassembled at the destination | A web page arriving as many small packets |
| Client-server | A client requests a service and a server provides it | My browser (client) asking a web server for a page |

### Task 7.2 - Network observation

`ping -c 5 example.com` output (summarised):

- Destination: `example.com` resolved to `104.20.23.154`
- 5 packets transmitted, **5 received, 0.0% packet loss**
- Round-trip time: min 5.563 ms, avg 9.807 ms, max 13.964 ms
- TTL of 58

`nslookup example.com` output:

- DNS server used: `8.8.8.8#53` (Google Public DNS, port 53)
- Non-authoritative answer (cached, not from the authoritative name server)
- Two A records: `104.20.23.154` and `172.66.147.243`

**Answers to the questions:**

- **What a connectivity test helps you check:** whether this machine can reach a remote
  host over the network, whether it is losing packets, and how long the round trip
  takes. 0% loss and single-digit millisecond latency mean the network path is healthy.
- **What a DNS lookup displays:** which DNS server answered, whether the answer came
  from cache (non-authoritative) or from the domain's own name servers (authoritative),
  and the IP address(es) that the domain name currently maps to.
- **Role of DNS when a website name is typed:** the browser does not know how to route
  packets to a name, only to an IP address, so it asks a DNS resolver to translate
  `example.com` into an IP it can actually connect to.

### Task 7.3 - What happens when a website opens

1. I type `example.com` into the browser's address bar.
2. The browser first checks its own DNS cache, then the operating system's cache. If
   the name is not cached, the OS sends a DNS query to the configured resolver
   (here `8.8.8.8`) which returns an IP such as `104.20.23.154`.
3. The browser (client) opens a TCP connection to that IP on port 443 using the
   **HTTPS protocol**, which starts with a TLS handshake to agree on encryption.
4. The request passes through my local **router** and then across **WAN** links through
   several intermediate routers until it reaches the **server** that owns the IP.
5. The **server** processes the request and sends the response (HTML, CSS, images)
   back the same way, split into **packets** that are reassembled at my computer.
6. The browser renders the page and displays it to me.

## 5. Difficulties faced
No major difficulties.

## 6. How I resolved them
Not applicable.

## 7. Evidence / files

| File | What it contains |
|---|---|
| `mission-07-networking/README.md` | This report |
| `evidence/mission-07/network-check.txt` | Captured output of `ping -c 5 example.com` and `nslookup example.com` |

Only public domains and public IPs (Cloudflare, Google DNS) are shown - no personal
IP address, Wi-Fi name or router address is included.

## 8. Commit details

| Field | Value |
|---|---|
| Commit message | `Explain networking concepts and website communication` |
| Files in commit | `mission-07-networking/README.md`, `evidence/mission-07/network-check.txt` |
