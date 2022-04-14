# Metapackage e scripts para LXDE no Debian

## Introdução

O LXDE é a interface gráfica mais leve existente (existem outras interfaces mais leve que ela, mas elas estão em outras "categorias"), por este motivo é muito usado em computadores com processamento e memórias mais limitados, sejam por serem antigos ou por serem de baixa potência e consumo energético. Mas nada impede pessoas com computadores de alto poder computacional usarem o LXDE buscando eficiência e minimalismo. O problema é que a equipe de desenvolvimento do LXDE não é grande o suficiente para criar um ambiente completo, nem solucionar todos os bugs de seus programas.

Exemplos práticos:
1. Conectividade: A equipe do LXDE estava desenvolvendo um gerenciador de redes chamado LXNM, mas abandonou o projeto. Hoje o projeto usa como substituto o NetworkManager (gnome) ou o Connection Manager (connman). O metapackege instala o network-manager-gnome.
2. Energia: Não foi desenvolvido um software para fazer o gerenciamento de energia. O metapackege instala o xfce4-power-manager.
3. Mouse: Atualmente a versão do lxinput disponível no debian não funciona recursos como alterar a aceleração do mouse, por exemplo. Este reposítorio recomenda que você instale a versão melhorada pela equipe do Raspberry Pi.

O objetivo deste repositório é permitir que pessoas que queiram obter os beneficios do LXDE o consigam, sem os maleficios do mesmo.

Este metapackage foi testado no Debian Sid, mas provavelmente funcionará nas versões anteriores e em sistemas operacionais baseados no debian como Ubuntu e derivados.

## Metapackage

### Dependências

- lxde
- xfce4-power-manager
- network-manager-gnome
- deepin-icon-theme
- gedit

### Recomendados

- grub-customizer
- gparted
- gimp
- inkscape
- qbittorrent
- obs-studio
- tor-browser
- vlc
- unrar

### Arquivos

- /usr/share/themes/deepin/...
  - https://www.gnome-look.org/p/1177633
- /usr/share/themes/deepin-dark/...
  - https://www.gnome-look.org/p/1190867/
- /usr/share/lxde/images/linux.png
  - https://www.flaticon.com/br/icone-gratis/linux_518713
- /usr/share/lxde/wallpapers/pink-floyd.jpg
  - https://wallpaperaccess.com/download/pink-floyd-4k-3956179

## Scripts

### Instalar metapackage

    sudo apt install ./debianlxde.deb

### Ou Instalar metapackage com os recomendados

    sudo apt install ./debianlxde.deb --install-suggests

### Instalar Spotify

    curl -sS https://download.spotify.com/debian/pubkey_5E3C45D7B312C643.gpg | sudo apt-key add - 
    echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
    sudo apt update && sudo apt install spotify-client


## Operações manuais

### Baixar e Instalar

- Visual Studio Code: https://code.visualstudio.com/download
- WPS Office: https://linux.wps.com/
- VNC Viewer: https://www.realvnc.com/en/connect/download/viewer/linux/
- 4K Video Downloader: https://www.4kdownload.com/products/videodownloader
- Discord: https://discord.com/api/download?platform=linux&format=deb

#### LxInput

Baixar a versão mais recente do lxinput no repositório do Raspberry Pi e a dependência lxinput-dbg na mesma versão e arquitetura adequada ao seu sistema operacional: https://archive.raspberrypi.org/debian/pool/main/l/lxinput/

OBS: Muito provavelmente você estará utilizando um sistema operacional amd64.

Intalar com o comando:

    sudo apt install ./lxinput_* ./lxinput-dbg_*

## Resultado

Depois dos pacotes instalados, o sistema pode ser personalizado ao seu gosto. Eu gosto dele assim:

![Resultado LXDE](https://raw.githubusercontent.com/campagnani/DebianLxde/main/debian1.png)
