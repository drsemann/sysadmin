## Deixando o Fedora totalmente em Português

## Instale o GNOME Tweak Tool

<code>sudo dnf install gnome-tweak-tool</code>

 ## Instalação do Vscode

<code>
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
sudo dnf check-update
sudo dnf update -y
sudo dnf install code -y
</code>

## Instalação do Teams
<code>
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
sudo dnf install teams -y
</code>

## Instalação do skype
<code>
sudo curl -o /etc/yum.repos.d/skype-stable.repo https://repo.skype.com/rpm/stable/skype-stable.repo
sudo dnf install skypeforlinux -y
</code>

## Instalação do repositorio rpmfusion
<code>
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm -y
sudo dnf install https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm -y
</code>

## Instalação do Brave
<code>
sudo dnf install dnf-plugins-core
sudo dnf config-manager --add-repo https://brave-browser-rpm-release.s3.brave.com/x86_64/
sudo rpm --import https://brave-browser-rpm-release.s3.brave.com/brave-core.asc
sudo dnf install brave-browser -y
</code>

## Instalação do Notion Linux
<code>
wget https://notion.davidbailey.codes/notion-linux.repo
sudo mv notion-linux.repo /etc/yum.repos.d/notion-linux.repo
sudo dnf install notion-desktop -y
</code>

## Temas Tilix
<code>
git clone https://codeberg.org/SnowCode/tilix-colors.git
mv tilix-colors/*.json ~/.config/tilix/schemes
rm -r tilix-colors
</code>

## Onedrive no Linux
<code>
sudo dnf install onedrive
onedrive (primeira execução para configurar)
onedrive --synchronize (Primeira sincronização)
</code>

# Rodar como Serviço
<code>
systemctl --user enable onedrive
systemctl --user start onedrive
</code>

# Ver log de sincronização
<code>
journalctl --user-unit=onedrive -f
</code>

## Alterar secgurança para funcionar com Cisco Anyconnect mais antigos
<code>
sudo update-crypto-policies --set DEFAULT:FEDORA32
</code>