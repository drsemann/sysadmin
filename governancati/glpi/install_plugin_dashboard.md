# Instalando Plugin Dashboard no Glpi

### Baixando plugin

``` # wget https://forge.glpi-project.org/attachments/download/2189/GLPI-dashboard_plugin-0.8.5.tar.gz ```

### Descompactar

``` # tar -zxvf GLPI-dashboard_plugin-0.8.5.tar.gz ```

### Mover pasta para /var/www/html/glpi/plugins/

``` # mv dashboard/ /var/www/html/glpi/plugins/ ```

### Permissionamento

``` # chown www-data. -R /var/www/html/glpi/plugins/dashboard/ ```
