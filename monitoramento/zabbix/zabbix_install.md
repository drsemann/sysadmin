# Instalando Zabbix Server (Debian 9)

## Instalando repositorio

```
# wget http://repo.zabbix.com/zabbix/3.4/debian/pool/main/z/zabbix-release/zabbix-release_3.4-1+stretch_all.deb
# dpkg -i zabbix-release_3.4-1+stretch_all.deb
# apt update
```

### Instalando o servidor Zabbix

```# apt install zabbix-server-mysql zabbix-frontend-php```

### Instalando libs adicionais

```# apt install php7.0-bcmath php7.0-mbstring php-sabre-xml```

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

### Configurando zabbix_server.conf

```
# vim /etc/zabbix/zabbix_server.conf
DBHost=localhost
DBName=zabbix
DBUser=zabbix
DBPassword=<password>
```
### Iniciando o serviço

```# systemctl start zabbix-server```

### Configurações /etc/apache2/conf-enabled/zabbix.conf
```
php_value max_execution_time 300
php_value memory_limit 128M
php_value post_max_size 16M
php_value upload_max_filesize 2M
php_value max_input_time 300
php_value always_populate_raw_post_data -1
php_value date.timezone America/Sao_Paulo
```

### Reiniciando Apache
```# systemctl restart apache2```

# Instalando e configurando Agente

### Instalando agente no Linux

**Deb**

```# apt install zabbix-agent```

**Rpm**

```# yum install zabbix-agent```

### Configuração básica

```
# Server=<IP Servidor Zabbix>
# Hostname=<Nome do host monitorado> (No cadastro do zabbix tem que ser o mesmo)
# ServerActive=<IP Servidor Zabbix>
```

### Instalando agente no Windows

**Baixar agente**

```
# https://www.zabbix.com/downloads/3.4.0/zabbix_agents_3.4.0.win.zip
# Criar pasta Zabbix no C:\ do host
# Criar pasta log dentro C:\Zabbix
# Descompactar arquivo zip
# Copiar zabbix_agentd.exe (Arquitetura do host 32 ou 64bits) e zabbix_agentd.conf para C:\Zabbix
```

**Instalar serviço do agente**

```# zabbix_agentd.exe -c zabbix_agentd.conf -i```

**Iniciar serviço**

```# zabbix_agentd.exe -x```

**Verificar execução do serviço**

```#tasklist | findstr zabbix```
