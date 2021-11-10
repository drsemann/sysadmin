<!--
  Title: Sysadmin
  Description: Lista de howto e dicas de ferramenta e serviços de infra-estrutura.
  Author: drsemann
  -->

# Sysadmin

Coleção de howto e dicas.


## Conteúdo

 - [Plataformas](#plataformas)
 - [Networking](#networking)
 - [Monitoramento](#monitoramento)
 - [Banco de Dados](#banco-de-dados)
 - [Governança de TI](#governança-de-ti)
 - [Dicas Rápidas](#dicas)
 - [Virtualização](#virtualização)

## Plataformas

 - Linux
   - Fedora
     - <a href="https://github.com/drsemann/sysadmin/blob/master/linux/fedora/fedora_posinstall.md">Pos-Instalação</a>
   - Debian
     - <a href="https://github.com/drsemann/sysadmin/blob/master/linux/debian/install_remmina.md">Instalação Remmina 1.2</a>
	 - <a href="https://github.com/drsemann/sysadmin/blob/master/linux/debian/wireguard_aws.md">Instalação wireguard no AWS</a>
   - Redhat
     - <a href="https://github.com/drsemann/sysadmin/blob/master/linux/redhat/recuperar_senha_root.md">Recuperação de senha root</a>
	 - <a href="https://github.com/drsemann/sysadmin/blob/master/linux/redhat/autenticacao_pam_squid.md">Autenticação PAM Squid</a>
	 - <a href="https://github.com/drsemann/sysadmin/blob/master/linux/redhat/remover_erro_squidlog.md">Erro log Squid</a>

   - Dicas
    	- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/progresso_dd.md">Acompanhar Progresso comado dd</a>
    	- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/allow_openvpn_selinux.md">Liberar Openvpn SELinux</a>
    	- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/java_gtk_theme.md">Habilitar tema gtk aplicações java</a>
		- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/postfix_auth_failed.md">Verificar login falho postfix</a>
		- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/systemd_active_runing.md">Verificar serviços ativos e rodando systemd</a>
		- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/install_eveNG_hyperV.md">Instalar Eve-NG no HyperV</a>
		- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/change_interface_name.md">Alterar nome interfaces</a>
		- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/data_instalacao.md">Data de Instalação Sistema</a>
		- <a href="https://github.com/drsemann/sysadmin/blob/master/linux/dicas/compartilhamento_semsenha.md">Compartilhamento sem senha Samba</a>	
 - MacOS X
   - Dicas
     - <a href="https://github.com/drsemann/sysadmin/blob/master/macosx/dicas/ifconfig_alias.md">Alias na Interface</a>
 - Windows
 	 - Active Directory
 		 - <a href="https://github.com/drsemann/sysadmin/blob/master/windows/activedirectory/migra_win08_win12.md">Migração AD Windows Server 2008 para 2012R2</a>
		 - <a href="https://github.com/drsemann/sysadmin/blob/master/windows/activedirectory/sincronizacao_ad.md">Sincronização AD e testes</a>
		 - <a href="https://github.com/drsemann/sysadmin/blob/master/windows/alterar_mtu_testar.md">Testando e alterando o mtu no Windows</a>

 - VMware
 	 - Dicas
 		 - <a href="https://github.com/drsemann/sysadmin/blob/master/vmware/dicas/enable_snmp.md">Habilitar SNMP</a>
 		 - <a href="https://github.com/drsemann/sysadmin/blob/master/vmware/dicas/check_uuid.md">Checar UUID Host</a>
		 - <a href="https://github.com/drsemann/sysadmin/blob/master/vmware/dicas/install_powercli.md">Instalando PowerCLI</a>

## Networking

 - Cisco
 	- Roteadores
 		- <a href="https://github.com/drsemann/sysadmin/blob/master/cisco/roteadores/config_dhcp.md">DHCP</a>
 		- Dicas
 			- <a href="https://github.com/drsemann/sysadmin/blob/master/cisco/roteadores/dicas/list_con_vpn.md">Listar conexões vpn ipsec</a>

 - Juniper
 - Fortinet
 - Ubiquiti
 	- Roteadores
 		- <a href="https://github.com/drsemann/sysadmin/blob/master/ubiquiti/roteadores/site_to_site_er_cisco.md">Vpn site-to-site entre Edge Router Lite e Cisco Router</a>
	  	- <a href="https://github.com/drsemann/sysadmin/blob/master/ubiquiti/roteadores/troubleshooting_vpn_ipsec.md">Troubleshooting IPsec </a>
		- <a href="https://github.com/drsemann/sysadmin/blob/master/ubiquiti/roteadores/dns_forward_ad.md">Enviando consultas DNS dominio AD </a>
	- Dicas
 - pfSense
	- Dicas
		- <a href="https://github.com/drsemann/sysadmin/blob/master/pfsense/dicas/interface_hp_bge.md">Desabilitar watchdog interface bge HP</a>
		- <a href="https://github.com/drsemann/sysadmin/blob/master/pfsense/dicas/recuperar_filesystem.md">Recuperar sistema corrompido</a> 


## Monitoramento

 - Zabbix
 	- <a href="https://github.com/drsemann/sysadmin/blob/master/monitoramento/zabbix/zabbix_install.md">Instalação Zabbix Debian</a>
 	- <a href="https://github.com/drsemann/sysadmin/blob/master/monitoramento/zabbix/zabbix_agent_install.md">Instalação Agente</a>
 	- <a href="https://github.com/drsemann/sysadmin/blob/master/monitoramento/zabbix/macros_zabbix.md">Macros Zabbix</a>


## Banco de Dados
 
 - MariaDB
 	-  <a href="https://github.com/drsemann/sysadmin/blob/master/dbs/mariadb/setar_pass_root.md">Setando e alterando senha root</a>

## Governança de TI

- Glpi
	- <a href="https://github.com/drsemann/sysadmin/blob/master/governancati/glpi/install_glpi_debian.md">Instalação Glpi no Debian</a>

	- <a href="https://github.com/drsemann/sysadmin/blob/master/governancati/glpi/install_plugin_dashboard.md">Instalação do plugin dashboard no Glpi</a>

## Virtualização

- <a href="https://github.com/drsemann/sysadmin/blob/master/virtualizacao/proxmox/proxmox.md">Proxmox</a>


