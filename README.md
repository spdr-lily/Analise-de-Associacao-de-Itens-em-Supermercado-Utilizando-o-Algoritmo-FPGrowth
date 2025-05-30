**Análise de Associação de Itens em Supermercado Utilizando o Algoritmo FP-Growth**

**1\. Introdução**

A análise de associação de itens é uma técnica de mineração de dados amplamente utilizada para descobrir relações interessantes entre variáveis em grandes bancos de dados. No contexto do varejo, essa análise permite identificar padrões de compra, ou seja, quais produtos são frequentemente adquiridos em conjunto. Este projeto aplica o algoritmo FP-Growth a um conjunto de dados de transações de supermercado com o objetivo de extrair regras de associação que possam ser utilizadas para otimizar estratégias de marketing, aprimorar a gestão de estoque e implementar sistemas de recomendação de produtos.

A capacidade de prever quais itens os clientes provavelmente comprarão juntos tem um valor estratégico significativo. Por exemplo, um supermercado pode usar essas informações para posicionar produtos relacionados próximos uns aos outros nas prateleiras, criar promoções conjuntas ou enviar recomendações personalizadas aos clientes. Além disso, a análise pode ajudar a otimizar os níveis de estoque, garantindo que os produtos frequentemente comprados juntos estejam sempre disponíveis.

**2\. Metodologia**

A metodologia adotada neste estudo compreende as seguintes etapas:

**2.1. Coleta e Preparação dos Dados**

O conjunto de dados utilizado contém informações sobre as transações de compra em um supermercado, incluindo o número do cliente, a data da compra e a descrição dos itens adquiridos. Os dados foram carregados em um DataFrame do pandas e pré-processados para o formato adequado à análise de associação.

**2.2. Transformação dos Dados**

Para aplicar o algoritmo FP-Growth, os dados foram transformados em um formato transacional. Cada transação representa uma compra única, e os itens adquiridos são os elementos dessa transação. A biblioteca `mlxtend` foi utilizada para realizar essa transformação, convertendo as listas de itens comprados em uma matriz booleana, onde as colunas representam os itens e as linhas representam as transações.

**2.3. Aplicação do Algoritmo FP-Growth**

O algoritmo FP-Growth foi aplicado à matriz transacional para identificar conjuntos frequentes de itens. O suporte mínimo foi definido como 0,5%, o que significa que apenas os conjuntos de itens que aparecem em pelo menos 0,5% das transações foram considerados. O algoritmo FP-Growth é eficiente na descoberta de padrões frequentes, pois utiliza uma estrutura de árvore para compactar o banco de dados transacional.

**2.4. Geração de Regras de Associação**

A partir dos conjuntos frequentes de itens, regras de associação foram geradas. Essas regras indicam relações do tipo "se A, então B", onde A e B são conjuntos de itens. A confiança foi utilizada como métrica para avaliar a força das regras, com um limiar mínimo de 0,5%. A confiança de uma regra é a probabilidade de que o item B seja comprado dado que o item A já foi comprado.

**2.5. Análise e Filtragem das Regras**

As regras geradas foram analisadas e filtradas para identificar padrões relevantes. Neste projeto, foi realizada uma análise específica das regras que contêm "soda" como antecedente, com o objetivo de entender quais itens são frequentemente comprados junto com refrigerantes. As regras foram ordenadas por confiança para destacar as associações mais fortes.

**3\. Resultados**

Na análise específica das regras que contêm "soda" como antecedente, foram encontradas as seguintes associações:

* `soda` \-\> `whole milk` (confiança: 11.96%)  
* `soda` \-\> `other vegetables` (confiança: 10.16%)  
* `soda` \-\> `rolls/buns` (confiança: 8.00%)  
* `soda` \-\> `sausage` (confiança: 6.34%)  
* `soda` \-\> `tropical fruit` (confiança: 5.84%)  
* `soda` \-\> `yogurt` (confiança: 5.69%)

Esses resultados indicam que os clientes que compram refrigerantes também tendem a comprar leite integral, outros vegetais, pães, salsichas, frutas tropicais e iogurte. A confiança dessas regras varia de 5.69% a 11.96%, refletindo a probabilidade de que esses itens sejam comprados junto com refrigerantes.

**4\. Conclusão**

Este projeto demonstrou a eficácia da análise de associação de itens, utilizando o algoritmo FP-Growth, para descobrir padrões de compra em um supermercado. As regras de associação extraídas fornecem insights valiosos que podem ser aplicados em diversas áreas do varejo.

As associações identificadas podem ser utilizadas para:

* **Marketing:** Criar promoções conjuntas, agrupar produtos relacionados nas prateleiras e desenvolver campanhas publicitárias direcionadas.  
* **Gestão de Estoque:** Otimizar os níveis de estoque, garantindo que os produtos frequentemente comprados juntos estejam sempre disponíveis para os clientes.  
* **Recomendação de Produtos:** Implementar sistemas de recomendação que sugiram aos clientes itens que eles provavelmente comprarão com base em seu histórico de compras e nos padrões de compra identificados.

A análise específica das regras que contêm "soda" como antecedente revelou associações interessantes com outros produtos, como leite integral, vegetais e pães. Essas informações podem ser utilizadas para posicionar esses produtos próximos aos refrigerantes nas prateleiras, aumentando as vendas e melhorando a experiência de compra do cliente.
