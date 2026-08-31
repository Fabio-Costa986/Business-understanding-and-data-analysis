# Análise e Previsão de NPS - Fase 1

**Um projeto abrangente de análise de dados para entender e prever o Net Promoter Score (NPS) utilizando a metodologia CRISP-DM.**

---

## Índice

- [Visão Geral](#visão-geral)
- [Equipe](#equipe)
- [Escopo do Projeto](#escopo-do-projeto)
- [Resumo dos Dados](#resumo-dos-dados)
- [Principais Descobertas](#principais-descobertas)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Metodologia](#metodologia)
- [Qualidade dos Dados](#qualidade-dos-dados)
- [Como Reproduzir](#como-reproduzir)
- [Próximos Passos](#próximos-passos)

---

## Visão Geral

Este projeto conduz a **fase de compreensão de negócio e análise de dados** de uma iniciativa de previsão de NPS. A análise se concentra em entender os padrões de satisfação do cliente, identificar fatores críticos que afetam o NPS e preparar dados para modelagem preditiva.

**Objetivos:** Responder a quatro perguntas-chave de negócio:
1. Quais fatores são mais críticos para a satisfação do cliente?
2. O que gera detratores (NPS baixo)?
3. Existem "pontos de ruptura" na experiência do cliente?
4. Que tipos de cliente tendem a ter NPS mais alto ou mais baixo?

---

## Equipe

- Amanda Alves de Lima Santos - RM 376932
- Fábio da Silva Costa - RM 376887
- Gabriel Victor Santos Oliveira - RM 376713
- Vanessa Partala - RM 376277
- Humberto Henrique Alves Moreira dos Santos - RM 377025

---

## Escopo do Projeto

**Metodologia:** CRISP-DM (Processo Padrão Entre Indústrias para Mineração de Dados)

**Fase Atual:** Compreensão de Negócio, Preparação de Dados e Análise Exploratória

**Dados de Entrada:** `data/desafio_nps_fase_1.csv`

**Dados de Saída:**
- `data/processed/nps_tratado.csv` - Dataset limpo e processado
- `data/processed/nps_registros_rejeitados.csv` - Registros que falharam nas validações de qualidade

---

## Resumo dos Dados

### Características do Dataset

| Métrica | Valor |
|---------|-------|
| **Total de Registros** | 2.500 |
| **Total de Colunas** | 19 |
| **Unidade de Análise** | Pedido (identificado por `order_id`) |
| **Intervalo de Datas** | Requer verificação nos dados |
| **Valores Ausentes** | Nenhum detectado |

### Distribuição de Tipos de Dados

| Tipo | Quantidade | Detalhes |
|------|-----------|----------|
| **Colunas Inteiras** | 13 | Idade, NPS, contagens, sinalizadores |
| **Colunas Decimais** | 5 | Métricas financeiras, percentuais |
| **Categóricas** | 1 | `customer_region` (5 categorias) |

### Variáveis-Chave

| Variável | Tipo | Intervalo/Categorias | Notas |
|----------|------|----------------------|-------|
| `nps_score` | Decimal | 0-10 | Contém valores decimais; variável alvo principal |
| `customer_age` | Inteira | 18-69 anos | Variável de segmentação demográfica |
| `customer_region` | Categoria | 5 regiões | Segmentação geográfica |
| `order_id` | Inteira | 2.500 únicos | Identificador primário |
| `customer_id` | Inteira | 2.500 únicos | Identificador do cliente |
| `delivery_delay_days` | Inteira | 2-14 dias | Métrica operacional crítica |
| `complaints_count` | Inteira | Variável | Indicador de satisfação do cliente |
| `csat_internal_score` | Decimal | 0-10 | Métrica de satisfação interna |
| `repeat_purchase_30d` | Binária | Sim/Não | Indicador de intenção de recompra |

---

## Principais Descobertas

### 1. Fatores Críticos para a Satisfação do Cliente

Classificados pela força de correlação com o Score NPS:

1. **Intenção de Recompra** (r = 0,578)
   - Clientes propensos a recomprar nos próximos 30 dias têm NPS significativamente mais alto
   - Forte indicador de que a experiência de compra influencia diretamente a satisfação

2. **Score CSAT Interno** (r = 0,548)
   - Relação consistente entre métricas internas de satisfação e NPS
   - Ambas as medições se alinham bem ao capturar satisfação

3. **Atrasos na Entrega** (r = -0,578)
   - Tempos de entrega mais longos correlacionam diretamente com NPS mais baixo
   - A eficiência operacional é crítica para a satisfação do cliente

4. **Reclamações de Clientes** (r = -0,507)
   - Contagens mais altas de reclamações predizem fortemente NPS mais baixo
   - A capacidade de resolução impacta a satisfação do cliente

### 2. Perfil de Detratores

Detratores (NPS ≤ 6) representam **83,7% da base de clientes** e são caracterizados por:
- Frequência maior de atrasos na entrega
- Taxas aumentadas de reclamações
- Menor intenção de recompra
- Scores CSAT internos mais baixos

### 3. Distribuição de NPS e Classificação

| Categoria | Quantidade | Percentual | Intervalo NPS |
|-----------|-----------|-----------|---------------|
| **Detratores** | 1.964 | 83,7% | 0-6 |
| **Neutros** | 274 | 11,7% | 6,1-8 |
| **Promotores** | 108 | 4,6% | 8,1-10 |

**Insight:** Desbalanceamento severo de classes com maioria de detratores. 

### 4. Insights Demográficos

- Variações regionais, baseadas em idade e comprimento de relacionamento mostram **impacto mínimo** no NPS
- **Fatores operacionais** (atrasos, reclamações) são mais determinantes que dados demográficos
- Tempo de cliente mostra que 42% da base tem 72+ meses de relacionamento

### 5. Avaliação de Qualidade dos Dados

- **Nenhum registro completamente duplicado** identificado
- **Nenhum valor ausente** em todos os 2.500 registros
- **Nenhuma categoria inválida** ou valores fora do intervalo
- Todas as regras de qualidade passaram sem violações críticas
- Algumas anomalias sinalizadas para investigação durante análise exploratória

---

## Estrutura do Projeto

```
Business-understanding-and-data-analysis/
│
├── README.md                           # Visão geral do projeto (este arquivo)
├── data/
│   ├── desafio_nps_fase_1.csv         # Dataset original (entrada)
│   └── processed/
│       ├── nps_registros_rejeitados.csv # Registros que falharam nas validações
        ├── nps_tratado.csv              # base tratada sem os registros marcados como inconsistentes
│
├── notebook/
│   ├── 01_tratamento_dados.ipynb      # Preparação e limpeza dos dados
│   ├── 02_eda.ipynb                   # Análise Exploratória de Dados
│   └── old/                           # Versões anteriores dos notebooks
│
├── reports/
│   ├── 1IAST - Fase 1 - Tech Challenge.pdf # Relatório técnico da Fase 1
│   ├── Entendimento_negocio_target.md     # Documentação de compreensão de negócio
│   ├── insights_eda.md                    # Insights da análise exploratória
│   ├── Roadmap.md                         # Planejamento dos próximos passos
│   └── SLIDES_TECH_CHALLENGE_DIVIDIDO.md  # estrutura dos slides da apresentação
│
└── .claude/
    └── skills/
        └── eda-skill.md               # Instruções de IA para colaboração
```

---

## Metodologia

### Fases CRISP-DM Aplicadas

#### Fase 1: Compreensão de Negócio ✓
- Análise de contexto: Framework de medição de satisfação do cliente
- Definição de objetivo: Identificar direcionadores de NPS e preparar para previsão
- Revisão bibliográfica: Classificação padrão de NPS (Detrator/Neutro/Promotor)

#### Fase 2: Preparação de Dados ✓
- Carregamento e reconhecimento de estrutura
- Diagnósticos de qualidade (valores ausentes, duplicatas, consistência)
- Validação de regras de negócio (regras de domínio)
- Engenharia de características: Variáveis de agrupamento criadas
  - Intervalos de tempo de entrega
  - Faixas de tempo de relacionamento
  - Faixas de valor do pedido
  - Intervalos de frequência de reclamações
  - Categorias de percentual de desconto
  - Categorias de percentual de atraso na entrega

#### Fase 3: Análise Exploratória de Dados ✓
- Análise de correlação entre variáveis e NPS
- Comparações categóricas entre segmentos
- Análise de distribuição
- Identificação de fatores críticos

---

## Qualidade dos Dados

### Resultados de Validação de Qualidade

✅ **Verificações Aprovadas:**
- Nenhum valor ausente em nenhuma coluna
- Nenhum registro completamente duplicado
- Nenhum valor `order_id` repetido
- Nenhum valor `customer_id` repetido
- Todos os scores NPS dentro do intervalo 0-10
- Todas as idades dentro de limites razoáveis (18-69)
- Todas as categorias são válidas

### Framework de Regras de Qualidade

**Regras Críticas** (rejeição de registro):
- Valores de categoria inválidos
- Valores NPS, idade ou valores financeiros fora do intervalo
- Inconsistências lógicas

**Regras de Atenção** (registro sinalizado, não rejeitado):
- Combinações incomuns, mas possíveis
- Marcadas para investigação na análise exploratória

---

## Como Reproduzir

### Pré-requisitos

```bash
# Bibliotecas Python necessárias (instaladas no ambiente do notebook)
- pandas: Manipulação e análise de dados
- numpy: Operações numéricas
- matplotlib & seaborn: Visualização de dados
- scipy: Análise estatística
```

### Passos para Executar

1. **Navegue até o diretório do projeto**
   ```bash
   cd Business-understanding-and-data-analysis
   ```

2. **Abra os notebooks em sequência**
   ```bash
   # Primeiramente: Preparação de Dados
   jupyter notebook notebook/01_tratamento_dados.ipynb
   
   # Em seguida: Análise Exploratória
   jupyter notebook notebook/02_eda.ipynb
   ```

3. **Execute as células sequencialmente**
   - Comece com `01_tratamento_dados.ipynb` para preparar e validar os dados
   - Prossiga com `02_eda.ipynb` para explorar e responder as perguntas de negócio
   - Os resultados são reproduzíveis com os mesmos dados de entrada

4. **Revise os resultados**
   - Verifique `data/processed/` para datasets gerados
   - Examine as visualizações nos notebooks
   - Revise as descobertas documentadas nas células markdown

### Notebooks Principais

| Notebook | Conteúdo Principal |
|----------|-------------------|
| **01_tratamento_dados.ipynb** | Carregamento, limpeza, validação de qualidade, engenharia de características (variáveis de agrupamento) e geração de dataset processado |
| **02_eda.ipynb** | Análise exploratória completa, correlações, comparações entre segmentos, distribuições, resposta às 4 perguntas de negócio e identificação de fatores-chave |

---

## Como Usar Este Repositório

### Para Cientistas de Dados/Analistas
1. Revise `02_eda.ipynb` para metodologia, análises e descobertas principais
2. Consulte `01_tratamento_dados.ipynb` para entender as transformações de dados
3. Use os dados em `data/processed/` para análises adicionais ou modelagem
4. Referencie `nps_registros_rejeitados.csv` para contexto de qualidade

### Para Stakeholders de Negócio
1. Comece com a seção "Principais Descobertas" deste README
2. Revise as visualizações em `02_eda.ipynb`
3. Verifique "Próximos Passos" para recomendações estratégicas
4. Consulte `reports/` para apresentações e documentação executiva

### Para Novos Membros da Equipe
1. Leia este README para contexto geral
2. Execute `01_tratamento_dados.ipynb` para entender a preparação de dados
3. Execute `02_eda.ipynb` para ver as análises exploratórias
4. Revise os documentos em `reports/` para resumos executivos e insights
5. Consulte `.claude/skills/eda-skill.md` para contexto de colaboração com IA

---

## Notas e Suposições

- **Classificação de NPS:** Adaptada do framework padrão para lidar com scores decimais
  - Detratores: ≤ 6,0
  - Neutros: 6,1 a 8,0
  - Promotores: > 8,0

- **Unidade de Análise:** Cada linha representa um pedido de um cliente

- **Estratégia de Dados Ausentes:** Nenhuma imputação realizada; todos os registros retidos pois nenhum valor estava ausente

- **Tratamento de Outliers:** Outliers sinalizados mas retidos; nenhum valor removido sem investigação

---

## Contato e Dúvidas

Para dúvidas sobre esta análise, favor contactar os membros da equipe do projeto listados acima.

**Última Atualização:** 31/08/2026  
**Fase:** 1 - Compreensão de Negócio e Análise de Dados  
**Status:** Análise Exploratória Completa - Pronto para Modelagem

---

**Licença:** FIAP Tech Challenge - Uso Interno Apenas

