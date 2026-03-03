# 📊 Análise de Performance de Vendas SQLite

Projeto de análise de dados com foco em performance de vendas, utilizando SQLite

---

## Sumário
1. [Objetivo](#Objetivo)
2. [Dados Utilizados](#Dados-Utilizados)
3. [Consultas SQL Desenvolvidas](#Consultas-SQL-Desenvolvidas)
4. 
5. [Recomendação Final](#Recomendação-Final)

---
## Objetivo

Este projeto tem como finalidade analisar o desempenho dos distribuidores com base em dados de vendas, identificando:

* Número de clientes únicos atendidos por distribuidor
* Distribuidor com o maior número de clientes únicos
* Total de vendas por distribuidor

---
## Dados Utilizados

Foram Criadas duas tabelas:

1. Distribuidor

Contendo as colunas: ID e NomeDistribuidor.

<img width="240" height="223" alt="image" src="https://github.com/user-attachments/assets/ffe2659d-2e94-426c-a1c4-bce32dcfd9d9" />

2. Vendas

Contendo as colunas : IDDistribuidor, Cliente, TamanhoLoja, QuantidadeVendida, ValorVendido

<img width="692" height="385" alt="image" src="https://github.com/user-attachments/assets/76d52cc4-36f3-44c5-a9e6-835d5e4ac904" />

---

## Consultas SQL Desenvolvidas


# Número de clientes únicos atendidos por cada distribuidor

<img width="957" height="445" alt="image" src="https://github.com/user-attachments/assets/88edb8fe-0d33-4347-84c7-11843a777965" />



# número de clientes únicos atendidos por cada distribuidor, considerando o tamanho da loja

<img width="962" height="401" alt="image" src="https://github.com/user-attachments/assets/46ab0c76-b405-428f-9d97-7be32586670e" />




# Identifique qual distribuidor possui o maior número de clientes únicos

<img width="592" height="432" alt="image" src="https://github.com/user-attachments/assets/d329b4c1-8d56-4ee2-a9aa-782ea8cda683" />



# Identifique qual distribuidor possui o maior número de clientes únicos considerando o tamanho da loja

-- Seleciona o nome do distribuidor
SELECT
    d.NomeDistribuidor AS distribuidor, 
-- Conta clientes distintos por distribuidor
    COUNT(DISTINCT (v.Cliente || '|' || v.TamanhoLoja)) AS clientes_unicos
-- Lista todos os distribuidores da tabela Distribuidor
FROM Distribuidor d
-- Junta as vendas correspondentes a cada distribuidor
LEFT JOIN Vendas v
-- Comparação de chaves para unir as tabelas
       ON v.IDDistribuidor = d.ID
-- Agrupa por distribuidor
GROUP BY d.NomeDistribuidor
-- Ordena para que o maior número fique em primeiro
ORDER BY clientes_unicos DESC
-- Pega somente o distribuidor com mais clientes
LIMIT 5;


#  Total de vendas (valor) por distribuidor

-- Seleciona as informações que queremos no resultado
SELECT
-- Nome do distribuidor
    d.NomeDistribuidor AS distribuidor,
-- Soma de valor por distribuidor
    SUM(v.ValorVendido) AS total_vendas   
-- Lista tabela Distribuidor
FROM Distribuidor d
-- Comparação de chaves para unir as tabelas
LEFT JOIN Vendas v
       ON v.IDDistribuidor = d.ID 
-- Agrupa por distribuidor
GROUP BY d.NomeDistribuidor
-- Ordena os distribuidores do maior para o menor total de vendas
ORDER BY total_vendas DESC;



## Recomendação Final

A Distribuidora Delta se destacou, liderando tanto em valor total de vendas quanto em quantidade de produtos vendidos.

Apesar disso, os dados mostram que o desempenho entre os distribuidores está relativamente equilibrado.

Como próximo passo, vale buscar estratégias para impulsionar os parceiros com menor valor e quantidade de vendas.
