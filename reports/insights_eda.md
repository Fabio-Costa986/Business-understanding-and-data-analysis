## 1. O que o notebook já consegue afirmar
Achados efetivamente demonstrados e hipóteses que ainda precisam ser testadas. 

## 1.1 A base está relativamente limpa
Pelas validações iniciais temos:
- 2.500 registros e 19 variáveis inicialmente.
- Nenhum valor ausente.
- Nenhuma linha duplicada.
- Nenhum order_id duplicado.
- Nenhum customer_id duplicado.
- As regras básicas de domínio não encontraram idades, NPS, valores negativos etc. inválidos.

A base apresenta boa completude e consistência estrutural, sem valores ausentes ou registros duplicados. **As principais inconsistências identificadas estão relacionadas a regras de negócio** entre variáveis, especialmente **entrega** e **desconto**.

## 2. O que os histogramas e boxplots mostram

## 2.1 Valor do pedido
O valor dos pedidos apresenta forte assimetria positiva, com concentração em valores mais baixos e uma cauda de pedidos de maior valor. A presença desses valores extremos merece atenção na modelagem, pois a média pode ser influenciada por pedidos de alto valor.
- Seria importante validar a relaçao **preco x quantidade** de itens 
- validar relação entre: Pedidos de maior valor apresentam NPS diferente dos pedidos de menor valor?

## 2.2 Valor de desconto
Os descontos apresentam forte assimetria positiva e presença de valores extremos. Além dos outliers estatísticos, foram identificados registros em que o desconto supera o valor do pedido, tratados como inconsistências de negócio.

De modo geral o histograma sugere que descontos altos são mais raros, indicando uma politica de desconto estruturada. **Nesta variável é importante retirar os 35 casos outliers da base**, pois são erros legítimos (um comercio não pode dar mais desconto do que o valor do pedido), além desses 35 casos inflacionarem a variância de modelos preditivos que usarem essa variável (distorce a correlação entre NPS e desconto). 
- Para a **documentação**: Removemos 35 registros onde discount_value > order_value, caracterizando erros de base de dados. Esta limpeza é essencial pois esses dados corrompidos comprometeriam a acurácia do modelo preditivo de NPS.
- Validar se descontos maiores estão associados a maior satisfação/NPS

## 2.3 Valor do frete
O valor do frete apresenta distribuição mais concentrada e simétrica, diferentemente das variáveis financeiras de pedido e desconto, que apresentam forte assimetria.
- Validar se fretes maiores podem estar associados a NPS menor.

## 2.4 NPS 
A distribuição do NPS apresenta forte concentração em notas baixas, refletida na predominância de clientes classificados como detratores. Apenas 4,60% dos registros são classificados como promotores.

| Categoria |          % |
| --------- | ---------: |
| Detrator  | **83,72%** |
| Neutro    | **11,68%** |
| Promotor  |  **4,60%** |

## 2.5 CSAT

O csat_internal_score apresenta forte concentração em valores baixos, especialmente próximos de zero, indicando elevada assimetria da variável.
- testar correlação entre NPS e CSAT

## 2.6 Idade do cliente
A idade apresenta distribuição relativamente ampla e sem valores extremos incompatíveis com o domínio, não havendo evidência de problemas de qualidade nessa variável.
- O NPS muda entre as faixas etárias?

## 2.7 Tempo de relacionamento
Não apresenta outliers estatísticos preocupantes. Mas, existe uma característica interessante: há bastante representação de clientes com relacionamento longo.
- Validar: Clientes com maior tempo de relacionamento apresentam NPS diferente de clientes novos?

## 2.8 Quantidade de itens 
Distribuição discreta e relativamente equilibrada entre 1 e 6 itens. Não há evidencia de outliers relevantes.
- validar: Pedidos com maior quantidade de itens apresentam NPS diferente?

## 2.9 Número de parcelas 
Apresenta distribuição relativamente equilibrada entre 1 e 11 parcelas.
Não há outliers relevantes pelo boxplot.

## 2.10 Tempo total de entrega
Distribuição bastante regular entre 2 e 14 dias.
Não há outliers relevantes.

## 2.11 Atraso na entrega
Os atrasos estão concentrados em poucos dias, mas existe uma cauda de pedidos com atrasos significativamente maiores, indicando diferentes níveis de severidade do problema logístico.
- Validar: A proporção do tempo de entrega correspondente ao atraso está negativamente associada ao NPS.

## 2.12 Tentativas de entrega
Distribuição somente entre 1, 2 e 3 tentativas.
Não há outliers.

## 2.13 Contatos com o atendimento
A maioria dos pedidos está associada a pelo menos um contato com o atendimento, enquanto uma parcela menor apresenta múltiplos contatos, caracterizando uma distribuição concentrada com cauda de casos de maior recorrência.
- validar: Quanto maior o número de contatos com atendimento, menor tende a ser o NPS.

## 2.14 Tempo de resolução 
Distribuição relativamente equilibrada entre 0 e 11.
Sem outliers relevantes.
Sozinha, não é uma variável muito interessante na análise univariada. Mas quando combinada com atendimento, podemos ter insights relevantes, como:
- Clientes que precisam de mais tempo para resolução apresentam menor NPS?

## 2.15 Número de reclamações registradas
Existe concentração em torno de 3–5 reclamações, mas uma cauda para valores maiores e alguns outliers.
E praticamente toda a base possui alguma reclamação (acima de 90%).
- Validar: O aumento da quantidade de reclamações está associado à redução do NPS.

## Principais insights retirados das conclusões sobre os gráficos que precisam ser validados

**Experiência logística**
- Quanto maior o atraso proporcional da entrega (delivery_delay_ratio), menor tende a ser o NPS.

**Recorrência de problemas**
- Quanto maior o número de contatos com o atendimento, menor tende a ser o NPS.

**Reclamações**
- Quanto maior o número de reclamações, menor tende a ser o NPS.

**Resolução**
- Maior tempo de resolução tende a estar associado a menor NPS.

**Satisfação interna**
- Clientes com maior csat_internal_score tendem a apresentar maior NPS.

**Perfil do cliente**
- NPS pode variar de acordo com idade, tempo de relacionamento e região.

E deixaria como **hipóteses secundárias**:

-valor do pedido;

-desconto;

-número de itens;

-parcelas;

-número de tentativas de entrega;

-frete.


