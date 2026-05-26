Este trabalho esta disponível no git: https://github.com/echer/26E2-infnet-trabalho-pd-mineracao-de-dados-para-series-temporais.git.

# Dataset
Para este trabalho estou utilizando o dataset do kaggle `Takeaway Food Orders` disponível no link: https://www.kaggle.com/datasets/henslersoftware/19560-indian-takeaway-orders.


Order Date (Data do pedido)
Problema: Datas faltantes podem impedir análise temporal.
Soluções possíveis:
Remover linhas — se forem poucas (ex.: <1% do dataset).
Substituir por valor aproximado:
usar a data do pedido anterior ou posterior (Forward Fill ou Backward Fill).
usar uma data média/mode para o pedido (menos recomendado, perde precisão).
Node KNIME: Missing Value ou Row Filter para remover linhas.

Quantity (Quantidade de itens)
Problema: Quantidade faltante prejudica cálculo de receita.
Soluções:
Substituir por 1 se fizer sentido (pedido mínimo 1 item).
Substituir pela média ou mediana da coluna Quantity.
Node KNIME: Missing Value → escolher Replace with Mean ou Replace with Fixed Value.

Total Products (Total de produtos no pedido)
Problema: Usado para análise de tamanho de pedido e ticket médio.
Soluções:
Substituir pelo valor calculado somando Quantity por Order Number.
Substituir pela média de total por pedido se for aceitável.
Node KNIME: Missing Value → Replace with Mean ou criar fórmula em Math Formula.