📘 Aula Introdutória ao Pandas
🎯 Objetivos

Entender o que é o Pandas e para que serve.

Aprender a instalar e importar a biblioteca.

Criar e manipular Series e DataFrames.

Realizar operações básicas (filtrar, ordenar, estatísticas).

1. O que é o Pandas?

O Pandas é uma biblioteca Python para análise e manipulação de dados.
Ele é muito usado em ciência de dados porque facilita o trabalho com tabelas, parecido com Excel, mas com muito mais poder.

2. Instalação

No terminal/cmd ou dentro do Jupyter Notebook, execute:

pip install pandas

3. Importando a biblioteca
import pandas as pd

4. Estruturas principais

O Pandas possui duas estruturas principais:

Series → vetor de dados (1 dimensão).

DataFrame → tabela de dados (2 dimensões).

4.1 Criando uma Series
import pandas as pd

# Criando uma série de números
s = pd.Series([10, 20, 30, 40, 50])
print(s)


Saída:

0    10
1    20
2    30
3    40
4    50
dtype: int64


👉 Repare que o Pandas cria automaticamente um índice (0, 1, 2...).

4.2 Criando um DataFrame
# Criando um DataFrame com dicionário
dados = {
    "Nome": ["Ana", "Bruno", "Carlos", "Diana"],
    "Idade": [23, 35, 31, 19],
    "Nota": [8.5, 7.0, 9.2, 6.8]
}

df = pd.DataFrame(dados)
print(df)


Saída:

     Nome  Idade  Nota
0     Ana     23   8.5
1   Bruno     35   7.0
2  Carlos     31   9.2
3   Diana     19   6.8

5. Operações básicas no DataFrame
5.1 Selecionar colunas
print(df["Nome"])     # Mostra apenas a coluna Nome
print(df[["Nome", "Nota"]])  # Mostra duas colunas

5.2 Selecionar linhas
print(df.loc[0])   # Linha pelo índice (loc)
print(df.iloc[2])  # Linha pela posição (iloc)

5.3 Filtrar dados
# Alunos com nota maior que 7
print(df[df["Nota"] > 7])

5.4 Estatísticas rápidas
print(df["Nota"].mean())   # Média
print(df["Nota"].max())    # Valor máximo
print(df.describe())       # Resumo estatístico

5.5 Ordenar dados
print(df.sort_values("Nota", ascending=False))  # Ordena por nota decrescente

6. Importando dados de arquivos
CSV
# Lendo dados de um arquivo CSV
df_csv = pd.read_csv("dados.csv")
print(df_csv.head())   # Mostra as primeiras 5 linhas

Excel
# Lendo dados de um arquivo Excel
df_excel = pd.read_excel("dados.xlsx")
print(df_excel.head())
