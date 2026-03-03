# 📊 Análise de Performance de Vendas SQLite

Projeto de análise de dados com foco em performance de vendas, utilizando SQLite

---

## Sumário
1. [Objetivo](#Objetivo)
2. [Dados Utilizados](#Dados-Utilizados)
3. [Consultas SQL Desenvolvidas](#Consultas-SQL-Desenvolvidas)
4. [Resultados](#Resultados)
5. [Tecnologias Utilizadas](#Tecnologias-Utilizadas)

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

<img width="933" height="417" alt="image" src="https://github.com/user-attachments/assets/5e56bcab-ea51-46c9-a2fe-8856b0d4d83b" />



# Número de clientes únicos atendidos por cada distribuidor, considerando o tamanho da loja

<img width="956" height="393" alt="image" src="https://github.com/user-attachments/assets/9f4a472a-c5e7-4d27-8cc9-f3d2c688b876" />



# Identifique qual distribuidor possui o maior número de clientes únicos

<img width="592" height="432" alt="image" src="https://github.com/user-attachments/assets/d329b4c1-8d56-4ee2-a9aa-782ea8cda683" />



# Identifique qual distribuidor possui o maior número de clientes únicos considerando o tamanho da loja

<img width="742" height="418" alt="image" src="https://github.com/user-attachments/assets/c4355c1e-a436-46e6-aced-15869a12deb1" />


#  Total de vendas (valor) por distribuidor

<img width="661" height="392" alt="image" src="https://github.com/user-attachments/assets/c63cf07f-64bf-427a-a415-836c509abff9" />


## Resultados

Após as consultas realizadas:

Todas os distribuidores possuem a mesma quantidade de clientes únicos.
A Distribuidora Alfa apresentou o maior valor total de vendas.

## Tecnologias Utilizadas

* VS Code com extensão SQLite
