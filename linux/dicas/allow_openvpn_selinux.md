#### Liberar Openvpn no SELinux ####

##### Alternativa 1 #####
```
# sudo ausearch -c 'openvpn' --raw | sudo audit2allow -M my-openvpn
# sudo semodule -X 300 -i my-openvpn.pp
```

##### Alternativa 2 #####
```
# mkdir ~/.cert
# mkdir ~/.openvpn
# mv *.p12 *.key ~/.cert
# mv *.ovpn ~/.openvpn
# restorecon -R -v ~/.cert


