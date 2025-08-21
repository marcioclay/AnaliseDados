# 📘 Estrutura Pandas


## 4. Estruturas Principais no Pandas

O Pandas possui duas estruturas de dados principais:

Series → vetor de dados unidimensional (1D).

DataFrame → tabela de dados bidimensional (2D).

Além disso, também existem variações úteis como Índices personalizados, DataFrames a partir de listas e leitura de arquivos externos.

## 4.1 Series

Uma Series é como uma coluna de uma tabela ou um vetor com rótulos.

Criando uma Series simples
- import pandas as pd

# Criando uma série de números
```
s = pd.Series([10, 20, 30, 40, 50])
print(s)


Saída:

0    10
1    20
2    30
3    40
4    50
dtype: int64
```

👉 Aqui o Pandas criou índices automáticos (0, 1, 2...).

Criando uma Series com índice personalizado
```
s = pd.Series([10, 20, 30], index=["A", "B", "C"])
print(s)


Saída:

A    10
B    20
C    30
dtype: int64
```

Criando uma Series a partir de dicionário
```
s = pd.Series({"Ana": 8.5, "Bruno": 7.0, "Carlos": 9.2})
print(s)

Saída:

Ana       8.5
Bruno     7.0
Carlos    9.2
dtype: float64
```

👉 Isso é útil quando queremos transformar dados de chave:valor em tabela.

## Funções úteis em Series
- print(s.mean())   # Média
- print(s.max())    # Máximo
- print(s.min())    # Mínimo
- print(s.head(2))  # Primeiros 2 elementos
- print(s.tail(2))  # Últimos 2 elementos

## 4.2 DataFrame

Um DataFrame é a estrutura mais usada no Pandas: uma tabela com linhas e colunas.

Criando DataFrame a partir de dicionário
```
dados = {
    "Nome": ["Ana", "Bruno", "Carlos", "Diana"],
    "Idade": [23, 35, 31, 19],
    "Nota": [8.5, 7.0, 9.2, 6.8]
}

df = pd.DataFrame(dados)
print(df)
```

## Criando DataFrame a partir de lista de listas
```
dados = [
    ["Ana", 23, 8.5],
    ["Bruno", 35, 7.0],
    ["Carlos", 31, 9.2],
    ["Diana", 19, 6.8]
]

df = pd.DataFrame(dados, columns=["Nome", "Idade", "Nota"])
print(df)
```
## Criando DataFrame com índice personalizado
```
df = pd.DataFrame(dados, columns=["Nome", "Idade", "Nota"], index=["A", "B", "C", "D"])
print(df)
```
## Acessando dados no DataFrame
```
print(df["Nome"])        # Seleciona coluna
print(df[["Nome","Nota"]])  # Seleciona múltiplas colunas
print(df.loc["A"])       # Seleciona linha pelo índice
print(df.iloc[2])        # Seleciona linha pela posição
```

## Funções úteis em DataFrame
```
print(df.info())      # Informações gerais
print(df.describe())  # Estatísticas (média, min, max, etc.)
print(df.head(2))     # Primeiras 2 linhas
print(df.tail(2))     # Últimas 2 linhas
print(df.shape)       # Quantidade de linhas e colunas
print(df.columns)     # Nome das colunas
print(df.index)       # Índices
```

## Alterando colunas
```
df["Status"] = ["Aprovado", "Aprovado", "Aprovado", "Reprovado"]
print(df)
```
## 4.3 Outras Estruturas Derivadas

Index → objeto que representa os índices (linhas).

Series dentro de DataFrame → cada coluna de um DataFrame é uma Series.

Exemplo:
```
coluna_notas = df["Nota"]
print(type(coluna_notas))  # pandas.core.series.Series
```

📌 Resumo :

- Series → coluna (vetor com índice).

- DataFrame → tabela completa (linhas + colunas).

- Cada coluna de um DataFrame é, na verdade, uma Series.
