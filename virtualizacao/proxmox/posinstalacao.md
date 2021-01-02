# Pos Instalação

Editar o arquivo **.bashrc** e descomentar as linhas:

```bash
PS1='${debian_chroot:+($debian_chroot)}\h:\w\$ '
umask 022
export LS_OPTIONS='--color=auto'
eval "`dircolors`"
alias ls='ls $LS_OPTIONS'
alias ll='ls $LS_OPTIONS -l'
alias l='ls $LS_OPTIONS -lA'
alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'
```

Adicionar em **/etc/environment** para resolver possivel erro de codificação do perl:

```bash
LANGUAGE=en_US.UTF-8
LANG=en_US.UTF-8
LC_ALL=en_US.UTF-8
```

Comentar a linha do repositorio do arquivo **/etc/apt/sources.list.d/pve-enterprise.list**:

```bash
#deb https://enterprise.proxmox.com/debian/pve buster pve-enterprise
```

Adicionar repositório **no-subscription** em **/etc/apt/sources.list**:

```bash
deb http://download.proxmox.com/debian buster pve-no-subscription
```

Efetuar o update e upgrade do sistema:

```bash
# apt update -y
# apt upgrade -y
```

Instalar **ifupdown2** para que seja alterado as configurações de rede sem ser preciso reiniciar:

```bash
# apt install ifupdown2 -y
```
