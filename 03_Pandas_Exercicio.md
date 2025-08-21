# 📝 Exercício – Panda

## Questão 1 – Criando DataFrame a partir de dicionário

Crie um DataFrame a partir do seguinte dicionário:
```
dados = {
    "Produto": ["Camiseta", "Calça", "Tênis", "Boné"],
    "Preço": [50, 120, 300, 40],
    "Estoque": [100, 50, 30, 200]
}
```

- Exiba o DataFrame.

- Mostre apenas a coluna Preço.

- Mostre apenas as duas primeiras linhas.
- 

## Questão 2 – Lendo dados de um arquivo CSV

Baixe ou crie um arquivo chamado alunos.csv com o seguinte conteúdo:

```
Nome,Idade,Nota
Ana,23,8.5
Bruno,35,7.0
Carlos,31,9.2
Diana,19,6.8
```

- Leia o arquivo com pd.read_csv("alunos.csv").

- Mostre apenas a coluna Nota.

- Calcule a média das notas.

## Questão 3 – Salvando DataFrame em CSV

A partir do DataFrame criado na Questão 1, salve os dados em um arquivo chamado produtos.csv.
Depois, leia novamente o arquivo e exiba os dados.

## Questão 4 – Lendo arquivo Excel

Suponha que você tenha um arquivo Excel chamado vendas.xlsx com a planilha:
```
Produto	Quantidade	Preço
Caderno	100	10.5
Caneta	300	2.5
Mochila	50	120.0
```
- Use pd.read_excel("vendas.xlsx") para ler os dados.

- Calcule o valor total de cada produto (Quantidade × Preço).

- Crie uma nova coluna chamada Total.

## Questão 5 – Operações com DataFrame

Usando o DataFrame da Questão 2 (alunos.csv):

- Mostre apenas os alunos com Nota >= 7.

- Adicione uma nova coluna chamada Situação com os valores:

```
"Aprovado" se a nota ≥ 7

"Reprovado" caso contrário
```
- Salve o resultado em um arquivo chamado resultado.xlsx.


Selecionar colunas/linhas

Criar colunas novas e aplicar condições
