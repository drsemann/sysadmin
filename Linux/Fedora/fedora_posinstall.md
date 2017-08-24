## Habilitando Delta RPM

Instalando o pacote
  sudo dnf install deltarpm
  
Para habilitar o deltarpm edite o arquivo /etc/dnf/dnf.conf e adicione a linha abaixo
  deltarpm=1

## Deixando o Fedora totalmente em Português

### Instalando o gerenciador de idiomas
  sudo dnf install system-config-language

### Execute o comando abaixo e selecione seu idioma, ele fará o download de todos os pacotes de seu idioma
  system-config-language
  
## Instale o GNOME Tweak Tool

Ferramenta para gerenciamento de configurações e mudança na aparência do gnome.

Instalando o pacote
  sudo dnf install gnome-tweak-tool

===== Instale o Yumex =====

Gerenciador de pacotes em modo gráfico.

Instalando o pacote
  sudo dnf install yumex-dnf
  
===== Adicionando repositórios RPM Fusion e instalando codecs multimídia =====

Por questões legais, o Fedora (e a grande maioria das distros Linux) não disponibiliza nos repositórios oficiais os codecs para a reprodução de arquivos MP4, WMA, dentre outros, exceto o suporte a reprodução de arquivos MP3, que a partir do Fedora 25 os pacotes necessários estão incluídos nos repositórios oficiais (gstreamer1-plugin-mpg123 e mpg123-libs). Para reproduzir somente arquivos MP3, remova o pacote "gstreamer1-plugins-ugly" do sistema (caso esteja instalado):

  sudo dnf remove gstreamer1-plugins-ugly

E instale os pacotes a seguir:

  sudo dnf install gstreamer1-plugin-mpg123 mpg123-libs

 Com isso você poderá escutar as suas músicas em MP3 no Fedora sem a necessidade de adicionar repositórios adicionais.

MAS, se quiser reproduzir outros formatos multimídia (além do MP3) no Fedora, a solução é adicionar os repositórios RPM Fusion e instalar todos os codecs necessários por eles.

O RPM Fusion é a fusão dos projetos Dribble, Freshrpms e Livna, simplificando assim a vida do usuário final. O RPM Fusion é dividido em dois repositórios distintos, o "Free", que contém softwares de código aberto, e o "Non-free", que disponibiliza softwares proprietários, codecs e outros. Para adicioná-los, copie e cole os comandos a seguir no terminal:

  su -c 'dnf install http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm'
  
Importe a chave GPG do repositório com:

  sudo rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-rpmfusion-free-fedora-25
  
RPM Fusion Non-free

  su -c 'dnf install http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm'

Remova o pacote "gstreamer1-plugin-mpg123" (caso esteja instalado no sistema):

  sudo dnf remove gstreamer1-plugin-mpg123

E após, instale os codecs multimídia com:

  sudo dnf install amrnb amrwb faad2 flac ffmpeg gpac-libs lame libfc14audiodecoder mencoder mplayer x264 x265 gstreamer-plugins-espeak gstreamer-plugins-fc gstreamer-rtsp gstreamer-plugins-good gstreamer-plugins-bad gstreamer-plugins-bad-free-extras gstreamer-plugins-bad-nonfree gstreamer-plugins-ugly gstreamer-ffmpeg gstreamer1-plugins-base gstreamer1-libav gstreamer1-plugins-bad-free-extras gstreamer1-plugins-bad-freeworld gstreamer1-plugins-base-tools gstreamer1-plugins-good-extras gstreamer1-plugins-ugly gstreamer1-plugins-bad-free gstreamer1-plugins-good

===== Instalando o Telegram no Fedora via repositório =====

Já para o Fedora Workstation, execute o comando abaixo para adicionar o repositório no sistema:

  sudo dnf copr enable youssefmsourani/telegram-desktop

Importe a chave de assinatura do repositório:

  sudo rpm --import https://copr-be.cloud.fedoraproject.org/results/youssefmsourani/telegram-desktop/pubkey.gpg

E instale o Telegram Desktop em seguida com:

  sudo dnf install telegram-desktop

Aguarde enquanto o Telegram é instalado e após, abra o mesmo através do atalho criado no menu de aplicativos.

===== Instalando o Spotify =====

Para instalar o Spotify no Fedora, é necessário que tenha habilitado os repositórios RPMFusion no sistema. Feito isso, abra um terminal e adicione o repositório "negativo17 - Spotify client":

  sudo dnf config-manager --add-repo=http://negativo17.org/repos/fedora-spotify.repo

Importe a chave de assinatura do repositório:

  sudo rpm --import http://negativo17.org/repos/RPM-GPG-KEY-slaanesh

E instale o Spotify com:

  sudo dnf install spotify-client
  
===== Instale o Dropbox no Fedora =====

O Dropbox é um serviço de armazenamento e compartilhamento de arquivos na nuvem. Se você é usuário do Dropbox e habilitou os repositórios RPM Fusion, instale-o no Fedora com:

  sudo dnf install nautilus-dropbox python-gpgme
  
===== Instalando Google Chrome =====

Importe a chave de assinatura da Google:

  sudo rpm --import https://dl.google.com/linux/linux_signing_key.pub
  
Adicione o repositório do Google Chrome no sistema, para isto, copie e cole todo o conteúdo abaixo no terminal e após, pressione Enter:

  sudo tee /etc/yum.repos.d/google-chrome.repo <<RPMREPO
  [google-chrome]
  name=google-chrome
  baseurl=http://dl.google.com/linux/chrome/rpm/stable/x86_64
  enabled=1
  gpgcheck=1
  gpgkey=https://dl.google.com/linux/linux_signing_key.pub
  RPMREPO
  
Feito isso, instale o Google Chrome (estável) com:

  sudo dnf install google-chrome-stable

===== Instalando o Adobe Flash Player =====

Atualmente, a grande maioria dos sites mais acessados (como, por exemplo, o YouTube) já não "dependem" do Adobe Flash Player instalado, mas, caso necessite utilizá-lo (no Mozilla Firefox), basta adicionar o repositório da Adobe no sistema:

Se instalou o Fedora de 64 bits, execute:

  sudo dnf install http://linuxdownload.adobe.com/adobe-release/adobe-release-x86_64-1.0-1.noarch.rpm

Se instalou o Fedora de 32 bits, execute:

  sudo dnf install http://linuxdownload.adobe.com/adobe-release/adobe-release-i386-1.0-1.noarch.rpm

Importe a chave de assinatura do repositório Adobe:

  sudo rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-adobe-linux

E instale o Adobe Flash Player com:

  sudo dnf install flash-plugin
  
===== Instalando o OpenJDK (o Java de código aberto) =====

Para instalar o OpenJDK no Fedora e também o plugin IcedTea Web (que disponibiliza o plugin Java para navegadores) basta digitar:

  sudo dnf install java-openjdk icedtea-web

===== Instale o Dropbox =====

O Dropbox é um serviço de armazenamento e compartilhamento de arquivos na nuvem. Se você é usuário do Dropbox e habilitou os repositórios RPM Fusion, instale-o no Fedora com:

  sudo dnf install nautilus-dropbox python-gpgme
  
===== Instalando o Editor Atom =====
  
 Instale os plugins 
  sudo dnf install dnf-plugins-core
  
 Habilitando o repositório
  sudo dnf copr enable mosquito/atom
 
Instalando o editor 
  sudo dnf install atom  

----

fonte [[http://www.blogopcaolinux.com.br/2016/11/Guia-de-pos-instalacao-do-Fedora-25-Workstation.html | BlogOpcaoLinux]]

fonte Instalação Atom [[https://andrewwippler.com/2016/03/18/atom-editor-on-fedora/ | Andrew Wippler's Sketchpad]]