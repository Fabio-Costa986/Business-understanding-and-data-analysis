# 01 — Entendimento do Negócio e Definição da Target

## 1. Entendimento do Negócio

### 1.1 Qual problema de negócio está sendo resolvido?
Hoje, analisando os dados de forma superficial, vimos que a empresa tem um NPS médio de 4.38, que é um NPS bem baixo e um alto numero de clientes que tiveram que fazer ao menos uma reclamação sobre o pedido. 

O NPS foi calculado pós compra, portanto esses números indicam que os clientes não estão satisfeitos com algum aspecto dos produtos comercializados, seja atrasos na entrega, qualidade do produto, pós venda, produtos entregues errados, etc. 

Deste modo, é possivel afirmar que o principal problema de negócio a ser resolvido é entender no que a empresa falhou/ está falhando, que poderia proporcionar aos proximos clientes uma melhor experiencia e, consequentemente, maior credibilidade no mercado, mais vendas e melhores notas.

### 1.2 Por que o NPS é importante para um e-commerce?

Quando falamos de comercio na internet cada cliente tem uma disponibilidade de opções muito maior do que nos comercios físicos. Além disso, a internet possibilita aos consumidores expressarem suas opnioes sobre o serviço ou produto de forma muito mais fácil, inclusive por meio de sites oficiais de reclamação, como por exemplo o Reclame Aqui, e um cliente que já está fazendo a compra por meio digital, tem acesso a opinioes de compradores muito mais acessivel do que em uma loja física. 

Portanto, o NPS se torna extremamente importante para o e-commerce para entender onde está falhando com o cliente e possibilitar uma melhor experiencia e, consequentemente, gerar mais engajamento online, melhores feedbacks e se sobressair em comparação os demais concorrentes, com produtos ou experiencias diferenciadas. 

### 1.3 Quais áreas poderiam se beneficiar desses insights?

Olhando para a base de dados temos alguns indicios de áreas que poderiam se beneficiar. 
A área de logistica por exemplo, tem o indicador de dias de atraso da entrega, que pode é um fator relevante que impacta o NPS especialmente porque 88% dos pedidos tem algum atraso, assim como os valores de frete, que também podem ser revistos em prol de motivar mais vendas e expandir o publico. 

O time de atendimento poderia reduzir custo com menor numero de acionamentos, pois com os dados que temos vemos que existe um alto indice de solicitações de atendimento para 78% dos pedidos realizados e uma taxa altissima de 99% de reclamações feitas nos pedidos analisados. 

Também tem o fator de descontos, que ao entender melhor o publico o e-commerce pode passar a ofertar melhores descontos a publicos especificos e trazer mais receita. 

Portanto ao entender o que está motivando os clientes a darem notas tão baixas de NPS e fazer reclamações pode auxiliar muito no custo da empresa, reduzindo custo de atendimento, de correção de pedidos e logistica.  


### 1.4 Reflexão: como o NPS impacta recompra, boca a boca e market share?

Com um NPS tão baixo, com média de 4,4, mostra que os clientes não estão satisfeitos com a empresa, seja pela qualidade dos produtos comercializados ou pelo atendimento e pós venda (ainda a ser avaliado com os dados). E um cliente insatisfeito dificilmente irá comprar novamente o mesmo produto, salvo em situações de produtos muito especificos que só essa empresa venda. 

Isso impacta muito pois os clientes farão reclamações online, nas paginas de redes sociais da loja ou em canais como o Reclame aqui, impedindo que novos clientes possam comprar esses produtos, dificultando o aumento de market share. 

### 1.5 Indicadores de mercado complementares
É importante entendermos os parametros do mercado que venda produtos similares à empresa analisada, pois um NPS de 4,4 (detrator) como observamos na base de dados é um NPS muito ruim caso as demais empresas do setor tenham NPS maior (neutro ou promotor), porém se a média do mercado for um NPS mais baixo, pode indicar que existe um problema sistemico em todo o setor que torna a experiencia do cliente ruim e resulta em um NPS médio de mercado baixo. 

Outro indicador de mercado importante é referente a logistica, pois na empresa analisada existe uma taxa alta de trasos na entrega, mas é importante avaliar se isso é uma regra nos e-commerce no brasil ou se, de fato, a empresa em questão não está conseguindo dar os prazos corretos aos clientes, gerando frustração. 

Com esse NPS baixo é relevante buscar dados de concorrentes para validar se há perda de clientes para outra empresa do setor. 

## 2. Definição da Target


### 2.1 Qual variável representa a satisfação do cliente?
nps_score - que é a nota dada pelo cliente pós a compra 

### 2.2 Por que ela foi escolhida?
Porque ela mede, em uma escala de 0 a 10, a satisfação do cliente, sendo 0 totalmente insatisfeito e 10 satisfeito. 

### 2.3 Em que momento da jornada ela é coletada?
Essa variável é coletada após o cliente realizar a compra. Sendo que ele só dá sua opinião após o recebimento do produto

### 2.4 Riscos de uso inadequado
É importante entender os diversos fatores que podem estar impactando o NPS, como região, custo de frete, atrasos

## sugestão de melhorias para o notebook: 
- validar se tem maior numero de atrasos por região
- onde o NPS é mais baixo por região? está bem distribuido ou é um problema regional?
- os clientes mais novos ou mais velhos tendem a reclamar mais ou menos?