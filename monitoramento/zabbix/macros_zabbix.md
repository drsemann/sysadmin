## Macros Zabbix

### Macros Zabbix

```
{HOST.NAME}
{HOST.CONN}
{$SNMP_COMMUNITY}
```

### Cadastro Host ESX | Macros

```
{$PASSWORD}
{$URL} : https://iphost/sdk
{$USERNAME}
{$UUID}
```

### Macros Email Zabbix

```
{HOST.NAME} : {TRIGGER.STATUS}

Hora:  {EVENT.TIME}
Data : {EVENT.DATE}
Problema: {TRIGGER.NAME}
```