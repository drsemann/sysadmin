### Verificando UUID host

Conectado no host

```# Connect-VIServer -Server "server" -User "user" -Password "pass"

Verificando UUID

```# Get-VMHost | Select Name,@{n="HostUUID";e={$_.ExtensionData.hardware.systeminfo.uuid}}```