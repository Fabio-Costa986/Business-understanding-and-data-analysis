# Roadmap — Tech Challenge Fase 1 | Case NPS Preditivo

**Equipe:** 5 integrantes  
**Início:** 29/07/2026 (quarta-feira)  
**Conteúdo pronto para revisão:** 28/08/2026 (sexta-feira)  
**Revisão + gravação do vídeo:** 29–30/08/2026 (fim de semana)  
**Entrega final:** **01/09/2026 (terça-feira)**

> **Premissa:** o grupo só consegue trabalhar à noite durante a semana e aos finais de semana.

---

# Visão Geral das Entregas

| Entrega | Onde entra no roadmap |
|----------|-----------------------|
| Repositório GitHub público (tratamento de dados, EDA, modelo opcional, README e estrutura) | Semanas 1–4 |
| Slides de storytelling gerencial | Semanas 3–5 |
| Vídeo executivo (até 5 min) | 29–30/08 |

---

# Decisão Importante

Logo no início, o grupo deve decidir se fará o **Item 4 (Modelo Preditivo)**.

Embora seja opcional, ele é **fortemente recomendado**, pois enriquece o storytelling e facilita responder ao requisito do vídeo sobre **como o modelo apoia decisões reais**.

Este roadmap considera que o modelo será desenvolvido.

---

# Papéis Sugeridos

Os papéis são rotativos (todos participam de tudo pelo menos uma vez).

| Papel | Responsabilidade |
|-------|------------------|
| **P1** | Líder técnico de dados |
| **P2** | Líder de EDA |
| **P3** | Líder de Modelagem |
| **P4** | Líder de Negócio / Storytelling |
| **P5** | Líder de Entrega / PM |

> As sessões de fim de semana são coletivas. As noites durante a semana são destinadas ao trabalho individual ou em dupla.

---

# Semana 1 (29/07–02/08)

## Objetivo

- Fechar os Itens 1 e 2 (conceituais)
- Criar a estrutura do repositório

## Durante a semana

### Kickoff

- Definir papéis
- Criar repositório GitHub
- Convidar integrantes
- Criar README
- Configurar Branch Protection (opcional)

### Estrutura do projeto

```text
data/
 ├── raw/
 └── processed/

notebooks/
models/
reports/

README.md
.gitignore
```

### Item 1 — Entendimento do Negócio

Responder:

- Problema de negócio
- Importância do NPS
- Áreas beneficiadas
- Impacto em recompra
- Boca a boca
- Market Share
- Indicadores complementares

### Item 2 — Definição da Target

Responder:

- Variável alvo (`nps_score`)
- Justificativa
- Momento de coleta
- Riscos de utilização

## Final de semana

- Revisão coletiva
- Finalizar itens 1 e 2
- Salvar em:

```text
reports/
└── 01_entendimento_negocio_target.md
```

### Primeira leitura técnica da base

Avaliar:

- Tipos de dados
- Valores nulos
- Duplicados
- Estatísticas descritivas

### Entregável

- Itens 1 e 2 concluídos
- Estrutura criada
- Base em:

```text
data/raw/
```

---

# Semana 2 (03/08–09/08)

## Objetivo

Tratamento completo da base.

## Notebook

```text
notebooks/
└── 01_tratamento_dados.ipynb
```

### Tratamentos

- Valores nulos
- Duplicados
- Tipos de dados
- Outliers
- Padronização de categorias
- Variáveis derivadas
- Classificação do NPS

Salvar base tratada em:

```text
data/processed/nps_tratado.csv
```

### README

Começar:

- Objetivo
- Descrição da base
- Metodologia
- Como reproduzir

### Final de semana

- Revisão coletiva
- Merge
- Planejamento da EDA

### Entregável

- Notebook finalizado
- Base tratada
- README iniciado

---

# Semana 3 (10/08–16/08)

## Objetivo

EDA completa com foco em negócio.

## Notebook

```text
notebooks/
└── 02_eda.ipynb
```

Responder:

1. Quais fatores mais impactam o NPS?
2. O que gera detratores?
3. Existe ponto de ruptura?
4. Qual perfil possui maior NPS?

Todos os gráficos devem conter interpretação em linguagem de negócio.

### Slides

Criar estrutura dos seis blocos obrigatórios.

### Final de semana

- Consolidar notebook
- Escolher 4–6 insights
- Criar:

```text
reports/
└── 02_eda_insights.md
```

### Checkpoint

Decidir oficialmente sobre o modelo preditivo.

### Entregável

- EDA concluída
- Insights definidos
- Primeira versão dos slides

---

# Semana 4 (17/08–23/08)

## Objetivo

Modelo preditivo.

## Notebook

```text
notebooks/
└── 03_modelo_preditivo.ipynb
```

### Definir

- Regressão
- Classificação
- Ou ambos

### Pipeline

- Variáveis
- Split treino/teste
- Modelos
- Avaliação
- Feature Importance

Salvar:

```text
models/
```

Métricas:

```text
reports/
```

### Slides

Adicionar:

- Importância das variáveis
- Recomendações
- Limitações

### Entregável

- Pipeline completa
- Slides 80%

---

# Semana 5 (24/08–28/08)

## Objetivo

Fechar absolutamente tudo.

### README

Finalizar:

- Objetivo
- Base
- Metodologia
- Reprodução

### Limpeza

- Código morto
- Comentários
- Padronização
- Execução completa

### Slides

Finalizar design.

### Checklist

Conferir consistência entre:

- GitHub
- Slides
- Vídeo

### Entregável

- GitHub pronto
- README completo
- Slides finalizados
- Roteiro do vídeo

---

# Final de Semana (29–30/08)

## Objetivo

Gravar vídeo.

### Sábado

- Ensaio
- Gravações
- Revisão do GitHub
- Revisão dos slides

### Domingo

- Edição
- Revisão ortográfica
- Checklist

### Segunda (31/08)

Buffer para imprevistos.

### Terça (01/09)

Entrega final.

Enviar:

- Link GitHub
- Slides
- Vídeo

---

# Checklist

## GitHub

- [ ] Item 1
- [ ] Item 2
- [ ] Item 3
- [ ] Item 4 (opcional)
- [ ] Código organizado
- [ ] Variáveis padronizadas
- [ ] Comentários
- [ ] Estrutura de pastas
- [ ] README
- [ ] Projeto reproduzível
- [ ] Repositório público

---

## Slides

- [ ] Contexto
- [ ] Pergunta de negócio
- [ ] Insights
- [ ] Fatores críticos
- [ ] Recomendações
- [ ] Limitações
- [ ] Linguagem executiva

---

## Vídeo

- [ ] Até 5 minutos
- [ ] Pelo menos um apresentador
- [ ] Linguagem executiva
- [ ] Problema
- [ ] Solução
- [ ] Insights
- [ ] Como o modelo apoia decisões reais

---

# Dicas

- Não criar conteúdo novo depois de **28/08**.
- Fazer peer review em todas as entregas.
- Gravar o vídeo com antecedência.
- Manter **31/08** como buffer.
- Agendar uma conversa com os professores durante a Semana 2 ou 3.