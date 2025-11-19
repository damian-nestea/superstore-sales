# Análise Inicial

Para familiarização com o conjunto de dados, realizamos uma análise rápida de cada variável. Uma forma prática é utilizar o filtro da planilha, que oferece uma visão geral dos valores em cada coluna.
Foram analisadas as seguintes variáveis:
- **Order_Date** e **Order_Year** para identificar os anos abrangidos pelo *dataset*;

![Order Year](../images/analyse/01_check_order_year.png)

- **Segment** para verificar os diferentes segmentos de clientes;

![Client Segment](../images/analyse/02_check_segment.png)

- Variáveis de localização como **Country**, **State**, **City** e **Region**, a fim de compreender a distribuição geográfica dos clientes;

![Client Localization](../images/analyse/03_check_localization.png)

- **Category**, **Sub_Category** e **Product_Name** para conhecer o portfólio de produtos comercializados pela empresa.

![Product Info](../images/analyse/04_check_product_info.png)

Utilizamos **tabelas dinâmicas** para listar os valores presentes em cada uma das variáveis mencionadas. O resultado obtido foi o seguinte:

![Pivot Tables Overview](../images/analyse/05_pivot_table_table_overview.png)

---

## Análise Univariada de “Sales”

Analisamos a variável de vendas do dataset. Para isso, empregamos tabelas dinâmicas para totalizar o volume e o valor total das vendas. Também aplicamos as funções **MÉDIA**, **MED**, **MÁXIMO**, **MÍNIMO** e **DESVPAD.P** para calcular a média, mediana, valor máximo, valor mínimo e o desvio padrão das vendas.

![Sales Info](../images/analyse/06_overview_column_sales.png)

Construímos um histograma com os dados da coluna *Sales* para visualizar a distribuição dos valores.

![Sales Distribution](../images/analyse/07_distribution_column_sales.png)

## Conclusão
Com base nos dados coletados, compilamos a seguinte tabela com as informações gerais mais relevantes do dataset antes de prosseguir com análises mais detalhadas:

![Dataset Overview](../images/analyse/08_overview_dataset.png)
