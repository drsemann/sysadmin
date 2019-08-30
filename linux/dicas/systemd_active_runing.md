### Ver serviços ativos ou rodando Systemd ###

#### Listando todos os serviços ####
``` 
# systemctl list-units --type=service
OU
# systemctl --type=service 
```

#### Listando os serviços ativos ####
```
# systemctl list-units --type=service --state=active
OU
# systemctl --type=service --state=active
```

#### Listando os serviços que estão rodando ####
```
# systemctl list-units --type=service --state=running 
OU
# systemctl --type=service --state=running
```
