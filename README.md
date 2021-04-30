Install and configure auditd on Linux systems.

This role has been tested against Ubuntu 18.04, but will work for most distributions.

NOTE: Ubuntu disables auditd network listening in their auditd build. This is visible in the trace of auditd running in the foreground, e.g.
```
/sbin/auditd -f
...
tcp_listen_port_parser called with: 5000
Listener support is not enabled, ignoring value at line 25
tcp_listen_queue_parser called with: 5
Listener support is not enabled, ignoring value at line 26
tcp_max_per_addr_parser called with: 1
Listener support is not enabled, ignoring value at line 27
tcp_client_max_idle_parser called with: 0
Listener support is not enabled, ignoring value at line 29
...
```
The patch that introduced this change appears to be: https://linux-audit.redhat.narkive.com/3axjIQyB/patch-0-5-build-time-disabling-of-auditd-network-listener
