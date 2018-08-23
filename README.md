# Aula de filogenia

Por Prof. Dr. Tetsu Sakamoto (IMD - UFRN)

## Introdução

Este repositório contém programas e arquivos que serão utilizados durante a aula prática de Filogenia Molecular ministrada durante a disciplina "Fundamentos de Bioinformática" (ICE1024) da UFRN.

## Descrição dos arquivos:

- lep_16SrRNA.fas - Sequências do gene 16SrRNA de espécies de leptospira no formato FASTA;
- lep_ORF22.fas - Sequências do gene ORF22 de espécies de leptospira no formato FASTA;
- muscle - Programa de alinhamento de sequências;
- trimal - Programa que remove regiões mal alinhadas;
- FastTree - Programa de inferência de árvores filogenéticas baseado em método de máxima verossimilhança;
- figtree.jar - Programa de visualização de árvores filogenéticas.

## Roteiro da aula

### Preparando os arquivos
Em um computador com Linux:
1. Baixe o repositório clicando em “Clone or Download” e depois em “Download ZIP”;
2. Abra um terminal e acesse a pasta onde está o arquivo baixado (aula_filogenia_master.zip);
3. Descompacte o arquivo baixado através do seguinte comando:
```
unzip aula_filogenia_master.zip
```
4. Acesse a pasta aula_filogenia_master/
```
cd aula_filogenia_master
```

### Alinhamento das sequências

Utilize o programa *muscle* para realizar o alinhamento das sequências contidas no arquivo lep_16SrRNA.fas pelo seguinte comando:
```
./muscle -in lep_16SrRNA.fas -out lep_16SrRNA_aligned.fas
```

### Remoção de regiões mal alinhadas

Utilize o programa *trimal* para remover as regiões mal alinhadas do arquivo fasta com as sequências alinhadas (lep_16SrRNA_aligned.fas) pelo seguinte comando:
```
./trimal -in lep_16SrRNA_aligned.fas -out lep_16SrRNA_trimmed.fas -automated1
```

### Inferência da árvore filogenética

Utilize o programa *FastTree* para inferir uma árvore filogenética a partir das sequências alinhadas e que tiveram as regiões mal alinhadas removidas (lep_16SrRNA_trimmed.fas) pelo seguinte comando:
```
./FastTree lep_16SrRNA_trimmed.fas > lep_16SrRNA.tree
```

### Visualização da árvore filogenética

Utilize o programa *figtree.jar* para visualizar a árvore filogenética gerada (lep_16SrRNA.tree). Abra o figtree.jar utilizando o seguinte comando:
```
java -jar figtree.jar
```
Dentro do programa, vá em File > Open e selecione o arquivo da árvore (lep_16SrRNA.tree).

## Exercício
1. Realize todo o procedimento para a montagem de uma árvore filogenética para o arquivo lep_ORF22.fas.
2. Compare as duas árvores geradas e verifique se eles deram o mesmo resultado.

