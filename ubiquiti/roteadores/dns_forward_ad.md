# Configurando redirecionamento consulta dominio para AD

## Adicionando entrada no dnsmasq
```# echo 'server=/dominio/ipdoactivedirectory' > /etc/dnsmasq.d/forward-ad.conf```
## Restart serviço DNSMASQ
```# service dnsmasq restart```

Baseado em: https://community.ui.com/questions/Edge-Router-and-Windows-Active-Directory-DNS/509f608c-20c1-4a63-bb17-c0a35a19ac74