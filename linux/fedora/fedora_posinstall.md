## Deixando o Fedora totalmente em Português

## Instale o GNOME Tweak Tool

```sudo dnf install gnome-tweak-tool```

 ## Instalação do Vscode

```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
sudo dnf check-update
sudo dnf update -y
sudo dnf install code -y
```

## Instalação do Teams
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
sudo dnf install teams -y
```

## Instalação do skype
```
sudo curl -o /etc/yum.repos.d/skype-stable.repo https://repo.skype.com/rpm/stable/skype-stable.repo
sudo dnf install skypeforlinux -y
```

## Instalação do repositorio rpmfusion
```
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm -y
sudo dnf install https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm -y
```

## Instalação do Brave
```
sudo dnf install dnf-plugins-core
sudo dnf config-manager --add-repo https://brave-browser-rpm-release.s3.brave.com/x86_64/
sudo rpm --import https://brave-browser-rpm-release.s3.brave.com/brave-core.asc
sudo dnf install brave-browser -y
```

## Instalação do Notion Linux
```
wget https://notion.davidbailey.codes/notion-linux.repo
sudo mv notion-linux.repo /etc/yum.repos.d/notion-linux.repo
sudo dnf install notion-desktop -y
```

## Temas Tilix
```
git clone https://codeberg.org/SnowCode/tilix-colors.git
mv tilix-colors/*.json ~/.config/tilix/schemes
rm -r tilix-colors
```

## Onedrive no Linux
```
sudo dnf install onedrive
onedrive (primeira execução para configurar)
onedrive --synchronize (Primeira sincronização)
```

# Rodar como Serviço
```
systemctl --user enable onedrive
systemctl --user start onedrive
```

# Ver log de sincronização
```
journalctl --user-unit=onedrive -f
```

## Alterar secgurança para funcionar com Cisco Anyconnect mais antigos
```
sudo update-crypto-policies --set DEFAULT:FEDORA32
```