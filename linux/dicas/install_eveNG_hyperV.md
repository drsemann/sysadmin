## Instalar Eve-NG no HyperV

#### Baixa iso de instalação
https://www.eve-ng.net/downloads/eve-ng-2

#### Requisitos Instalação

Cpu: 4 vCpu
Hd 300GB
Mem: 8GB

#### Instalação

Selecionar a opção **Install VM** no menu de boot

#### Pós instalação

Executar o seguinte comando no Powershell para habilitar o **Intel VT-x ou AMD-V**
```# Set-VMProcessor -VMName "NomedaVMnoHyperV" -ExposeVirtualizationExtensions $True```
