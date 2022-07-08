# IP Tables

Add rule:

```iptables -A [INPUT/OUTPUT/FORWARD] -p [tcp] -s [source ip] --dport [port number e.g. 22, 80] -j ACCEPT```


List all ip tables

```iptables -L```

Delete rule
iptables -D [OUTPUT] 5