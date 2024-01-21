# **Alertas**

1. Estes protocolos foram testados em várias unidades sem nenhuma ocorrência negativa. Leia-os completamente antes de realizar qualquer procedimento para que não haja qualquer dúvida a respeito.
2. Há o risco eventual de travamento e/ou perda da sua TV Box caso haja algum problema mais severo. Use por seu próprio risco. Não me responsabilizo por nenhum dano.
3. Se o Armbian estiver instalado no seu pendrive ou cartão de memória, faz-se necessário aumentar o tamanho da partição de instalação para que seja possível baixar e instalar todos os aplicativos. Sugere-se o uso do Gparted em ambiente Linux para maior facilidade. Se estiver trabalhando diretamente na sua TV Box após a instalação, isto não se faz necessário.

# **Roteiros**

## Instalação do ambiente gráfico XFCE

`sudo apt install task-xfce-desktop lightdm-gtk-greeter`

*Observação: o pacote lightdm-gtk-greeter é necessário para que o sistema inicie corretamente após o reinício.*

## Instalação do LibreOffice e pacotes adicionais para maior usabilidade

`sudo apt install thunar-volman gvfs policykit-1 xfce4-screenshooter file-roller qpdfview ristretto libreoffice-writer libreoffice-calc libreoffice-impress ttf-mscorefonts-installer catfish thunar-archive-plugin menulibre gnome-terminal`
