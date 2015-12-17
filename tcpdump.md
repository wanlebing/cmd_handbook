tcpdump
================================

# issues
## packets dropped by kernel
What's the `packets dropped by kernel`?
```
1537 packets captured
2023 packets received by filter
477 packets dropped by kernel
```
> "packets dropped by kernel" (this is the number of packets that were dropped, due to a lack of buffer space, by the packet capture mechanism in the OS on which tcpdump is running, if the OS reports that information to applications; if not, it will be reported as 0).

Set the buffer size with `tcpdump -B 4096`, the unit is KB.

## where does the packets be captured
[Between kernel stack and device driver.](http://www.cubrid.org/blog/dev-platform/understanding-tcp-ip-network-stack/)

[TCPdump hooks above the driver, and does not see what is sent on the wire. Rather it sees what is sent from the stack to the driver.](https://www.myricom.com/software/myri10ge/349-when-i-view-traffic-with-tcpdump-why-do-i-see-packets-larger-than-the-mtu.html)