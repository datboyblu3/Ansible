alert ssh any any -> 134.209.124.236 !22 (msg:"SSH TRAFFIC on non-SSH port"; flow:to_client, not_established; classtype: misc-attack; target: dest_ip; sid:1000000;)

alert ssh any any -> 2001:DB8::1/32 !22 (msg:"SSH TRAFFIC on non-SSH port"; flow:to_client, not_established; classtype: misc-attack; target: dest_ip; sid:1000001;)

alert http any any -> 203.0.113.5 !80 (msg:"HTTP REQUEST on non-HTTP port"; flow:to_client, not_established; classtype:misc-activity; sid:1000002;)

alert http any any -> 2001:DB8::1/32 !80 (msg:"HTTP REQUEST on non-HTTP port"; flow:to_client, not_established; classtype:misc-activity; sid:1000003;)

alert tls any any -> 203.0.113.5 !443 (msg:"TLS TRAFFIC on non-TLS HTTP port"; flow:to_client, not_established; classtype:misc-activity; sid:1000004;)

alert tls any any -> 2001:DB8::1/32 !443 (msg:"TLS TRAFFIC on non-TLS HTTP port"; flow:to_client, not_established; classtype:misc-activity; sid:1000005;)
