---
title: "Funções no R"
date: "2018-04-05"
---

Neste tutorial vamos treinar a construção de funções no R. Cada um dos 7 tópico abaixo contém um desafio de criação de uma função.

Exercícios de função de programação costumam ser bastante "bobos", ou seja, são bons exercícios didáticos, mas não servem para a prática de programação. A necessidade de criar funções aparece somente quando temos um problema prático. É difícil pensar em funções que sirvam para casos gerais, pois estas são justamente as funçõe que provavelmente alguém já implementou. 

Os desafios abaixo são para criação de funções úteis, a maioria delas funções que eu mesmo tive de criar no passado para resolver algum problema.

Vou disponibilizar um gabarito ao final da aula, mas quero mesmo que vocês quebrem a cabeça tentando construir as funções. Algumas terão poucas linhas (as vezes até uma única) de código, mas serão complexas. Outras serão simples, mesmo que você tenha que escrever muito.

## Normalização de variáveis

Contrua uma função para "normalizar" uma variável contínua (ou vetor numérico), ou seja, uma função que subtraia de cada valor $x_i$ da variável $X$ a média $\bar{x}$ e divida pelo desvio padrão $s_x$.

Teste seu dados com as variáveis "income" e "savings" do data frame "fake\_data", utilizado no curso.

## Remoção de acentos agudos, circunflexos, tils e crases

Construa uma variável que remova de um vetor de texto (ou variável) todos os acentos agudos, circunflexos, tils e crases, sem, no entanto, remover outros caracteres especiais (como cecedilha). Dica: use _str\_replace\_all_ ou _gsub_.

Teste seu dados com os discursos da deputada Luiza Erundina, utilizados na aula anterior.

## Remoção de todos os caracteres especiais

A função _iconv_ converte o encoding de um texto. "ASCII//TRANSLIT" é um encoding sem caracteres especiais. Veja seu uso:

```{r}
texto_com_cecedilha_e_acento <- "remoção de caracteres especiais"
iconv(texto_com_cecedilha_e_acento, to = "ASCII//TRANSLIT")
```

Crie uma função que remove todos os caracteres especiais de um vetor de texto usando a função iconv e o encoding "ASCII//TRANSLIT". Teste seu dados com os discursos da deputada Luiza Erundina, utilizados na aula anterior.

## Download + unzip

Crie uma função que recebe como argumento um endereço url, faz o download do arquivo .zip contido no endereço e descompacta o arquivo. Teste com dados do repositório do TSE.

## Combinando arquivos

Crie uma função que recebe como argumento uma pasta de seu computador que contenha diversos arquivos e combina todos os arquivos com a extensão .txt (e não inclui os demais). Teste com dados do repositório do TSE.

Dica: você precisará usar loop ou funções que fazem iterações (a exemplo das funções da família "lapply" ou das funções "map" do pacote _purrr_).

## Capturando beta de uma regressão

Para produzir uma regressão linear entre x e y fazemos:

```{r}
reg <- lm(x ~ y, data = my_data)
```

Com o comando abaixo, observamos os coeficientes do modelo estimado:

```{r}
summary(reg)$coefficients
```

Se quisermos apenas o coeficiente de x, por exemplo, fazemos:

```{r}
summary(reg)$coefficients[2,1]
```

Crie uma função que calcula uma regressão linear entre duas variáveis, x e y, retorna um vetor com dois valores, que contém o valor do coeficiente de x e seu respectivo erro padrão, nesta ordem.

Teste seu dados com as variáveis "income" e "savings" do data frame "fake\_data", utilizado no curso.

## Exportando gráficos

Crie uma função que recebe como argumento duas variáveis contínuas, x e y, um título ("titulo"), um rótulo para a variável x ("rotulo_x"), um rótulo para a variável y (rotulo_y) e um nome de arquivo ("arquivo") e exporta para uma pasta local com nome "arquivo" um um gráfico de dispersão com uma reta de regressão de y por x, com título e rótulos dos eixos.

Teste seu dados com as variáveis "income" e "savings" do data frame "fake\_data", utilizado no curso.
