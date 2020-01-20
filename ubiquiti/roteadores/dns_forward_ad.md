# Configurando redirecionamento consulta dominio para AD

## Adicionando entrada no dnsmasq
```# echo 'server=/dominio/ipdoactivedirectory' > /etc/dnsmasq.d/forward-ad.conf```
## Restart serviço DNSMASQ
```# service dnsmasq restart```