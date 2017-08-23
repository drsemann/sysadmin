# Instalando Zabbix Server (Debian 9)

## Instalando repositorio

```
wget http://repo.zabbix.com/zabbix/3.4/debian/pool/main/z/zabbix-release/zabbix-release_3.4-1+stretch_all.deb
dpkg -i zabbix-release_3.4-1+stretch_all.deb
apt update
```

### Instalando o servidor Zabbix

``` # apt install zabbix-server-mysql zabbix-frontend-php ```