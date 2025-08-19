# Aula Introdutória: Pandas, Matplotlib e Seaborn

## 📑 Sumário

## Introdução

### Pandas – Manipulação de Dados

- Criando DataFrames

- Operações básicas

### Matplotlib – Gráficos básicos

- Gráfico de linha

- Gráfico de barras

### Seaborn – Visualizações estatísticas

- Gráfico de dispersão

- Gráfico de barras com estilo

### Exercícios práticos

### 1. Introdução

Na análise de dados em Python, algumas bibliotecas são fundamentais:

Pandas: para manipular tabelas de dados.

Matplotlib: para criar gráficos simples.

Seaborn: para gráficos estatísticos mais bonitos e informativos.

### 2. Pandas – Manipulação de Dados

O pandas é usado para organizar dados em tabelas chamadas DataFrames.

Exemplo – Criando um DataFrame
```
import pandas as pd

dados = {
    "Mes": ["Jan", "Fev", "Mar", "Abr", "Mai", "Jun"],
    "Vendas": [120, 150, 170, 160, 180, 200],
    "Gastos": [100, 110, 130, 120, 140, 150]
}

df = pd.DataFrame(dados)
print(df)
```

Saída:
```
   Mes  Vendas  Gastos
0  Jan     120     100
1  Fev     150     110
2  Mar     170     130
3  Abr     160     120
4  Mai     180     140
5  Jun     200     150
```

### 3. Matplotlib – Gráficos básicos

A biblioteca matplotlib permite criar gráficos simples, mas personalizáveis.

Exemplo – Gráfico de Linha
```
import matplotlib.pyplot as plt

plt.plot(df["Mes"], df["Vendas"], marker="o", label="Vendas")
plt.plot(df["Mes"], df["Gastos"], marker="s", label="Gastos")
plt.xlabel("Mês")
plt.ylabel("Valores")
plt.title("Vendas e Gastos")
plt.legend()
plt.show()
```

👉 Esse gráfico mostra a evolução de vendas e gastos ao longo dos meses.

Exemplo – Gráfico de Barras
```
plt.bar(df["Mes"], df["Vendas"], color="skyblue")
plt.xlabel("Mês")
plt.ylabel("Vendas")
plt.title("Vendas por Mês")
plt.show()
```

### 4. Seaborn – Visualizações estatísticas

O seaborn é construído sobre o matplotlib e facilita a criação de gráficos com estilo moderno.

Exemplo – Gráfico de Dispersão

```
import seaborn as sns

sns.scatterplot(x="Gastos", y="Vendas", data=df)
plt.title("Relação entre Gastos e Vendas")
plt.show()
```

👉 Esse gráfico mostra se há relação entre gastar mais e vender mais.

Exemplo – Gráfico de Barras
```
sns.barplot(x="Mes", y="Vendas", data=df, palette="Blues")
plt.title("Vendas por Mês (Seaborn)")
plt.show()
```

👉 Parecido com o matplotlib, mas com estilo automático mais bonito.
