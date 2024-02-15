# Informações complementares

## Alteração das senhas do root e do usuário comum

1. Para alterar a senha do usuário **tvboxreceita**, execute o comando abaixo.

`sudo passwd tvboxreceita`

2. Se você quer alterar a senha do **root**, execute o comando abaixo.

`sudo passwd`

Em ambos os casos você deverá inserir a senha duas vezes.

## Alterando o papel de parede na inicialização

1. Supondo que o arquivo com seu papel de parede esteja em /usr/share/wallpapers/wallpaper.png, execute o comando abaixo na Inicialização do sistema.

`dconf write /org/mate/desktop/background/picture-filename "'/usr/share/wallpapers/wallpaper.png'"`

## Configurando o LightDM para iniciar automaticamente no usuário comum

1. Vamos supor que o usuário comum definido na instalação seja **tvboxreceita**. A cada reinício da TV Box faz-se necessário fornecer o nome do usuário, **tvboxreceita**, e a sua senha. Contudo, com essa senha torna-se possível realizar alterações no sistema de acordo com as configurações atuais. Qual a solução? Optamos por iniciar automaticamente no usuário padrão sem a necessidade de acesso à senha para os discentes das escolas atendidas.
2. No prompt do Terminal, execute `sudo nano /etc/lightdm/lightdm.conf`.
3. Busque as linhas a seguir e altere-as de forma a ficar conforme descrito abaixo:
   - [SeatDefaults]
   - autologin-user=**tvboxreceita**
   - autologin-user-timeout=0
4. Salve o arquivo pressionando simultaneamente Ctrl+O.
5. Execute **sudo reboot** (pode ser necessário fornecer a sua senha de usuário comum).

## Configurando o teclado

1. Para configurar o teclado, digite o comando **sudo armbian-config** (pode ser necessário fornecer a sua senha de usuário comum). Escolha **Personal**, **Keyboard**. Em seguida, escolha as configurações mais adequadas ao equipamentos que será utilizado.

## Desativando a interface Wi-Fi

1. Em função de restrições impostas pela ANATEL, faz-se necessária a desativação da interface Wi-Fi antes da disponibilização para as escolas públicas.
2. No prompt do Terminal, execute **cd /etc/NetworkManager/conf.d/**. Em seguida, execute **sudo nano 99-unmanaged-devices.conf** (pode ser necessário fornecer a sua senha de usuário comum).
3. Insira o conteúdo a seguir:
   - [keyfile]
   - unmanaged-devices=interface-name:wlan0
4. Salve o arquivo pressionando simultaneamente Ctrl+O.
5. Execute **sudo systemctl reload NetworkManager.service** (pode ser necessário fornecer a sua senha de usuário comum).
6. Execute **sudo reboot** (pode ser necessário fornecer a sua senha de usuário comum).
7. Após reiniciar, a interface Wi-Fi não deve estar mais disponível ao usuário.

## Gerar imagem do pendrive/cartão excluindo espaços em branco.

### Cenário

1. Pendrive/cartão com aproximadamente 58 Gb de espaço total, contendo duas partições cuja soma se aproxima de 6,3 Gb com  51,7 Gb de espaço não alocado.
2. Em condição normais a cópia do pendrive/cartão seria realizada considerando o tamanho total do disco (58 Gb), e não somente a soma das duas partições (6,3 Gb).

### Procedimento

1. Executar `fdisk -l` no Terminal. A saída do comando será semelhante ao apresentado abaixo.

```
Disk /dev/mmcblk0: 57.9 GiB, 62115545088 bytes, 121319424 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0xd65780db

Device         Boot  Start      End  Sectors  Size Id Type
/dev/mmcblk0p1        8192   532479   524288  256M  c W95 FAT32 (LBA)
/dev/mmcblk0p2      532480 13332479 12800000  6.1G 83 Linux
```

2. Supondo que o cartão/pendrive a ser clonado esteja em **mmcblk0**, o setor final da partição é o **13332479**.
3. Adicione um setor a este valor, ou seja, 13332479+1 = **13332480**.
4. Multiplique pelo número de bytes por setor (512 bytes/setor), 13332480x512 = **6826229760**. Este valor representa o número de bytes a serem copiados. 
5. Insira o valor na opção `count=` no comando. Assim, supondo que o nome do arquivo de imagem que deseja criar seja `imagem.iso`, execute o comando abaixo.

```dd if=/dev/mmcblk0 of="imagem.iso" count=6826229760 status=progress iflag=count_bytes```

**Observação**

Se a partição **/dev/mmcblk0p2** de 6,1 Gb possuísse 2 Gb de espaço não utilizado, por exemplo, você poderia reduzir o seu tamanho utilizando o aplicativo [Gparted](https://gparted.org/), otimizando ainda mais o tamanho final do arquivo ISO.

## Limpando o histórico do Terminal

1. Para limpar o histórico do Terminal, abra-o e execute o comando abaixo.

`echo "" > ~/.bash_history`

2. Feche o Terminal e abra novamente. O histórico estará limpo.
