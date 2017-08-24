## Habilitando Delta RPM

Instalando o pacote

<code>sudo dnf install deltarpm</code>
  
Para habilitar o deltarpm edite o arquivo /etc/dnf/dnf.conf e adicione a linha abaixo

<code>deltarpm=1</code>

## Deixando o Fedora totalmente em Português

Instalando o gerenciador de idiomas

<code>sudo dnf install system-config-language</code>

Execute o comando abaixo e selecione seu idioma, ele fará o download de todos os pacotes de seu idioma

<code>system-config-language</code>
  
## Instale o GNOME Tweak Tool

Ferramenta para gerenciamento de configurações e mudança na aparência do gnome.

Instalando o pacote

<code>sudo dnf install gnome-tweak-tool</code>

## Instale o Yumex

Gerenciador de pacotes em modo gráfico.

Instalando o pacote
  
<code>sudo dnf install yumex-dnf</code>
  
## Adicionando repositórios RPM Fusion e instalando codecs multimídia

Por questões legais, o Fedora (e a grande maioria das distros Linux) não disponibiliza nos repositórios oficiais os codecs para a reprodução de arquivos MP4, WMA, dentre outros, exceto o suporte a reprodução de arquivos MP3, que a partir do Fedora 25 os pacotes necessários estão incluídos nos repositórios oficiais (gstreamer1-plugin-mpg123 e mpg123-libs). Para reproduzir somente arquivos MP3, remova o pacote "gstreamer1-plugins-ugly" do sistema (caso esteja instalado):

<code>sudo dnf remove gstreamer1-plugins-ugly</code>

E instale os pacotes a seguir:

<code>sudo dnf install gstreamer1-plugin-mpg123 mpg123-libs</code>

Com isso você poderá escutar as suas músicas em MP3 no Fedora sem a necessidade de adicionar repositórios adicionais.

MAS, se quiser reproduzir outros formatos multimídia (além do MP3) no Fedora, a solução é adicionar os repositórios RPM Fusion e instalar todos os codecs necessários por eles.

O RPM Fusion é a fusão dos projetos Dribble, Freshrpms e Livna, simplificando assim a vida do usuário final. O RPM Fusion é dividido em dois repositórios distintos, o "Free", que contém softwares de código aberto, e o "Non-free", que disponibiliza softwares proprietários, codecs e outros. Para adicioná-los, copie e cole os comandos a seguir no terminal:

<code>su -c 'dnf install http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm'</code>
  
Importe a chave GPG do repositório com:

<code>sudo rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-rpmfusion-free-fedora-25</code>
  
RPM Fusion Non-free

<code>su -c 'dnf install http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm'</code>

Remova o pacote "gstreamer1-plugin-mpg123" (caso esteja instalado no sistema):

<code>sudo dnf remove gstreamer1-plugin-mpg123</code>

E após, instale os codecs multimídia com:

<code>sudo dnf install amrnb amrwb faad2 flac ffmpeg gpac-libs lame libfc14audiodecoder mencoder mplayer x264 x265 gstreamer-plugins-espeak gstreamer-plugins-fc gstreamer-rtsp gstreamer-plugins-good gstreamer-plugins-bad gstreamer-plugins-bad-free-extras gstreamer-plugins-bad-nonfree gstreamer-plugins-ugly gstreamer-ffmpeg gstreamer1-plugins-base gstreamer1-libav gstreamer1-plugins-bad-free-extras gstreamer1-plugins-bad-freeworld gstreamer1-plugins-base-tools gstreamer1-plugins-good-extras gstreamer1-plugins-ugly gstreamer1-plugins-bad-free gstreamer1-plugins-good </code>

## Instalando o Telegram no Fedora via repositório

Já para o Fedora Workstation, execute o comando abaixo para adicionar o repositório no sistema:

<code>sudo dnf copr enable youssefmsourani/telegram-desktop</code>

Importe a chave de assinatura do repositório:

<code>sudo rpm --import https://copr-be.cloud.fedoraproject.org/results/youssefmsourani/telegram-desktop/pubkey.gpg</code>

E instale o Telegram Desktop em seguida com:

<code>sudo dnf install telegram-desktop</code>

Aguarde enquanto o Telegram é instalado e após, abra o mesmo através do atalho criado no menu de aplicativos.

<code>Instalando o Spotify</code>

Para instalar o Spotify no Fedora, é necessário que tenha habilitado os repositórios RPMFusion no sistema. Feito isso, abra um terminal e adicione o repositório "negativo17 - Spotify client":

<code>sudo dnf config-manager --add-repo=http://negativo17.org/repos/fedora-spotify.repo</code>

Importe a chave de assinatura do repositório:

<code>sudo rpm --import http://negativo17.org/repos/RPM-GPG-KEY-slaanesh</code>

E instale o Spotify com:

<code>sudo dnf install spotify-client</code>
  
## Instale o Dropbox no Fedora

O Dropbox é um serviço de armazenamento e compartilhamento de arquivos na nuvem. Se você é usuário do Dropbox e habilitou os repositórios RPM Fusion, instale-o no Fedora com:

<code>sudo dnf install nautilus-dropbox python-gpgme</code>
  
## Instalando Google Chrome

Importe a chave de assinatura da Google:

<code>sudo rpm --import https://dl.google.com/linux/linux_signing_key.pub</code>
  
Adicione o repositório do Google Chrome no sistema, para isto, copie e cole todo o conteúdo abaixo no terminal e após, pressione Enter:

<code>
sudo tee /etc/yum.repos.d/google-chrome.repo <<RPMREPO
[google-chrome]
name=google-chrome
baseurl=http://dl.google.com/linux/chrome/rpm/stable/x86_64
enabled=1
gpgcheck=1
gpgkey=https://dl.google.com/linux/linux_signing_key.pub
RPMREPO
</code>

Feito isso, instale o Google Chrome (estável) com:

<code>sudo dnf install google-chrome-stable</code>

## Instalando o Adobe Flash Player

Atualmente, a grande maioria dos sites mais acessados (como, por exemplo, o YouTube) já não "dependem" do Adobe Flash Player instalado, mas, caso necessite utilizá-lo (no Mozilla Firefox), basta adicionar o repositório da Adobe no sistema:

Se instalou o Fedora de 64 bits, execute:

<code>sudo dnf install http://linuxdownload.adobe.com/adobe-release/adobe-release-x86_64-1.0-1.noarch.rpm</code>

Se instalou o Fedora de 32 bits, execute:

<code>sudo dnf install http://linuxdownload.adobe.com/adobe-release/adobe-release-i386-1.0-1.noarch.rpm</code>

Importe a chave de assinatura do repositório Adobe:

<code>sudo rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-adobe-linux</code>

E instale o Adobe Flash Player com:

<code>sudo dnf install flash-plugin</code>
  
## Instalando o OpenJDK (o Java de código aberto)

Para instalar o OpenJDK no Fedora e também o plugin IcedTea Web (que disponibiliza o plugin Java para navegadores) basta digitar:

<code>sudo dnf install java-openjdk icedtea-web</code>

## Instale o Dropbox

O Dropbox é um serviço de armazenamento e compartilhamento de arquivos na nuvem. Se você é usuário do Dropbox e habilitou os repositórios RPM Fusion, instale-o no Fedora com:

<code>sudo dnf install nautilus-dropbox python-gpgme</code>
  
## Instalando o Editor Atom
  
 Instale os plugins 

<code>sudo dnf install dnf-plugins-core</code>
  
 Habilitando o repositório

<code>sudo dnf copr enable mosquito/atom</code>
 
Instalando o editor 

<code>sudo dnf install atom</code>

----

fonte <a href="http://www.blogopcaolinux.com.br/2016/11/Guia-de-pos-instalacao-do-Fedora-25-Workstation.html">BlogOpcaoLinux</a>

fonte Instalação Atom <a href="https://andrewwippler.com/2016/03/18/atom-editor-on-fedora/"> - Andrew Wippler's Sketchpad</a>