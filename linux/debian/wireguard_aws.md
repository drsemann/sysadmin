### Instalando o wireguard no AWS ###

#### Instalando o wireguard ####

```# apt install wireguard```

#### Habilitando o suporte da VM ####

```
   # uname --kernel-release
   # apt install linux-headers-cloud-amd64
   # apt install --reinstall wireguard-dkms
   # reboot
```
