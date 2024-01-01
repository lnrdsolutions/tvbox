**Alertas**

1. Estes protocolos foram testados em várias unidades sem nenhuma ocorrência negativa. Leia-os completamente antes de realizar qualquer procedimento para que não haja qualquer dúvida a respeito.
2. Há o risco eventual de travamento e/ou perda da sua TV Box caso haja algum problema mais severo. Use por seu próprio risco. Não me responsabilizo por nenhum dano.

**Roteiros**

<u>Configurando o teclado</u>

1. Para configurar o teclado, digite o comando **sudo armbian-config** (pode ser necessário fornecer a sua senha de usuário comum). Escolha **Personal**, **Keyboard**. Em seguida, escolha as configurações mais adequadas ao equipamentos que será utilizado.

<u>Configurando o LightDM para iniciar automaticamente no usuário comum</u>

1. Vamos supor que o usuário comum definido na instalação seja **tvboxreceita**. A cada reinício da TV Box faz-se necessário fornecer o nome do usuário, **tvboxreceita**, e a sua senha. Contudo, com essa senha torna-se possível realizar alterações no sistema de acordo com as configurações atuais. Qual a solução? Optamos por iniciar automaticamente no usuário padrão sem a necessidade de acesso à senha para os discentes das escolas atendidas.
2. No prompt do Terminal, execute **sudo nano /etc/lightdm/lightdm.conf** (pode ser necessário fornecer a sua senha de usuário comum).
3. Busque as linhas a seguir e altere-as de forma a ficar conforme descrito abaixo:
   - [SeatDefaults]
   - autologin-user=**tvboxreceita**
   - autologin-user-timeout=0
4. Salve o arquivo pressionando simultaneamente Ctrl+O.
5. Execute **sudo reboot** (pode ser necessário fornecer a sua senha de usuário comum).

<u>Desativando a interface Wi-Fi</u>

1. Em função de restrições impostas pela ANATEL, faz-se necessária a desativação da interface Wi-Fi antes da disponibilização para as escolas públicas.
2. No prompt do Terminal, execute **cd /etc/NetworkManager/conf.d/**. Em seguida, execute **sudo nano 99-unmanaged-devices.conf** (pode ser necessário fornecer a sua senha de usuário comum).
3. Insira o conteúdo a seguir:
   - [keyfile]
   - unmanaged-devices=interface-name:wlan0
4. Salve o arquivo pressionando simultaneamente Ctrl+O.
5. Execute **sudo systemctl reload NetworkManager.service** (pode ser necessário fornecer a sua senha de usuário comum).
6. Execute **sudo reboot** (pode ser necessário fornecer a sua senha de usuário comum).
7. Após reiniciar, a interface Wi-Fi não deve estar mais disponível ao usuário.