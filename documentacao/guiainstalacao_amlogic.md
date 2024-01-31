# Guia de Instalação - Processadores Amlogic (em construção)

## ⚠️ Informações iniciais

Na Tabela 1 são apresentadas as informações técnicas para a instalação de cada modelo de TV Box descaracterizada, além das imagens originais do Armbian e as imagens desenvolvidas para a plataforma EcoBoxHub.

Tabela 1. Dados necessários à execução do protocolo de instalação

| Modelo         | Arquivo DTB                          | Imagem Armbian                                               | Imagem EcoBoxHub |
| :------------- | ------------------------------------ | ------------------------------------------------------------ | ---------------- |
| BTV Express 10 | meson-g12a-sei510.dtb (opção 303)    | Em construção.                                               | Em construção.   |
| BTV 11         | meson-sm1-x96-air.dtb (opção 510)    | [Armbian 24.2.0 - Debian Bookworm - Kernel 6.1.74 - Versão Server - 2024.01.25](https://drive.google.com/file/d/1gY52OXq8zVdpLazQ7xd9gcl4zHdtOirl/view?usp=sharing) | Em construção.   |
| HTV 6+         | meson-gxl-s905x-p212.dtb (opção 106) | Em construção.                                               | Em construção.   |
| HTV 7          | meson-sm1-x96-air.dtb (opção 510)    | [Armbian 24.2.0 - Debian Bookworm - Kernel 6.1.74 - Versão Server - 2024.01.25](https://drive.google.com/file/d/1gY52OXq8zVdpLazQ7xd9gcl4zHdtOirl/view?usp=sharing) | Em construção.   |

*Observações:*

1. A imagem Armbian corresponde ao Debian Bookworm.
2. A imagem EcoBoxHub corresponde à versão Workstation.
3. As imagens foram obtidas em https://github.com/ophub/amlogic-s9xxx-armbian/releases.

## Requisitos

1. Pendrive (8 Gb ou superior).
2. Hub USB (caso vá trabalhar com o ambiente gráfico).
3. Imagem ISO (Armbian ou EcoBoxHub). Selecione uma das duas disponíveis para seu modelo na Tabela 1.
4. Aplicativo de gravação de imagens no pendrive. Recomenda-se o Balena Etcher. [Clique aqui](https://www.balena.io/etcher/) para baixar e instalar na sua máquina.

## Instalação para a Imagem original do Armbian

1. Execute o Balena Etcher e transfira a imagem para o seu pendrive. 
2. Após a transferência da imagem, remova-o com segurança, de acordo com os procedimentos compatíveis com seu sistema operacional.
3. Reinsira o pendrive e abra a partição BOOT do pendrive.
4. Abra o arquivo `uEnv.txt` e procure a linha que se inicia com `FTD=`. Você deve inserir o caminho do arquivo DTB de acordo com o que é apresentado na Tabela 1. Os arquivos DTB estão localizados na pasta `/dtb/amlogic/`. Como exemplo, para a *BTV Express 10*, `FDT=/dtb/amlogic/meson-g12a-sei510.dtb`. Salve o arquivo.
5. Remova o pendrive com segurança conforme os procedimentos compatíveis com o seu sistema operacional.
6. Insira o pendrive na TV Box. Ligue os cabos HDMI, ethernet e teclado. Ao inserir a fonte de energia, faz-se necessário pressionar concomitantemente o botão RESET ou UPDATE com um clip por três segundos (conte de um a cinco). O procedimento é realizado apenas uma vez para ativar o multi-boot do equipamento. O sistema deverá iniciar pelo Armbian. Se entrar no sistema original da TV Box, refaça o procedimento.
7. Ao entrar no Armbian pela primeira vez será necessário fornecer:
   - Senha do root.
   - Shell a ser utilizado. Recomenda-se o bash.
   - Nome e senha do usuário comum.
   - Fuso horário a ser utilizado.
8. Ao término, o prompt estará disponível, no usuário root, sendo disponível para configuração e/ou transferência para a TV Box. Se você vai fazer a transferência do sistema para vários equipamentos, sugiro que faça todas as configurações necessárias utilizando o pendrive e somente em seguida execute o procedimento de transferência para a TV Box.
9. Faça a atualização da lista de pacotes com o comando `sudo apt update`.
10. Atualize os pacotes necessários com o comando `sudo apt upgrade`.
11. Reinicie o equipamento com o comando `sudo reboot`.
12. Após o reinício, o equipamento aguardará no prompt do login do shell. Você pode logar com o nome e senha de usuário comum que definiu no passo 7.
13. Lembre-se: a imagem utilizada nesse protocolo diz respeito à uma imagem *server*. Toda o ajuste de ferramentas adicionais deverá ser feito posteriormente, incluindo a parte gráfica. Essa escolha se deu pelas características dos equipamentos de TV Box, permitindo que você possa otimizar da forma que preferir. Qualquer dúvida, entre em contato por gentileza. Como sugestão, você pode seguir os procedimentos apresentados para a [configuração como estação de trabalho (workstation)](https://github.com/lnrddev/tvbox/blob/main/documentacao/workstation.md).

## Instalação para a Imagem EcoHubBox

Em construção.

## Transferindo a imagem do pendrive para a TV Box

Observação: este procedimento irá apagar todo o conteúdo do equipamento. Por serem sistemas ilegais, não apresentaremos aqui qualquer procedimento para realização de cópias dos sistemas originais.

1. No terminal, execute `sudo armbian-install`.
2. Forneça o código correspondente ao arquivo DTB necessário para seu equipamento. As opções são apresentadas na Tabela 1, junto com o nome dos arquivos DTB. Como exemplo, para a *BTV Express 10*, o arquivo *meson-g12a-sei510.dtb* corresponde à opção 303.
3. Escolha o formato de arquivos a ser utilizado. Sugerimos o formato `ext4` por sua maior estabilidade.
4. Aguarde a instalação.
5. Após a instalação, execute o comando `sudo shutdown -h now`. Aguarde o equipamento desligar.
6. Remova o pendrive, retire a fonte de energia e reinsira.
7. Aguarde o Armbian iniciar, agora diretamente da sua TV Box.
