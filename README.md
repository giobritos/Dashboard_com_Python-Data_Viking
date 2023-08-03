# Dashboard com Python - Data Viking

Este repositório contém arquivos relacionados ao curso "Dashboard com Python" ministrado pelo professor Odemir Depieri Jr, da Data Viking.

## Visão Geral

O objetivo deste projeto é criar um dashboard interativo utilizando a biblioteca Dash em Python para visualizar e analisar dados relacionados a multas de trânsito. O processo de criação do dashboard é dividido em três etapas principais: a Criação do Banco de Dados e Exportação dos Dados para SQLite e Arquivo Parquet, a Análise de Dados usando as bibliotecas Pandas e Plotly, e finalmente a criação do próprio Dashboard.

## 1. Criação do Banco de Dados e Exportação dos Dados

O primeiro script contém o código para extrair arquivos de um arquivo ZIP contendo os dados de infrações de trânsito em diferentes meses durante o ano de 2022. Os arquivos são armazenados em um diretório específico e são consolidados em um único DataFrame.

### Passos do Script:

1. Importar pacotes necessários, incluindo pandas, numpy, pathlib, zipfile e sqlite3.

2. Extrair arquivos de um arquivo ZIP para uma pasta de destino usando a função `extract_zip_files`.

3. Listar os arquivos contidos na pasta de destino.

4. Definir uma função para converter o tamanho de arquivos de bytes para megabytes.

5. Calcular o tamanho total dos arquivos em megabytes.

6. Ler os arquivos CSV e consolidá-los em um único DataFrame chamado `Base_Consolidada`.

7. Exibir uma amostra das primeiras linhas do DataFrame `Base_Consolidada`.

8. Exportar o DataFrame `Base_Consolidada` para um arquivo CSV chamado 'Base_Consolidada.csv'.

9. Criar um banco de dados SQLite chamado 'Banco_Dados.db' e inserir o DataFrame `Base_Consolidada` na tabela 'Base_Consolidada'.

10. Converter o DataFrame `Base_Consolidada` em um arquivo Parquet com compressão GZIP chamado 'Base_Consolidada.parquet'.

## 2. Análise de Dados usando Pandas e Plotly

O segundo script apresenta uma análise de dados usando a biblioteca Pandas e Plotly para visualização de dados. A seguir, vou detalhar cada etapa do código:

1. Instalação das bibliotecas: As bibliotecas Plotly e lxml estão sendo instaladas usando o comando pip.

2. Importação de bibliotecas: São importadas as bibliotecas necessárias para análise de dados e visualização.

3. Carregar a base de dados: É carregado um arquivo chamado 'Base_Consolidada.parquet', que contém a base de dados a ser analisada.

4. Análise exploratória dos dados:

   - Tipo, colunas e informações da base de dados são mostrados.

   - O total de multas nos últimos 12 meses é calculado.

   - A coluna 'Data da Infração' é convertida para o tipo datetime.

   - As multas por dia são calculadas, e uma média móvel é aplicada para suavizar a série temporal.

   - Gráficos de linha e sistema de grid são criados para visualizar a quantidade de multas diárias e a média móvel.

5. Análise de multas por estado:

   - É criada uma tabela de frequência para analisar a quantidade de multas por estado.

   - Gráficos de funil e de barra são criados para mostrar a concentração das multas nos estados.

6. Análise do valor das multas:

   - Dados adicionais sobre o valor das multas são obtidos em um website externo e incorporados à análise.

   - O preço médio das multas é calculado para cada código da infração.

## 3. Criação do Dashboard utilizando Dash

A terceira etapa consiste na criação do Dashboard interativo utilizando a biblioteca Dash em Python.

### Conteúdo do Dashboard:

O dashboard é composto por duas seções principais:

#### 3.1. Coluna Esquerda

- **Total Multas:** Nesta seção, é exibido o total de multas registradas, calculado a partir da base de dados "Dados_Diários.csv". O valor é exibido em milhões e formatado com uma cor de destaque verde (#b4bd53).

- **Total Valores:** Nesta seção, é exibido o total de valores das multas aplicadas, calculado a partir da base de dados "Dados_Mes_Valor.csv". O valor é exibido em milhões de reais e formatado com uma cor de destaque verde (#3a8c5d).

#### 3.2. Coluna Direita

- **Gráfico 1 - Multas Diárias:** Nesta seção, é exibido um gráfico de linhas que representa a quantidade de multas registradas diariamente ao longo do tempo. Os dados para este gráfico são obtidos da base de dados "Dados_Diários.csv". O gráfico possui a aparência do tema Darkly do Bootstrap e é configurado para mostrar a quantidade no eixo Y e o período no eixo X.

- **Gráfico 2 - Valores Mensais Aplicados:** Nesta seção, é exibido um gráfico de barras que representa o valor das multas aplicadas em cada mês. Os dados para este gráfico são obtidos da base de dados "Dados_Mes_Valor.csv". O gráfico possui a aparência do tema Darkly do Bootstrap e é configurado para mostrar o valor em reais no eixo Y e os meses no eixo X.

## Como Executar o Dashboard

Para executar o dashboard, é necessário instalar as bibliotecas Dash, Dash Core Components, Dash HTML Components e Dash Bootstrap Components. O código do dashboard pode ser copiado e executado em um ambiente Python, como o Jupyter Notebook ou um arquivo Python .py.

## Autor

Este projeto foi desenvolvido pela Giovana de Brito Silva com base no curso Dashboard com Python do professor Odemir Depieri Jr da Data Viking.
