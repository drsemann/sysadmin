# Instalando GLPI

### Preparando o servidor

```
 # apt install ca-certificates apache2 libapache2-mod-php php-cli php php-gd php-imap php-ldap php-mysql php-soap php-xmlrpc zip unzip bzip2 unrar-free php-snmp php-curl mariadb-server php7.0-bcmath php7.0-mbstring php-sabre-xml php-apcu-bc -y

```

### Download do GLPI

``` # wget https://github.com/glpi-project/glpi/releases/download/9.1.6/glpi-9.1.6.tgz ```

### Descompactar

``` # tar -zxvf glpi-9.1.6.tgz ```

### Copiar glpi para pasta html

``` # cp -Rf glpi /var/www/html ```

### Configurando Apache

``` # vim /etc/apache2/conf-available/glpi.conf ```

### Inserir configuração do GLPI

```
# <Directory "/var/www/html/glpi">
#   AllowOverride All
# </Directory>
```

### Habilitar a configuração do GLPI no Apache

``` # a2enconf /etc/apache2/conf-available/glpi.conf ```

### Reiniciar o Apache

``` # systemctl restart apache2 ```

### Permissionamento pasta GLPI

```
# chmod 775 -R /var/www/html/glpi
# chown www-data. -R /var/www/html/glpi
```

### Criando usuário e banco de dados

```
# mysql -u root
# mysql> create database glpi;
# mysql> create user 'glpi'@'localhost' identified by '<passowrd>';
# mysql> grant all on glpi.* to glpi identified by '<password>';
# mysql> quit;
```

