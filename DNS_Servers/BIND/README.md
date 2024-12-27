1. Update the Package Index First, make sure your package list is up to date: (Bind configuration)


```bash
sudo apt update
```

2. Install the bind9 package (the BIND DNS server) and its associated utilities:

```bash
sudo apt install bind9 bind9utils bind9-doc
```

3. Start the BIND9 service and enable it to start on boot:

```bash
sudo systemctl start bind9
sudo systemctl enable bind9
```

4. Configure the BIND Server

### Example of basic configuration in /etc/bind/named.conf.local:

//
// Do any local configuration here
//

```bash
zone "flaskfarnodes.in" IN {
        type master;
        file "/etc/bind/zones/forward.zone.flaskfarnodes.in";
        allow-update {none;};
};
```

// Consider adding the 1918 zones here, if they are not used in your
// organization
//include "/etc/bind/zones.rfc1918";

### Example of basic configuration in /etc/bind/named.conf.options

options {
	directory "/var/cache/bind";

```bash
        recursion yes;
        listen-on port 53 {any;};
        allow-query {any;};
```
	// If there is a firewall between you and nameservers you want
	// to talk to, you may need to fix the firewall to allow multiple
	// ports to talk.  See http://www.kb.cert.org/vuls/id/800113

	// If your ISP provided one or more IP addresses for stable 
	// nameservers, you probably want to use them as forwarders.  
	// Uncomment the following block, and insert the addresses replacing 
	// the all-0's placeholder.

	// forwarders {
	// 	0.0.0.0;
	// };

	//========================================================================
	// If BIND logs error messages about the root key being expired,
	// you will need to update your keys.  See https://www.isc.org/bind-keys
	//========================================================================
	dnssec-validation auto;

	listen-on-v6 { any; };
};


### Example of basic configuration in /etc/bind/etc/bind/zones$ 

forward.zone.flaskfarnodes.in 
$TTL 2d
@   IN  SOA dns.flaskfarnodes.in. admin.flaskfarnodes.in. (
        1          ; Serial
        604800     ; Refresh
        86400      ; Retry
        2419200    ; Expire
        604800     ; Negative cache TTL
)

;; NS record
@       IN  NS  dns.flaskfarnodes.in.

;; A records
@       IN  A   192.168.29.194   ; flaskfarnodes.in points to the BIND server (ip server)
dns     IN  A   192.168.29.124   ; dns.flaskfarnodes.in points to the BIND server (ip DNS)


5. After editing your configuration files, check for syntax errors:

```bash
sudo named-checkconf
sudo named-checkzone example.com /etc/bind/db.example.com
sudo named-checkzone 1.168.192.in-addr.arpa /etc/bind/db.192.168.1
```

6. Once you have configured the server, restart BIND to apply the changes:

```bash
sudo systemctl restart bind9
```

7. You can test your BIND server using the dig command. For example, to query your DNS server for example.com:

```bash
dig @localhost example.com
```

8. rahul@bind:/etc/default$ cat named 

# run resolvconf?
RESOLVCONF=no

# startup options for the server (Bind Server)
OPTIONS="-4 -u bind"


###  After Bind create entry HOST Localhost

```bash
/etc/hosts
/etc/resolv.conf
```


