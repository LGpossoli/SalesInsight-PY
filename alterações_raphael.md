# Geração do CSV

1. Removido caminho absoluto do 'to_csv': o arquivo agora é salvo na pasta do projeto, tornando o script portável entre diferentes máquinas

2. Trocado o separador do CSV de ',' para ';' para evitar conflitos com o padrão numérico brasileiro (onde vírgula é separador decimal). Comentário adicionado em 'gerar_csv.py'


# Criação de arquivos

1. Criado arquivo 'requirements.txt' com as dependências do projeto, gerado via:

    python -m pip freeze > requirements.txt

    Para instalar as dependências em outra máquina, execute:

    pip install -r requirements.txt


# salesinsight_alterações_raphael.ipynb

1. Adicionados markdowns e comentários ao longo do notebook para identificar e documentar cada etapa do pipeline de análise

2. As tratativas de limpeza e as transformações de dados foram feitas em cópias para proteger o estado dos dados.
    Resumo dos DataFrames:
        df_bruto — original intocado
        df — cópia intermediária para limpeza
        df_limpo — dataset higienizado (sem nulos/inválidos)
        df_transformado — dataset com colunas derivadas (receita e tempo)
        df_segmentado — dataset de agregação por cliente (Ouro/Prata/Bronze)

3. Removi os caminhos fixos da máquina do Luis e incluí caminhos genéricos:
        arquivo csv: df_bruto = pd.read_csv('./vendas.csv', sep=';')
        output dos gráficos: def gerar_visualizacoes(df_limpo, resultado_metricas, output_dir="outputs/graficos")