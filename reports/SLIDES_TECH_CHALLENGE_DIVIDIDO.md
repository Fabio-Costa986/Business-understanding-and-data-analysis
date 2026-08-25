# 📊 TECH CHALLENGE FASE 1 - APRESENTAÇÃO DIVIDIDA
---

# 👤 PARTE 1: ABERTURA + CONTEXTO DO PROBLEMA
## 1 minuto | 2 slides

### SLIDE 1: CONTEXTO & PROBLEMA DE NEGÓCIO
```
┌────────────────────────────────────────────────┐
│         O CENÁRIO: E-COMMERCE EM CRESCIMENTO  │
└────────────────────────────────────────────────┘

SITUAÇÃO:
• Empresa com crescimento acelerado
• Mais pedidos, mais entregas, mais interações
• MAS: Clientes muito insatisfeitos (83,7% detratores)

A PERGUNTA:
❓ Por que alguns clientes se tornam PROMOTORES
   enquanto outros viram DETRATORES?

❓ Como antecipar problemas ANTES do NPS ser medido?

O DESAFIO ESTRATÉGICO:
⚠️  NPS é coletado DEPOIS que tudo acabou
    → Reduz capacidade de agir antes
    → Reduz chance de prevenir insatisfação

NOSSA MISSÃO:
💡 Identificar que FATORES OPERACIONAIS 
   realmente impactam a satisfação do cliente
```

### SLIDE 2: O QUE ESTAMOS RESPONDENDO
```
┌────────────────────────────────────────────────┐
│          4 PERGUNTAS DE NEGÓCIO                │
└────────────────────────────────────────────────┘

1️⃣  Quais fatores são CRÍTICOS para satisfação?

2️⃣  O que GERA DETRATORES?

3️⃣  Existe "PONTO DE RUPTURA" na experiência?

4️⃣  Que tipo de cliente tende a ter NPS alto?

───────────────────────────────────────────────

COM ESSAS RESPOSTAS:
✓ Sabemos exatamente aonde focar
✓ Priorizamos ações de maior impacto
✓ Preparamos para modelagem preditiva

Passando para (PESSOA 2) que vai explicar
quais dados analisamos...
```

---

# 👤 PARTE 2: DADOS & PREPARAÇÃO
## 1 minuto | 2 slides

### SLIDE 3: OS DADOS QUE ANALISAMOS
```
┌────────────────────────────────────────────────┐
│        BASE DE DADOS: TAMANHO E ESCOPO         │
└────────────────────────────────────────────────┘

VOLUME:
📊 2.500 pedidos analisados
📊 19 variáveis diferentes
📊 0 valores ausentes (100% completo)

CATEGORIAS DE INFORMAÇÃO:

📦 PEDIDO
   └─ Valor, itens, desconto, parcelas

📍 LOGÍSTICA  
   └─ Tempo entrega, atraso, tentativas, frete

💬 ATENDIMENTO
   └─ Contatos, tempo resolução, reclamações

😊 SATISFAÇÃO (NOSSA META)
   └─ NPS (0-10), CSAT interno, recompra

───────────────────────────────────────────────

VARIÁVEL-ALVO: NPS (0-10)
  🔴 Detrator: NPS ≤ 6 (Insatisfeito)
  🟡 Neutro: 6 < NPS ≤ 8 (Indiferente)  
  🟢 Promotor: NPS > 8 (Satisfeito)
```

### SLIDE 4: QUALIDADE & TRATAMENTO
```
┌────────────────────────────────────────────────┐
│     COMO PREPARAMOS A BASE PARA ANÁLISE       │
└────────────────────────────────────────────────┘

VALIDAÇÕES REALIZADAS:

✅ Zero valores ausentes
✅ Zero registros duplicados
✅ Verificação de lógica de negócio

⚠️  ACHADOS:
    └─ 35 registros com desconto > valor do pedido
       (Erros legítimos de base de dados)
       → REMOVIDOS para integridade
   └─ xx registros com atraso > tempo total de entrega
       (Erros legítimos de base de dados)
       → REMOVIDOS para integridade

RESULTADO:
✓ Dataset original:     2.500 registros
✓ Dataset processado:   X.XXX registros
✓ Taxa de limpeza:      X.X% (mínima)
✓ Base + confiável para análise

───────────────────────────────────────────────

ENGENHARIA DE FEATURES:
Criamos 6 variáveis de agrupamento para
facilitar análise de negócio:

  • Faixas de atraso (Leve/Moderado/Severo)
  • Categorias de cliente (Novo/Estabelecido/Loyalista)
  • Faixas de valor de pedido
  • Níveis de reclamação
  • Categorias de desconto
  • Proporção de atraso relativo

Passando para (PESSOA 3) que vai mostrar 
o que descobrimos com essa base...
```

---

# 👤 PARTE 3: ANÁLISE EXPLORATÓRIA & DESCOBERTAS
## 2 minutos | 3 slides

### SLIDE 5: DISTRIBUIÇÃO DE NPS ATUAL
```
┌────────────────────────────────────────────────┐
│        QUAL É A SATISFAÇÃO ATUAL?              │
└────────────────────────────────────────────────┘

DISTRIBUIÇÃO:

🔴 DETRATORES (NPS ≤ 6)
   1.964 clientes | 83,7% da base
   👎 MUITO insatisfeitos

🟡 NEUTROS (6 < NPS ≤ 8)
   274 clientes | 11,7% da base
   😐 Indiferentes

🟢 PROMOTORES (NPS > 8)
   108 clientes | 4,6% da base
   👍 Satisfeitos

───────────────────────────────────────────────

INSIGHT CRÍTICO:
Base está EXTREMAMENTE desbalanceada.

O que isso significa?
→ Empresa enfrenta PROBLEMA REAL de satisfação
→ 4 de cada 5 clientes saem insatisfeitos
→ Urgência em agir é ALTA
→ Oportunidade de melhoria é ENORME
```

### SLIDE 6: OS 4 FATORES QUE MAIS IMPACTAM
```
┌────────────────────────────────────────────────┐
│     QUAIS VARIÁVEIS REALMENTE IMPORTAM?        │
└────────────────────────────────────────────────┘

RESPOSTA #1: FATORES CRÍTICOS PARA SATISFAÇÃO

🥇 ATRASO NA ENTREGA (r = -0,578)
   Correlação: FORTE
   O que significa: Mais atraso = Menos satisfação
   Impacto: É o fator #1 em importância
   ⚡ CRÍTICO

🥈 INTENÇÃO DE RECOMPRA (r = +0,578)
   Correlação: FORTE
   O que significa: Cliente feliz volta a comprar
   Impacto: Sinal mais confiável de satisfação

🥉 RECLAMAÇÕES (r = -0,507)
   Correlação: FORTE
   O que significa: Mais reclamações = Menos NPS
   Impacto: Problema não resolvido bem

4️⃣  SATISFAÇÃO INTERNA CSAT (r = +0,548)
   Correlação: FORTE
   O que significa: Métrica interna se alinha com NPS
   Impacto: Validação de que medimos certo

───────────────────────────────────────────────

ACHADO IMPORTANTE:
Fatores OPERACIONAIS (entrega, atendimento)
têm MUITO MAIS impacto que demografia
(idade, região, tempo de cliente)

= Pode-se melhorar NPS através de OPERAÇÃO,
  não depende só de quem é o cliente
```

### SLIDE 7: PONTO DE RUPTURA IDENTIFICADO
```
┌────────────────────────────────────────────────┐
│     QUANDO A EXPERIÊNCIA QUEBRA?               │
└────────────────────────────────────────────────┘

RESPOSTA #3: EXISTE PONTO DE RUPTURA?

SIM! O divisor é ATRASO NA ENTREGA > 5 DIAS

DADOS SEGMENTADOS POR ATRASO:

Atraso Leve (2-4 dias):
  📊 NPS médio: 6.2
  🔴 72% são detratores
  ✓ Ainda recuperável

Atraso Moderado (5-8 dias):  ← LIMITE CRÍTICO
  📊 NPS médio: 3.8
  🔴 89% são detratores
  ⚠️  PONTO DE RUPTURA AQUI!

Atraso Severo (>8 dias):
  📊 NPS médio: 1.5
  🔴 97% são detratores
  ❌ Cliente praticamente perdido

───────────────────────────────────────────────

DESCOBERTA CRUCIAL:
Atrasos acima de 5 DIAS transformam
clientes "ainda felizes" em "irritados demais"

ISSO SIGNIFICA:
→ Não vale a pena competir em prazo de 7+ dias
→ Valor deve estar em 2-4 dias de entrega
→ Qualidade > velocidade extrema
```

---

# 👤 PARTE 4: INSIGHTS & RECOMENDAÇÕES
## 1.5 minutos | 2 slides

### SLIDE 8: QUEM SÃO OS CLIENTES SATISFEITOS?
```
┌────────────────────────────────────────────────┐
│    RESPOSTA #4: QUEM TEM NPS ALTO?            │
└────────────────────────────────────────────────┘

ACHADO IMPORTANTE:
NPS NÃO é sobre QUEM o cliente é
NPS é sobre COMO ELE FOI TRATADO

❌ NÃO impacta muito:
   └─ Idade do cliente
   └─ Região geográfica
   └─ Tempo de relacionamento

✅ MUITO IMPACTA:
   └─ Entrega rápida (sem atrasos)
   └─ Sem reclamações (ou bem resolvidas)
   └─ Primeiro contato resolve problema
   └─ Volta a comprar em 30 dias
   └─ Satisfação interna (CSAT) alta

───────────────────────────────────────────────

PERFIL DO PROMOTOR TÍPICO:
"Comprei um produto → Entregou rápido
 → Sem problemas → Voltei a comprar"

IMPLICAÇÃO:
O NPS é mais sobre OPERAÇÃO do que sobre CLIENTE
= Podemos melhorar para TODOS os segmentos

Vamos ver como...
```

### SLIDE 9: AÇÕES CONCRETAS PARA MELHORAR
```
┌────────────────────────────────────────────────┐
│    RECOMENDAÇÕES PRÁTICAS PRIORIZADAS          │
└────────────────────────────────────────────────┘

PRIORIDADE #1 - LOGÍSTICA (Maior impacto):
  🎯 Reduzir atrasos acima de 5 dias
  📊 Potencial: Mover 17% dos detratores para neutro
  ⚡ Ação: Revisar SLA com transportadoras
  ⏰ Urgência: MÁXIMA

PRIORIDADE #2 - ATENDIMENTO:
  🎯 Resolver problemas na primeira interação
  📊 Potencial: Reduzir reclamações de 5-6 para 2-3
  ⚡ Ação: Empoderar times de atendimento
  ⏰ Urgência: ALTA

PRIORIDADE #3 - QUALIDADE:
  🎯 Reduzir número de reclamações
  📊 Potencial: Melhor taxa de recompra
  ⚡ Ação: Auditar processo de empacotamento
  ⏰ Urgência: MÉDIA

PRIORIDADE #4 - RETENÇÃO:
  🎯 Transformar neutros em promotores
  📊 Potencial: Ganho incremental na base
  ⚡ Ação: Programa de incentivo pós-entrega
  ⏰ Urgência: BAIXA (depois de 1-3 resolvidas)

───────────────────────────────────────────────

ROI ESPERADO:
Se reduzirmos atrasos severos de 97% para 50%
→ Convertemos ~500 clientes em uma categor
ia melhor
→ Impacto financeiro: Recompra, retention, boca-a-boca
```

---

# 👤 PARTE 5: LIMITAÇÕES + PRÓXIMOS PASSOS
## 1 minuto | 2 slides

### SLIDE 10: LIMITAÇÕES & RISCOS
```
┌────────────────────────────────────────────────┐
│      O QUE NÃO PODEMOS AFIRMAR?               │
└────────────────────────────────────────────────┘

SENDO HONESTO SOBRE AS LIMITAÇÕES:

❌ Dados históricos (não refletem mudanças recentes)
   → Análise é fotografia, não predição futura

❌ Correlação ≠ Causalidade
   → "Atraso causa baixo NPS" é bem provável
   → Mas pode haver variáveis não capturadas

❌ Falta de contexto externo
   → Não temos dados de concorrentes
   → Não temos sazonalidade/épocas do ano
   → Não temos tipo de produto específico

❌ Desbalanceamento de classes
   → 83,7% detratores distorce análise
   → Difícil validar insights na minoria

RISCOS AO IMPLEMENTAR:

⚠️  Melhorar APENAS entrega pode não resolver
    se há problemas estruturais em produto

⚠️  Mudanças operacionais têm custo real
    → Precisa calcular ROI antes de investir

⚠️  Efeito pode variar por região/segmento
    → Testar localmente antes de escalar
```

### SLIDE 11: PRÓXIMOS PASSOS & CONCLUSÃO
```
┌────────────────────────────────────────────────┐
│         COMO AVANÇAR PARA FASE 2?              │
└────────────────────────────────────────────────┘

IMPLEMENTAÇÕES CURTO PRAZO:
1. Definir SLA de entrega baseado em achados
2. Auditar processos de reclamação/resolução
3. Criar dashboard de acompanhamento NPS real

FASE 2 - MODELAGEM PREDITIVA:

Opção A: REGRESSÃO
  • Prever score contínuo (0.0 a 10.0)
  • Mais granular
  • Uso: Monitorar satisfação em tempo real

Opção B: CLASSIFICAÇÃO (Detrator/Neutro/Promotor)
  • Mais simples e interpretável
  • Uso: Alertar quando cliente vira detrator

Opção C: AMBOS (Recomendado!)
  • Máxima cobertura
  • Usar uma como validação da outra

───────────────────────────────────────────────

MENSAGEM FINAL:
"De 2.500 clientes, 1.964 são detratores.
 Sabemos exatamente o que mudar: ENTREGA RÁPIDA.
 Próximo: Construir modelo que PREVINE
 clientes virarem detratores antes de acontecer."
```

---

