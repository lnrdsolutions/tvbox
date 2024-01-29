# **Alertas**

1. Estes protocolos foram testados em várias unidades sem nenhuma ocorrência negativa. Leia-os completamente antes de realizar qualquer procedimento para que não haja qualquer dúvida a respeito.
2. Há o risco eventual de travamento e/ou perda da sua TV Box caso haja algum problema mais severo. Use por seu próprio risco. Não me responsabilizo por nenhum dano.
3. Se o Armbian estiver instalado no seu pendrive ou cartão de memória, faz-se necessário aumentar o tamanho da partição de instalação para que seja possível baixar e instalar todos os aplicativos. Sugere-se o uso do Gparted em ambiente Linux para maior facilidade. Uma partição de 4 Gb normalmente é suficiente para a instalação.  Se estiver trabalhando diretamente na sua TV Box após a instalação, isto não se faz necessário.

# **Roteiro - Instalação como estação de trabalho (workstation)**

## Ambiente gráfico Mate

`sudo apt install task-mate-desktop lightdm-gtk-greeter`

*Observação: o pacote lightdm-gtk-greeter é necessário para que o sistema inicie corretamente após o reinício.*

## Navegador Chromium

`sudo apt install chromium chromium-l10n`

## LibreOffice e pacotes adicionais para maior usabilidade

`sudo apt install gvfs policykit-1 libreoffice-writer libreoffice-calc libreoffice-impress libreoffice-l10n-pt-br libreoffice-help-pt-br ttf-mscorefonts-installer network-manager-gnome caja pluma eom atril engrampa mate-utils mate-calc mate-screensaver mate-media mate-tweak dconf-editor`

## Drivers gráficos e acessórios

`sudo apt install gstreamer1.0-plugins-base-apps gstreamer1.0-plugins-bad gstreamer1.0-plugins-good libavcodec-extra libavcodec-extra59 gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly mpv vlc`

## Arquivo xorg.conf

Para ativar o driver Mesa/Lima, alterar o arquivo /etc/X11/xorg.conf inserindo as informações a seguir.

```
Section "ServerFlags"
        Option  "AutoAddGPU" "off"
        Option "Debug" "dmabuf_capable"
 EndSection

 Section "OutputClass"
        Identifier "Lima"
        MatchDriver "<display DRM driver>"
        Driver "modesetting"
        Option "PrimaryGPU" "true"
 EndSection
```

Você deve substituir ```"<display DRM driver>"``` com seu respectivo driver, a depender de seu SoC:

* Allwinner: sun4i-drm
* Amlogic: meson
* Ericsson MCDE: mcde
* Exynos: exynos
* Rockchip: rockchip
* Tinydrm: tinydrm

Fonte: https://en.opensuse.org/ARM_Mali_GPU

## Alterando o papel de parede na inicialização

Supondo que o arquivo com seu papel de parede esteja em /usr/share/wallpapers/wallpaper.png, execute o comando abaixo na Inicialização do sistema.

`dconf write /org/mate/desktop/background/picture-filename "'/usr/share/wallpapers/wallpaper.png'"`

## Limpando o histórico do Terminal

Para limpar o histórico do Terminal, execute o comando abaixo.

`echo "" > ~/.bash_history`
