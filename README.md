![banner](https://github.com/lnrddev/tvbox/blob/main/images/banner_lnrd_tvbox.png?raw=true)

# Seja bem-vindo(a)!!! 👋

Desde junho de 2022 desenvolvemos projeto de extensão com a Receita Federal do Brasil (RFB), em sua Regional do Sul de Minas, para a descaracterização de aparelhos de TV Box ilegais na busca de produtos mais úteis para a sociedade evitando a sua disposição como lixo eletrônico com impactos significativos ao Meio Ambiente. As atividades contam com o apoio do Prof. Osvaldo Adilson Carvalho Júnior, do Prof. Marlus Pinheiro Rolemberg e do discente José Lúcio Zancan Júnior. Todos envolvidos estão ligados à Universidade Federal de Alfenas, no Campus Poços de Caldas (MG).

O projeto está inserido no Programa Além do Horizonte, da Receita Federal, que participa da destinação sustentável de produtos apreendidos pela Instituição. Neste programa, há diferentes ações da RFB para reaproveitamentos de itens como TV Box, vestuários e cigarros que, após a devida descaracterização, são destinados de forma ambientalmente mais sustentável diferindo do produto original fruto de cada apreensão. Especificamente neste projeto, participamos de uma rede com diferentes Instituições de Ensino voltadas ao emprego de TV Box como computadores em escolas públicas, embora haja potencial para diferentes aplicações. O fluxograma utilizado é apresentado na Figura 1.

![fluxograma](https://github.com/lnrddev/tvbox/blob/main/images/fluxograma_apreensao_RF.jpeg?raw=true)

Figura 1. Fluxograma do projeto para descaracterização de TV Box para escolas públicas.

A abordagem inicial que utilizamos é a determinação das capacidades dos equipamentos apreendidos, para posterior avaliação em diferentes aplicações, como educação, ensino de programação, uso como desktop e sinalização digital. Outras aplicações estão sendo avaliadas e estarão disponíveis assim que devidamente estabelecidas.

Os processadores utilizados em aparelhos de TV Box empregam a arquitetura ARM na sua concepção, diferindo substancialmente da maioria dos processadores que utilizamos no nosso dia a dia. O sistema Armbian utiliza o Debian como plataforma base mas para a arquitetura ARM. O desafio aqui é determinar uma distribuição adequada para cada configuração de TV Box pois, diferentemente dos equipamentos que utilizamos como notebooks e desktops, não há padronização nas diferentes configurações dos equipamentos que estão em avaliação.

Na medida em que obtivermos sucesso para as diferentes configurações de equipamentos, faremos a devida divulgação dos roteiros de instalação para que a proposta possa ser replicada em maior escala. Já efetuamos, até o presente momento, a entrega de aproximadamente 1500 unidades para Albertina, Andradas, Bandeira do Sul, Botelhos, Caldas, Campestre, Ibitiúra de Minas, Ipuiuna, Poços de Caldas, Santa Rita de Caldas, Alfenas, Alterosa, Areado, Campo do Meio, Campos Gerais, Carmo do Rio Claro, Carvalhópolis, Divisa Nova, Fama, Machado, Paraguaçu, Poço Fundo, Serrania, Frutal e Governador Valadares, todas no estado de Minas Gerais, além de dar o devido apoio às demais Instituições de Ensino envolvidas. Atualmente estamos descaracterizando próximo a mil unidades para o estado de Tocantis, visto o enorme potencial e demanda de equipamentos de TI no território brasileiro, notadamente em Instituições Públicas de ensino. Para qualquer dúvida, estamos à disposição no e-mail leonardo.damasceno at unifal-mg.edu.br. 

## TV Box descaracterizadas

*Processadores Amlogic*

| Modelo         | Processador                  | GPU      | RAM  | Disco | Wifi         | Ethernet | Áudio HDMI |
| :------------- | ---------------------------- | -------- | ---- | ----- | :----------- | :------: | :--------: |
| BTV Express 10 | Amlogic S905X2 (Cortex A-53) | Mali-G31 | 2 Gb | 8 Gb  | 🚫 RTL8189FTV |    ✅     |     ✅      |
| BTV 11         | Amlogic S905X3 (Cortex A-55) | Mali-G31 | 1 Gb | 16 Gb | ✅ AP6212     |    ✅     |     ✅      |
| HTV 6+         | Amlogic S905X (Cortex A-53)  | Mali-450 | 2 Gb | 16 Gb | ✅ RTL8723BS  |    ✅     |     ✅      |
| HTV 7          | Amlogic S905X3 (Cortex A-53) | Mali-G31 | 2 Gb | 16 Gb | ✅ RTL8822CS  |    ✅     |     ✅      |

Para saber mais a respeito dos protocolos de instalação, [clique aqui](https://github.com/lnrddev/tvbox/blob/main/documentacao/guiainstalacao_amlogic.md).

## A plataforma EcoBoxHub

A partir da descaracterização da TV Box, torna-se possível a aplicação do equipamento em diferentes finalidades, a saber: estação de trabalho ([workstation](https://github.com/lnrddev/tvbox/blob/main/documentacao/workstation.md)), sinalização digital, plataforma de ensino de programação, automação e robótica, dentre outras.

Para tanto, nossa equipe propõe cada equipamento como uma plataforma de desenvolvimento denominada EcoBoxHub, na qual diferentes aplicações são desenvolvidas para diversas finalidades. 

## O projeto na mídia

- [TV Box transformadas em minicomputadores pela UNIFAL-MG são doadas para instituições da região](https://www.unifal-mg.edu.br/portal/2023/05/18/tv-box-transformadas-em-minicomputadores-pela-unifal-mg-sao-doadas-para-instituicoes-da-regiao/).
- [Receita Federal e Unifal-MG destinam TV Box transformadas em Minicomputadores às prefeituras da região](https://www.gov.br/receitafederal/pt-br/assuntos/noticias/2023/maio/receita-federal-e-unifal-mg-destinam-tv-box-transformadas-em-minicomputadores-para-prefeituras-da-regiao).
- [Receita Federal e Unifal entregam minicomputadores reciclados para Poços](https://www.pocosja.com.br/2023/05/12/receita-federal-e-unifal-entregam-minicomputadores-reciclados-para-pocos/).
- [Receita Federal e Unifal destinam TV Box transformadas em Minicomputadores às prefeituras da região de Alfenas](https://www.gov.br/receitafederal/pt-br/assuntos/noticias/2023/setembro/receita-federal-e-unifal-destinam-tv-box-transformadas-em-minicomputadores-as-prefeituras-da-regiao-de-alfenas?fbclid=PAAaZtLbnv7aYcoEdHW3U64WpjAsq-OMBLXiz0oeHApGj6FEhLKvKTDPG6R18).
- [Reportagem da TV Plan - TV Box são transformadas em minicomputadores e destinadas à Prefeituras](https://www.youtube.com/watch?v=5mZmC_hQGf4).
- [Reportagem do Jornal das Geraes - Municípios recebem minicomputadores doados pela Receita Federal](https://www.youtube.com/watch?v=JIyAsC1v9Sc).

## Perguntas frequentes

Para saber mais sobre o projeto, [clique aqui](https://github.com/lnrddev/tvbox/blob/main/documentacao/faq.md).

Esta página estará em constante atualização, portanto, recomendo retornar sempre que possível para busca de novidades sobre o projeto.

**<p align="right">Prof. Leonardo Henrique Soares Damasceno</p>**

[![Visitors](https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fgithub.com%2Flnrddev%2Ftvbox&label=Visitantes&countColor=%23d9e3f0)](https://visitorbadge.io/status?path=https%3A%2F%2Fgithub.com%2Flnrddev%2Ftvbox)
[![name](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](http://wa.me/553597686099)
[![image](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)](https://www.r-project.org)

