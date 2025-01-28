# Domain Name Servers
```query
children:.
```
---

## DNS Hierarchy

See [here](https://www.dynu.com/en-US/Blog/Article?Article=DNS-Servers-Authoritative-Recursive-Root-TLD#:~:text=Recursive%20resolvers%20are%20also%20called,4.4.) for a very good overview of the different types of DNS servers. Due to the hierarchy outlined there, you can't just redirect google.com to your own IP address, since your DNS server is not the authority on google.com.

## DNS Records

* **A record:** Points a domain name (host) to an IP address (value).
* **CNAME record:** Points a domain name (host) to another domain name (value).

Note that for a DNS for a specific domain name, using @ indicates that this record is for the domain name withot a subdomain. If some other string is used, then that string is used as the subdomain for that DNS entry.
