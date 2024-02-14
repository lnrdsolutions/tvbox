# Gerar imagem do pendrive/cartão excluindo espaços em branco.



## Cenário

Pendrive/cartão com aproximadamente 58 Gb de espaço total, contendo duas partições cuja soma se aproxima de 6,3 Gb com  51,7 Gb de espaço não alocado.

Em condição normais a cópia do pendrive/cartão seria realizada considerando o tamanho total do disco (58 Gb), e não somente a soma das duas partições (6,3 Gb).



## Procedimento



Executar `fdisk -l` no Terminal. A saída do comando será semelhante ao apresentado abaixo.



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



Supondo que o cartão/pendrive a ser clonado esteja em **mmcblk0**, o setor final da partição é o **13332479**.

Adicione um setor a este valor, ou seja, 13332479+1 = **13332480**.

Multiplique pelo número de bytes por setor (512 bytes/setor), 13332480x512 = **6826229760**. Este valor representa o número de bytes a serem copiados. 

Insira o valor na opção `count=` no comando. Assim, supondo que o nome do arquivo de imagem que deseja criar seja `imagem.iso`, execute o comando abaixo.

```dd if=/dev/mmcblk0 of="imagem.iso" count=6826229760 status=progress iflag=count_bytes```



**Observação**

Se a partição **/dev/mmcblk0p2** de 6,1 Gb possuísse 2 Gb de espaço não utilizado, por exemplo, você poderia reduzir o seu tamanho utilizando o aplicativo [Gparted](https://gparted.org/), otimizando ainda mais o tamanho final do arquivo ISO.
