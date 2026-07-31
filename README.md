# ⭐ Modelagem Star Schema no Power BI

## 📌 Sobre o projeto

Este projeto apresenta a construção de um modelo dimensional utilizando a arquitetura **Star Schema** no Power BI, a partir da base de dados **Financial Sample**.

O objetivo foi transformar uma única tabela de origem em um modelo composto por tabelas dimensão e uma tabela fato, seguindo os conceitos de modelagem dimensional utilizados em Business Intelligence (BI).

---

## 🎯 Objetivos

- Aplicar conceitos de Star Schema.
- Organizar os dados em tabelas dimensão e fato.
- Melhorar a estrutura para análise de dados.
- Utilizar recursos do Power Query e DAX.
- Desenvolver boas práticas de modelagem no Power BI.

---

# Tecnologias utilizadas

- Microsoft Power BI Desktop
- Power Query
- DAX (Data Analysis Expressions)

---

# Base de dados

Financial Sample

A tabela original foi utilizada como fonte para criação de todas as dimensões e da tabela fato.

---

# Estrutura do modelo

O modelo foi dividido nas seguintes tabelas:

## Financials_Origem

Tabela utilizada como backup da base original.

Após a criação das demais tabelas, foi ocultada do relatório conforme solicitado no desafio.

---

## D_Produtos

Tabela dimensão criada por agrupamento contendo:

- ID_Produto
- Produto
- Média de unidades vendidas
- Média do valor de venda
- Mediana do valor de venda
- Valor máximo de venda
- Valor mínimo de venda

---

## D_Produtos_Detalhes

Tabela dimensão contendo:

- ID_Produto
- Discount Band
- Manufacturing Price
- Sale Price
- Product
- Segment
- Units Sold

---

## D_Descontos

Tabela dimensão contendo:

- ID_Produto
- Discounts
- Discount Band

---

## D_Detalhes

Tabela criada para armazenar informações complementares não contempladas nas demais dimensões.

Campos:

- Country
- Segment
- Discount Band
- Manufacturing Price
- Sale Price
- Units Sold
- ID_Produto

---

## D_Calendario

Tabela calendário criada utilizando DAX.

```DAX
D_Calendario =
CALENDAR(
    MIN(F_Vendas[Date]),
    MAX(F_Vendas[Date])
)
```

Também foram criadas colunas auxiliares:

- Ano
- Mês
- Nome do mês

---

## F_Vendas

Tabela fato contendo:

- SK_ID
- ID_Produto
- Product
- Units Sold
- Sales
- Profit
- Country
- Segment
- Discount Band
- Date

---

# Relacionamentos

O modelo possui relacionamento entre:

- D_Produtos → F_Vendas
- D_Calendario → F_Vendas

A tabela **Financials_Origem** foi mantida apenas como backup e ocultada da visualização.

---

# Imagem do modelo



![Modelo](imagens/modelo-star-schema.png.png)

---

# Aprendizados

Durante este projeto foram aplicados conceitos como:

- Modelagem Dimensional
- Star Schema
- Power Query
- Agrupamentos
- Colunas Condicionais
- Organização de Dimensões
- Criação de Tabela Calendário
- Funções DAX
- Boas práticas de modelagem de dados

---

# Autor

**Tatiana Lima**

---

# Bootcamp

Projeto desenvolvido como parte de um **desafio prático da DIO (Digital Innovation One)** durante o Bootcamp de Power BI.
