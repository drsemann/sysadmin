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
```

**Criar pasta Zabbix e descompactar zip**

```
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

```# tasklist | findstr zabbix```