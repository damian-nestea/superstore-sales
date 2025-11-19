# Processo de ETL

Antes da análise exploratória, foi realizado o processo de ETL para preparar os dados utilizando o **Power Query do Excel**. As etapas executadas foram:

## Extração (Extract):
1. Criação de um novo arquivo em Excel e acesso à funcionalidade: **Dados > Obter Dados > De Arquivo > De CSV**
![Import do CSV](../images/etl/01_import_csv.png)

2. Seleção e importação do *dataset* previamente baixado do **Kaggle**

## Transformação (Transform):
3. Acesso ao editor do Power Query através da opção "**Transformar Dados**"
![Abrir Power Query](../images/etl/02_transform_data.png)
![Abrindo Power Query](../images/etl/03_power_query_init.png)

4. Retirar a etapa de alteração dos tipos de dados no Power Query, na aba de Etapas.
![Remover Alteração de tipo de dados](../images/etl/04_power_query_remove_data_type.png)

5. Definição manual dos tipos de dados apropriados para cada coluna:
**Colunas de data**: Configurado formato brasileiro (dd/mm/aaaa) usando a opção "**Usando a Localidade**"
**Valores numéricos**: Ajustado separador decimal de ponto para vírgula utilizando "**Usando a Localidade**"
![Mudando tipo de dados](../images/etl/05_power_query_edit_data_type.png)

6. Remoção de registros duplicados através da seleção de todas as colunas e aplicação de **Remover Linhas > Remover Duplicatas**
![Remover duplicadas](../images/etl/06_pq_remove_duplicate.png)

7. Padronização dos nomes das colunas substituindo espaços por *underscore* (_)
![Renomeando colunas](../images/etl/07_pq_rename_columns.png)

8. Aplicação da função **Transformar > Formato > Cortar** em colunas textuais para eliminar espaços extras
![Retirando espaços](../images/etl/08_pq_trim_column_text.png)

9. Criação de colunas derivadas da data de pedido (**Order_Year, Order_Month, Order_Quarter**) através de **Adicionar Coluna > Coluna de Exemplos > Da Seleção**
![Criando colunas](../images/etl/09_pq_add_new_columns.png)
![Criando colunas](../images/etl/10_pq_add_new_columns.png)


## Carregamento (Load) e Validação:
10. Carregamento dos dados tratados para o Excel mediante **Página Inicial > Fechar e Carregar**
![Fechando e Carregando](../images/etl/11_pq_close_load.png)
![Dados carregados](../images/etl/12_data_loaded.png)

11. Validação da integridade dos dados:
- Contagem total de registros: **9.800**
- Verificação de valores ausentes por coluna usando função **CONT.VALORES**. Alternativamente pode ser feito também com **CONTAR.VAZIO**
- Identificação de 11 registros sem valor na coluna **Postal_Code** (9.789 preenchidos). **Decisão**: Manter todos os registros, já que a coluna não seria usada para as análises planejadas no futuro. 
![Contagem Vazios](../images/etl/13_count_values.png)
![Contagem Vazios](../images/etl/14_count_values.png)

## Preparação Final para Análise:
12. Criação da coluna **Order_Month_Name** em inglês usando função **SE** para manter consistência linguística com o restante do *dataset*
![Coluna Nome do Mês](../images/etl/15_month_names.png)

13. Organização da planilha com renomeação da aba e salvamento do arquivo
