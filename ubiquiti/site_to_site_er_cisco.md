# Configuração de exemplo de vpn site-to-site entre Edge Route e Cisco Router
### Roteador Cisco 
```
crypto isakmp policy 1
 encr 3des
 authentication pre-share
 group 2
crypto isakmp key YOURPRESHAREDKEYHERE address 8.8.8.8 no-xauth

crypto map SDM_CMAP_1 1 ipsec-isakmp
 description Tunnel to Ubnt Demo
 set peer 8.8.8.8
 set transform-set ESP-3DES-SHA1
 match address 107

access-list 107 permit ip host 10.11.0.63 10.12.10.0 0.0.0.255
```

### Edge Router Lite

```
disable-uniqreqids
 esp-group vpntunnel {
     compression disable
     lifetime 1800
     mode tunnel
     pfs disable
     proposal 1 {
         encryption 3des
         hash sha1
     }
 }
 ike-group vpntunnel {
     lifetime 28800
     proposal 1 {
         dh-group 2
         encryption 3des
         hash sha1
     }
 }
 ipsec-interfaces {
     interface eth1
 }
 logging {
     log-modes all
     log-modes control
 }
 nat-traversal disable
 site-to-site {
     peer 4.4.4.4 {
         authentication {
             mode pre-shared-secret
             pre-shared-secret YOURPRESHAREDKEYHERE
         }
         connection-type initiate
         default-esp-group vpntunnel
         ike-group HostedVoice
         local-ip 8.8.8.8
         tunnel 10 {
             allow-nat-networks disable
             allow-public-networks disable
             esp-group vpntunnel
             local {
                 subnet 10.12.10.0/24
             }
             remote {
                 subnet 10.11.0.63/32
             }
         }
     }
 }
 The commands used on the ER are as follows
configure
set vpn ipsec disable-uniqreqids
set vpn ipsec esp-group vpntunnel
set vpn ipsec esp-group vpntunnel compression disable
set vpn ipsec esp-group vpntunnel lifetime 1800
set vpn ipsec esp-group vpntunnel mode tunnel
set vpn ipsec esp-group vpntunnel pfs disable
set vpn ipsec esp-group vpntunnel proposal 1
set vpn ipsec esp-group vpntunnel proposal 1 encryption 3des
set vpn ipsec esp-group vpntunnel proposal 1 hash sha1
set vpn ipsec ike-group vpntunnel
set vpn ipsec ike-group vpntunnel lifetime 28800
set vpn ipsec ike-group vpntunnel proposal 1
set vpn ipsec ike-group vpntunnel proposal 1 dh-group 2
set vpn ipsec ike-group vpntunnel proposal 1 encryption 3des
set vpn ipsec ike-group vpntunnel proposal 1 hash sha1
set vpn ipsec ipsec-interfaces interface eth1
set vpn ipsec logging log-modes all
set vpn ipsec logging log-modes control
set vpn ipsec nat-traversal disable
set vpn ipsec site-to-site peer 4.4.4.4 (PUT CISCO PUBLIC IP HERE)
set vpn ipsec site-to-site peer 4.4.4.4 local-ip 8.8.8.8 (REAPLCE 4.4.4.4 with your Cisco Public IP, Replace 8.8.8.8 with your ERL public IP)
set vpn ipsec site-to-site peer 4.4.4.4 authentication mode pre-shared-secret
set vpn ipsec site-to-site peer 4.4.4.4 authentication pre-shared-secret mysecretkey
set vpn ipsec site-to-site peer 4.4.4.4 connection-type initiate
set vpn ipsec site-to-site peer 4.4.4.4 default-esp-group vpntunnel
set vpn ipsec site-to-site peer 4.4.4.4 ike-group vpntunnel
set vpn ipsec site-to-site peer 4.4.4.4 tunnel 1
set vpn ipsec site-to-site peer 4.4.4.4 tunnel 1 esp-group vpntunnel
set vpn ipsec site-to-site peer 4.4.4.4 tunnel 1 local subnet 10.12.10.0/24 (THIS IS THE LAN OF THE ER)
set vpn ipsec site-to-site peer 4.4.4.4 tunnel 1 remote subnet 10.11.0.63/32 (THIS IS THE LAN OF THE CISCO)
commit
```

Exemplo tirado do forum da ubiquiti: 


https://community.ubnt.com/t5/EdgeMAX/EdgeRouter-to-Cisco-Router-VPN-Example/td-p/803838