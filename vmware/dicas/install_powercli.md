### Instalando VMWare PowerCLI ###

#### Pesquisando o Modulo ####

```# Find-Module -Name VMware.PowerCLI```

#### Instalando Modulo ####

**Instalando para usuário atual somente**

```# Install-Module -Name VMware.PowerCLI -Scope CurrentUser```

**Instalando para todos usuários**

```# Install-Module -Name VMware.PowerCLI -Scope AllUsers```

**Caso ocorra erro na instalação para todos usuários adicionar *-AllowClobber* ao final do comando**

```# Install-Module -Name VMware.PowerCLI -Scope AllUsers -AllowClobber```

#### LIberar executar scripts PowerShell ####

```# Set-ExecutionPolicy Unrestricted```

