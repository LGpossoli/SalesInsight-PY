# SalesInsight PY

Pipeline de analise e visualizacao de dados de vendas desenvolvido em Python para o mini-projeto avaliativo do Modulo 01.

## Sobre o projeto

O SalesInsight PY le um dataset de vendas em CSV, realiza inspecao, limpeza, transformacao, analise agregada, segmentacao de clientes, visualizacoes e uma projecao simples de tendencia de receita.

O objetivo e simular uma situacao real de analise de dados para apoiar uma reuniao de negocio, identificando comportamento das vendas ao longo do tempo, produtos com maior receita, desempenho por categoria e regiao, clientes mais valiosos e uma estimativa simples para os proximos meses.

## O que o sistema analisa

- Receita total e volume de vendas por mes.
- Top 5 produtos por receita.
- Receita total por categoria.
- Receita total e ticket medio por regiao.
- Segmentacao de clientes por nivel de gasto: Bronze, Prata e Ouro.
- Estatisticas gerais da receita com NumPy.
- Projecao simples de tendencia usando media movel dos ultimos meses.
- Exportacao de relatorios em CSV e JSON.
- Geracao de graficos em PNG.

## Estrutura do projeto

```text
salesinsight-py/
|
|-- README.md
|-- salesinsight.ipynb
|-- vendas.csv
|-- outputs/
|   |-- relatorio_resumo.csv
|   |-- relatorio_resumo.json
|   |-- graficos/
|       |-- vendas_por_mes.png
|       |-- top_5_produtos_por_receita.png
|       |-- distribuicao_regioes.png
```

## Como executar

### No Google Colab

1. Abra o Google Colab.
2. Faca upload do notebook `salesinsight.ipynb`.
3. Faca upload do arquivo `vendas.csv`.
4. Execute as celulas em ordem.

### Localmente com VS Code ou Jupyter

1. Instale Python 3.10 ou superior.
2. Instale as dependencias:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

3. Abra o arquivo `salesinsight.ipynb`.
4. Execute todas as celulas do notebook.

### Como script Python

Tambem e possivel exportar o notebook para `salesinsight.py` e executar o pipeline pelo terminal:

```bash
python salesinsight.py
```

## Dependencias utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- re
- json
- os
- datetime

## Conceitos aplicados

O projeto aplica os principais conceitos estudados no modulo:

- Variaveis e tipos de dados.
- Listas, dicionarios e estruturas compostas.
- Operadores aritmeticos, logicos e relacionais.
- Condicionais com `if`, `elif` e `else`.
- Funcoes com parametros e retorno.
- Funcoes lambda.
- Leitura de arquivos CSV com `pd.read_csv()`.
- Escrita de arquivos CSV com `.to_csv()`.
- Escrita de arquivos JSON com `json.dump()`.
- Manipulacao de datas com `datetime` e recursos de data do Pandas.
- Expressoes regulares com o modulo `re`.
- Pandas DataFrames, filtros, selecoes e `groupby`.
- Transformacoes condicionais com `np.select`.
- NumPy arrays, estatisticas, broadcasting e operacoes vetorizadas.
- Visualizacao de dados com Matplotlib e Seaborn.
- Exportacao de graficos com `plt.savefig()`.
- Programacao orientada a objetos com classes, atributos, metodos e `self`.
- Heranca com `AnalisadorComProjecao` herdando de `AnalisadorDeVendas`.
- Uso de `super()` para inicializar a classe filha.

## Pipeline implementado

O notebook executa as seguintes etapas:

1. Importacao das bibliotecas.
2. Leitura do arquivo `vendas.csv`.
3. Inspecao dos dados brutos.
4. Limpeza de dados:
   - remocao de espacos extras em colunas de texto;
   - limpeza de caracteres especiais em clientes com regex;
   - conversao de datas;
   - remocao de datas invalidas;
   - remocao de linhas com valores nulos em colunas criticas;
   - conversao de tipos numericos.
5. Criacao de colunas derivadas:
   - `receita_total`;
   - `mes`;
   - `mes_nome`;
   - `trimestre`;
   - `ano`;
   - `faixa_receita_item`.
6. Calculo de metricas agregadas:
   - receita por mes;
   - top 5 produtos por receita;
   - receita por categoria;
   - receita por regiao.
7. Segmentacao de clientes por gasto total.
8. Calculo de estatisticas com NumPy.
9. Geracao de graficos.
10. Execucao do pipeline em classes.
11. Projecao simples de tendencia.
12. Exportacao dos resultados.

## Arquivos gerados

Ao executar o notebook, os seguintes arquivos sao gerados:

```text
outputs/relatorio_resumo.csv
outputs/relatorio_resumo.json
outputs/graficos/vendas_por_mes.png
outputs/graficos/top_5_produtos_por_receita.png
outputs/graficos/distribuicao_regioes.png
```

## Visualizacoes

O projeto gera tres graficos:

- Grafico de linha da receita total por mes.
- Grafico de barras com os top 5 produtos por receita.
- Boxplot da distribuicao de receita por regiao.

## Como a internet funciona no contexto do projeto

Neste projeto, os dados sao lidos a partir de um arquivo local chamado `vendas.csv`. Em um cenario real, esses dados poderiam vir de um sistema web ou de uma API REST.

Nesse caso, o script Python atuaria como cliente, enviando uma requisicao HTTP para um servidor. O servidor processaria a requisicao e retornaria os dados, geralmente em JSON. Depois disso, o Python poderia transformar esses dados em um DataFrame do Pandas para realizar as mesmas etapas de analise.

Essa comunicacao segue o modelo cliente-servidor: o cliente solicita dados ou servicos, e o servidor responde.

## Organizacao do desenvolvimento

O desenvolvimento foi organizado usando Kanban, com tarefas distribuidas entre as colunas:

- Backlog
- A Fazer
- Em Andamento
- Concluido

As tarefas contemplam leitura do dataset, limpeza, transformacoes, metricas, visualizacoes, classes, heranca, exportacoes, documentacao e demonstracao final.

Link do Kanban: https://github.com/users/LGpossoli/projects/1

## Versionamento

O projeto deve ser versionado em um repositorio publico no GitHub, utilizando commits descritivos e branches simples.

Branches sugeridas:

- `main`
- `develop`
- `feat/pipeline-dados`
- `docs/readme`

Link do repositorio: https://github.com/LGpossoli/SalesInsight-PY

## Video de demonstracao

O video deve demonstrar:

- objetivo do sistema;
- execucao do pipeline do inicio ao fim;
- dependencias necessarias;
- organizacao das tarefas no Kanban;
- branches utilizadas;
- melhorias futuras.

Link do video: inserir aqui o link do Google Drive ou YouTube nao listado.

## Melhorias futuras

- Ler o JSON exportado com `json.load()` para validar a gravacao.
- Criar uma funcao de ordem superior que receba outra funcao como parametro.
- Adicionar testes automatizados para validar as etapas do pipeline.
- Consumir dados de uma API externa em vez de usar apenas arquivo local.

## Autores

Projeto desenvolvido para a disciplina de IA para Analise Preditiva por Luis Gustavo da Silva, Acacia Rosar e Raphael Antonio dos Santos Pires.