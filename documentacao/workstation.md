# **Alertas**

1. Estes protocolos foram testados em várias unidades sem nenhuma ocorrência negativa. Leia-os completamente antes de realizar qualquer procedimento para que não haja qualquer dúvida a respeito.
2. Há o risco eventual de travamento e/ou perda da sua TV Box caso haja algum problema mais severo. Use por seu próprio risco. Não me responsabilizo por nenhum dano.
3. Se o Armbian estiver instalado no seu pendrive ou cartão de memória, faz-se necessário aumentar o tamanho da partição de instalação para que seja possível baixar e instalar todos os aplicativos. Sugere-se o uso do Gparted em ambiente Linux para maior facilidade. Uma partição de 4 Gb normalmente é suficiente para a instalação.  Se estiver trabalhando diretamente na sua TV Box após a instalação, isto não se faz necessário.

# **Roteiro - Instalação como estação de trabalho (workstation)**

## Ambiente gráfico Mate

`sudo apt install task-mate-desktop lightdm-gtk-greeter`

*Observação: o pacote lightdm-gtk-greeter é necessário para que o sistema inicie corretamente após o reinício.*

## Navegador Chromium

`sudo snap install chromium chromium-l10n`

## LibreOffice e pacotes adicionais para maior usabilidade

`sudo apt install gvfs policykit-1 libreoffice-writer libreoffice-calc libreoffice-impress libreoffice-l10n-pt-br libreoffice-help-pt-br ttf-mscorefonts-installer network-manager-gnome caja pluma eom atril engrampa mate-utils mate-calc mate-screensaver`

