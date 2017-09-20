## Habilitando SNMP

#### Setar Comunidade

```# esxcli system snmp set --communities YOUR_COMM_STRING```

#### Habilitando o serviço

```# esxcli system snmp set --enable true```

#### Liberando no firewall para todos
```
# esxcli network firewall ruleset set --ruleset-id snmp --allowed-all true
# esxcli network firewall ruleset set --ruleset-id snmp --enabled true
```

#### Ou restringindo para uma rede somente
```
# esxcli network firewall ruleset set --ruleset-id snmp --allowed-all false
# esxcli network firewall ruleset allowedip add --ruleset-id snmp --ip-address 192.168.0.0/24
# esxcli network firewall ruleset set --ruleset-id snmp --enabled true
```

#### Reiniciando o serviço

```# /etc/init.d/snmpd restart```