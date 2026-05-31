# Pipeline de Higienização de Dados — Olist E-Commerce

## 📋 Descrição do Projeto
Este projeto foi desenvolvido como entrega para o Mini-Projeto Avaliativo (Módulo 1). O objetivo principal é simular o dia a dia de um Analista de Dados Júnior na resolução de problemas de Engenharia de Dados, construindo um pipeline robusto, performático e puramente **nativo em Python** para realizar a higienização (*Data Cleaning*) e padronização de duas bases oficiais da Olist: 
* O dataset de produtos (`olist_products_dataset.csv`)
* O dataset de pedidos (`olist_orders_dataset.csv`)

As inconsistências originais dessas bases impediam a execução de relatórios automatizados da diretoria. Este script lê os dados brutos diretamente da internet, processa-os linha a linha na memória utilizando dicionários e gera novos arquivos higienizados e prontos para o consumo de BI.

---

## 🛠️ Recursos e Tecnologias Utilizadas
Para garantir a avaliação da lógica pura de programação estruturada, o projeto foi desenvolvido **sem o uso da biblioteca Pandas**, adotando estritamente os seguintes recursos nativos do Python:
* **Módulo `csv` (`DictReader` e `DictWriter`):** Para o mapeamento de colunas em formato de dicionários e manipulação de arquivos estruturados.
* **Gerenciadores de Contexto (`with open()`):** Para garantir o fechamento seguro e automático dos fluxos de escrita.
* **Módulo `urllib.request`:** Para realizar a ingestão dos dados de forma automatizada direto do GitHub Raw.
* **Expressões Regulares (Módulo `re`):** Para filtragem cirúrgica e limpeza de caracteres especiais em strings.
* **Módulo `datetime`:** Para conversão e internacionalização de formatos temporais.

---

## 🚀 Guia de Execução no Google Colab

O código foi otimizado para rodar em blocos sequenciais no Google Colab, garantindo modularidade. Siga os passos para execução:

1. Acesse o [Google Colab](https://colab.research.google.com/) e crie um novo Notebook.
2. Crie três células de código sequenciais e insira os blocos estruturados do script:
   * **Célula 1:** Importação de bibliotecas nativas e inicializações.
   * **Célula 2:** Declaração das funções modulares de higienização (`tratar_categoria`, `validar_dimensoes` e `formatar_data`).
   * **Célula 3:** Execução do pipeline principal (`main()`) que consome as URLs e gera o relatório.
3. Clique em **Ambiente de Execução > Executar tudo**.
4. Ao final da execução, os arquivos higienizados `produtos_limpos.csv` e `pedidos_limpos.csv` estarão disponíveis na barra lateral de arquivos do Colab para download, e o relatório estatístico será impresso no console.

---

## 🧠 Reflexão Teórica: Engenharia de Dados e Machine Learning

A aplicação de uma lógica de programação rigorosa na etapa de higienização de dados (*Data Cleaning*) é o pilar fundamental para garantir a integridade de qualquer modelo preditivo de Inteligência Artificial. Se alimentarmos um algoritmo com dados ruidosos, incompletos ou mal formatados, o modelo aprenderá padrões falsos ou irrelevantes, consolidando o famoso axioma da ciência da computação: *Garbage In, Garbage Out* (Se entra lixo, sai lixo). Ao criar regras estritas baseadas em regras de negócio para tratar categorias nulas e descartar registros com dimensões físicas ausentes, impedimos que futuros algoritmos estatísticos tomem decisões enviesadas ou baseadas em anomalias operacionais, gerando estimativas de frete ou agrupamentos logísticos muito mais realistas.

Além disso, uma etapa de preparação de dados bem estruturada atua como uma das defesas mais eficazes contra o **Overfitting** (quando o modelo decora o ruído dos dados de treino, perdendo a capacidade de generalizar para dados novos). Se mantivéssemos dados incoerentes no dataset — como um pedido sem data de entrega cujo status operacional estivesse marcado erroneamente como "entregue" por falha de sistema —, a Inteligência Artificial poderia interpretar esse ruído como um comportamento padrão de mercado. Ao mitigar essas inconsistências através de funções customizadas e expressões regulares, o conjunto de dados passa a refletir fielmente a realidade mercadológica da empresa, mitigando vieses e permitindo que os modelos matemáticos de Machine Learning operem com máxima precisão e segurança em ambiente de produção.

---
