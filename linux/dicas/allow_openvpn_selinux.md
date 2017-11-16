#### Liberar Openvpn no SELinux ####
```
# sudo ausearch -c 'openvpn' --raw | sudo audit2allow -M my-openvpn
# sudo semodule -X 300 -i my-openvpn.pp
```
