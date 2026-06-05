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