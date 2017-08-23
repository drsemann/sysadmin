# Instalando Zabbix Server (Debian 9)

## Instalando repositorio

```
# wget http://repo.zabbix.com/zabbix/3.4/debian/pool/main/z/zabbix-release/zabbix-release_3.4-1+stretch_all.deb
# dpkg -i zabbix-release_3.4-1+stretch_all.deb
# Pcapt update
```

### Instalando o servidor Zabbix

```# apt install zabbix-server-mysql zabbix-frontend-php```

### Criando o banco de dados e importando tabelas

#### Criando
```# mysql -uroot -p```
``` 
# mysql> create database zabbix character set utf8 collate utf8_bin;
# mysql> grant all privileges on zabbix.* to zabbix@localhost identified by '<password>';
# mysql> quit;
```

#### Importando
```# zcat /usr/share/doc/zabbix-server-mysql/create.sql.gz | mysql -uzabbix -p zabbix```