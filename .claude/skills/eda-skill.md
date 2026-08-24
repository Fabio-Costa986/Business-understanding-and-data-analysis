---
name: eda-skill
description: Guia completo para análise exploratória de dados do Tech Challenge de NPS
---

# EDA para Tech Challenge de NPS

Este skill documenta o processo de análise exploratória de dados para o Tech Challenge de NPS. Ele orienta a análise de dados para responder às quatro perguntas de negócio do desafio.

## Perguntas de Negócio Abordadas
1. Quais fatores parecem mais críticos para a satisfação?
2. O que mais gera detratores?
3. Existe algum "ponto de ruptura" na experiência do cliente?
4. Que tipo de cliente tende a ter NPS mais alto ou mais baixo?

## Instruções de Uso
- Ler o PDF com as instruções oficiais do Tech Challenge: C:\Users\amand\Documents\pos-tech-fiap-amanda\Business-understanding-and-data-analysis\reports\1IAST - Fase 1 - Tech Challenge.pdf
- Analisar o notebook parcialmente desenvolvido: C:\Users\amand\Documents\pos-tech-fiap-amanda\Business-understanding-and-data-analysis\notebook\EDA - Copia.ipynb
- Trabalhar com os arquivos Excel fornecidos:
  - Excel original da base: C:\Users\amand\Documents\pos-tech-fiap-amanda\Business-understanding-and-data-analysis\data\desafio_nps_fase_1.xlsx
  - Excel com as novas variáveis/colunas criadas: C:\Users\amand\Documents\pos-tech-fiap-amanda\Business-understanding-and-data-analysis\data\processed\df_avaliacao.xlsx

## Processo de Análise
1. Primeiro: entenda o trabalho já realizado
  Antes de alterar qualquer coisa:
  - Ler o PDF e entender os requisitos do Tech Challenge
  - Ler o notebook inteiro até o ponto em que ele foi desenvolvido
  - Entender: estrutura da base; variável nps_score; variáveis existentes; novas variáveis criadas; tratamentos realizados; análises já feitas; conclusões já obtidas
  - Ler os dois Excels para entender as variáveis disponíveis e confirmar suas características
  - Não refazer análises que já estejam adequadamente realizadas no notebook
  - O objetivo é dar continuidade ao notebook, e não começar um EDA do zero

2. Objetivo principal da análise
  O EDA precisa responder, com evidências dos dados, às quatro perguntas de negócio do Tech Challenge:
  1. Quais fatores parecem mais críticos para a satisfação? Identificar as variáveis que apresentam as relações/padrões mais relevantes com o nps_score
  2. O que mais gera detratores? Identificar quais características, situações, problemas ou perfis apresentam maior concentração/proporção de detratores
  3. Existe algum "ponto de ruptura" na experiência do cliente? Procurar mudanças relevantes no comportamento do NPS ou na proporção de detratores conforme alguma variável aumenta ou muda de categoria
  4. Que tipo de cliente tende a ter NPS mais alto ou mais baixo? Identificar padrões de perfil relacionados a Promotores, Neutros e Detratores

3. Use TODAS as variáveis disponíveis
  Não priorize automaticamente as variáveis agrupadas que criei
  Quero que você considere:
  - variáveis originais
  - variáveis agrupadas
  - variáveis categóricas
  - variáveis numéricas
  - variáveis derivadas
  - variáveis relacionadas à experiência
  - variáveis relacionadas ao perfil do cliente
  As novas variáveis agrupadas devem ser utilizadas somente quando agregarem valor à análise
  Se uma variável original for mais informativa do que sua versão agrupada, utilize a original
  Se uma variável agrupada tornar o padrão mais fácil de visualizar e interpretar, utilize-a
  Não crie novas variáveis simplesmente por criar. Só crie novas features se houver uma justificativa clara para responder uma das perguntas de negócio

4. Faça uma seleção inteligente das análises
  Não quero um EDA com dezenas de gráficos sem propósito
  Primeiro faça uma triagem das variáveis e identifique quais têm maior potencial de explicar o NPS
  Depois selecione as análises mais relevantes
  Para variáveis numéricas, considere quando fizer sentido:
  correlação com nps_score
  distribuição
  comparação de médias/medianas
  boxplots
  análise por faixas
  relação entre variável e proporção de detratores/promotores
  outros métodos simples que ajudem na interpretação
  Para variáveis categóricas, considere:
  NPS médio por categoria
  quantidade e percentual de detratores
  distribuição de Promotores/Neutros/Detratores
  gráficos de barras
  comparação entre categorias
  Não faça uma análise apenas porque ela é estatisticamente possível
  A pergunta deve ser sempre: "Essa análise ajuda a explicar por que o NPS está baixo?"

5. Gráficos são obrigatórios
  Execute diretamente no notebook os códigos necessários e crie gráficos relevantes para sustentar os insights
  Os gráficos precisam ser:
  claros
  legíveis
  visualmente organizados
  adequados à variável analisada
  fáceis de explicar em uma apresentação
  Evite:
  gráficos redundantes
  gráficos com informação demais
  gráficos puramente decorativos
  repetir o mesmo tipo de gráfico para todas as variáveis
  Para cada gráfico, inclua no notebook uma breve interpretação explicando o que devemos observar e por que isso é relevante para o negócio

6. Foque especialmente nos detratores
  Como o objetivo é entender o NPS baixo, quero uma investigação específica dos detratores
  Analise:
  - quais variáveis mais diferenciam detratores dos demais clientes
  - quais categorias concentram maior percentual de detratores
  - quais características aparecem com maior frequência entre detratores
  se existem combinações de características associadas a experiências particularmente ruins
  Não quero apenas saber: "Qual grupo possui menor NPS?"
  Quero entender: "O que caracteriza uma experiência que termina em detrator?"

7. Procure pontos de ruptura
  Faça uma investigação específica para encontrar possíveis thresholds ou mudanças bruscas
  Por exemplo: Até X → comportamento relativamente estável; Depois de X → aumento relevante de detratores / queda do NPS
  Caso encontre um possível ponto de ruptura: mostrar o gráfico; mostrar os números que sustentam a conclusão; explicar por que aquele ponto pode ser relevante para o negócio
  Se não existir evidência clara de um ponto de ruptura, informe isso
  Não force a existência de um threshold apenas para responder à pergunta

8. Análise de perfil
  Tente identificar padrões de clientes com NPS alto e baixo
  Considere combinações de variáveis quando fizer sentido
  Por exemplo: perfil demográfico + comportamento; comportamento + experiência; frequência + experiência; faixa de idade + comportamento; problemas + tempo de entrega
  Mas mantenha a análise simples e interpretável
  O objetivo é chegar a algo semelhante a: "Clientes com características X, Y e Z apresentam maior concentração de detratores." ou "Clientes com características A e B apresentam comportamento mais próximo dos promotores."
  Somente faça essas afirmações se os dados sustentarem

9. Estatística ≠ causalidade
  Tenha cuidado ao interpretar os resultados
  Não diga que uma variável causa um NPS baixo apenas porque existe associação
  Prefira expressões como: "está associado"; "apresenta relação"; "parece estar relacionado"; "apresenta maior concentração"; "é um possível fator"
  Se uma análise não apresentar evidência suficiente, deixe isso claro

10. Estilo do código
  Quero código simples, didático e fácil de entender
  Priorize: pandas; numpy; matplotlib; seaborn
  Evite métodos estatísticos excessivamente sofisticados se uma análise simples responder à pergunta
  O código precisa ser compreensível para alguém avaliando o Tech Challenge

11. Estrutura do notebook
  Ao adicionar as análises, organize o notebook de forma lógica
  Sempre que possível, mantenha a estrutura:
  Pergunta de negócio → Hipótese / objetivo → Análise → Visualização → Insight → Implicação para o negócio
  Não escreva conclusões genéricas como: "Podemos observar que existe uma diferença entre os grupos."
  Quero conclusões específicas, baseadas nos números encontrados

12. Ao final do EDA
  Depois de executar todas as análises, crie uma seção final no notebook chamada:
  Conclusões da Análise Exploratória
  Nessa seção, responda explicitamente:
  1. Quais fatores parecem mais críticos para a satisfação? Listar e explicar os principais fatores encontrados
  2. O que mais gera detratores? Listar os principais fatores/perfis associados aos detratores
  3. Existe algum ponto de ruptura? Informar se foi encontrado algum e qual é a evidência
  4. Que tipo de cliente tende a ter NPS mais alto ou mais baixo? Descrever os principais perfis identificados
  Depois disso, faça uma síntese executiva, com os 3–5 principais insights que alguém da área de negócio deveria levar dessa análise

13. Regra mais importante
  Não tente "preencher" as quatro perguntas artificialmente
  Se os dados não permitirem responder alguma pergunta de forma confiável, diga explicitamente: "Os dados disponíveis não apresentam evidência suficiente para concluir X."
  É melhor uma conclusão limitada, porém defensável, do que uma conclusão inventada
  Meu objetivo não é ter o maior número possível de análises
  Meu objetivo é construir um EDA que consiga responder:
  Por que o NPS está baixo, quem são os detratores e quais aspectos da experiência parecem estar mais associados a essa insatisfação?

Execute as análises diretamente no notebook, crie os gráficos necessários e escreva as interpretações junto aos resultados
Ao terminar, revise o notebook como se você fosse o avaliador do Tech Challenge e verifique se as quatro perguntas foram efetivamente respondidas com evidências.