
# ⚠️ Para ler/gravar Excel (.xlsx), garanta que o openpyxl esteja instalado:
```
pip install pandas openpyxl
```

## ✅ Questão 1 – DataFrame a partir de dicionário
```
import pandas as pd
```
## 1) Criar o DataFrame a partir do dicionário
```
dados = {
    "Produto": ["Camiseta", "Calça", "Tênis", "Boné"],
    "Preço": [50, 120, 300, 40],
    "Estoque": [100, 50, 30, 200]
}
df = pd.DataFrame(dados)
```

## 2) Exibir o DataFrame completo
```
print("DataFrame completo:")
print(df)
```
## 3) Mostrar apenas a coluna Preço
```
print("\nColuna 'Preço':")
print(df["Preço"])
```
## 4) Mostrar apenas as duas primeiras linhas
```
print("\nDuas primeiras linhas:")
print(df.head(2))
```

Saída esperada (resumo):
```
DataFrame completo:
    Produto  Preço  Estoque
0  Camiseta     50      100
1     Calça    120       50
2     Tênis    300       30
3      Boné     40      200

Coluna 'Preço':
0     50
1    120
2    300
3     40
Name: Preço, dtype: int64

Duas primeiras linhas:
    Produto  Preço  Estoque
0  Camiseta     50      100
1     Calça    120       50
```

## ✅ Questão 2 – Lendo dados de um arquivo CSV

Conteúdo do alunos.csv:
```
Nome,Idade,Nota
Ana,23,8.5
Bruno,35,7.0
Carlos,31,9.2
Diana,19,6.8
```
```
import pandas as pd
```
## 1) Ler o CSV
```
alunos = pd.read_csv("alunos.csv")
```
## 2) Mostrar apenas a coluna Nota
```
print("Coluna 'Nota':")
print(alunos["Nota"])
```
## 3) Calcular a média das notas
```
media = alunos["Nota"].mean()
print(f"\nMédia das notas: {media:.3f}")
```

Saída esperada (resumo):
```
Coluna 'Nota':
0    8.5
1    7.0
2    9.2
3    6.8
Name: Nota, dtype: float64

Média das notas: 7.875
```

## ✅ Questão 3 – Salvando DataFrame em CSV e lendo de volta
```
import pandas as pd
```
## Reaproveitando o df da Questão 1:
```
dados = {
    "Produto": ["Camiseta", "Calça", "Tênis", "Boné"],
    "Preço": [50, 120, 300, 40],
    "Estoque": [100, 50, 30, 200]
}
df = pd.DataFrame(dados)
```

## 1) Salvar em CSV
```
df.to_csv("produtos.csv", index=False)  # index=False evita salvar a coluna de índice
```
# 2) Ler novamente o arquivo e exibir
```
df_lido = pd.read_csv("produtos.csv")
print("Arquivo 'produtos.csv' lido novamente:")
print(df_lido)
```

Saída esperada (resumo):
```
Arquivo 'produtos.csv' lido novamente:
    Produto  Preço  Estoque
0  Camiseta     50      100
1     Calça    120       50
2     Tênis    300       30
3      Boné     40      200
```

## ✅ Questão 4 – Lendo arquivo Excel e criando coluna “Total”

Planilha vendas.xlsx (planilha única):
```
Produto	Quantidade	Preço
Caderno	100	10.5
Caneta	300	2.5
Mochila	50	120.0
```
Se ainda não tiver o arquivo, você pode criá-lo rapidamente:
```
import pandas as pd
vendas = pd.DataFrame({
    "Produto": ["Caderno", "Caneta", "Mochila"],
    "Quantidade": [100, 300, 50],
    "Preço": [10.5, 2.5, 120.0]
})
vendas.to_excel("vendas.xlsx", index=False)
```

- Agora, leia e crie a coluna Total:
```
import pandas as pd
```

## 1) Ler o Excel
```
df_vendas = pd.read_excel("vendas.xlsx")  # requer 'openpyxl' instalado
```

## 2) Calcular Total = Quantidade * Preço
```
df_vendas["Total"] = df_vendas["Quantidade"] * df_vendas["Preço"]

print(df_vendas)
```

Saída esperada:
```
   Produto  Quantidade   Preço   Total
0  Caderno         100   10.5  1050.0
1   Caneta         300    2.5   750.0
2  Mochila          50  120.0  6000.0
```

## ✅ Questão 5 – Filtro, nova coluna “Situação” e salvar em Excel
```
import pandas as pd
import numpy as np
```

## Ler o CSV de alunos (da Questão 2)
```
alunos = pd.read_csv("alunos.csv")
```

## 1) Mostrar apenas alunos com Nota >= 7
```
aprovados = alunos[alunos["Nota"] >= 7]
print("Aprovados (Nota >= 7):")
print(aprovados)
```

## 2) Adicionar coluna 'Situação' (Aprovado/Reprovado) no DataFrame completo
```
alunos["Situação"] = np.where(alunos["Nota"] >= 7, "Aprovado", "Reprovado")
print("\nDataFrame com coluna 'Situação':")
print(alunos)
```

## 3) Salvar o resultado em Excel
```
alunos.to_excel("resultado.xlsx", index=False)  # requer 'openpyxl'
print("\nArquivo 'resultado.xlsx' salvo com sucesso.")
```

- Saída esperada (resumo):
```
Aprovados (Nota >= 7):
     Nome  Idade  Nota
0     Ana     23   8.5
1   Bruno     35   7.0
2  Carlos     31   9.2
```
- DataFrame com coluna 'Situação':
  ```
     Nome  Idade  Nota   Situação
0     Ana     23   8.5  Aprovado
1   Bruno     35   7.0  Aprovado
2  Carlos     31   9.2  Aprovado
3   Diana     19   6.8  Reprovado
```
Arquivo 'resultado.xlsx' salvo com sucesso.


Seleção, filtro, ordenação e criação de novas colunas.

Uso de métodos descritivos e operações aritméticas em colunas.
