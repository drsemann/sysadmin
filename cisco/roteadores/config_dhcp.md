### Configuração reserva DHCP

```
ip dhcp pool poolname
  host ip mask
  client-identifier mac
  client-name nome
  domain-name domain-name
  dns-server dns servers
  default-router gateway
```

*O MAC deve seguir o seguinte padrão **01**00.5079.6468.05, o 01 identifica o tipo de mídia, 01(Ethernet).*

*Exemplo:*
*29-D2-44-3F-12-70 -> 0129.d244.3f12.70*
  
  
## Comandos opcionais

**Habilitar debug do servidor DHCP**

```# debug ip dhcp server packet```

**Remover ip atribuido no DHCP**

```# clear ip dhcp binding "IP"```
  
**Remover MAC da tabela ARP**

```# clear ip arp "MAC"```

fonte: https://networklessons.com/cisco/ccie-routing-switching/dhcp-static-binding-on-cisco-ios/

fonte: https://supportforums.cisco.com/discussion/11779701/binding-already-exists-xxxx-help