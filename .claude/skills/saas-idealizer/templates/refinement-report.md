# Relatório de Refinement — `<Nome do projeto / nicho>`

**Data:** `<YYYY-MM-DD>`
**Fundador:** `<nome / contexto resumido>`
**Origem:** `<Discovery (Área N) | Ideia trazida pelo usuário>`

---

## Veredito

`SEGUIR` | `ITERAR` | `MATAR`

`<2–4 linhas de justificativa. Sem rodeios. Se SEGUIR: por que vence agora? Se ITERAR: o que precisa mudar e qual experimento decide? Se MATAR: qual é o risco mortal não-mitigável e que adjacente faria sentido investigar.>`

---

## Top 3 riscos mortais

1. **`<Risco>`** — `<por que mata, mitigação proposta, gatilho que decide se persistir ou não>`.
2. **`<Risco>`** — `<...>`.
3. **`<Risco>`** — `<...>`.

---

## ICP (1 frase comportamental)

`<Não-demográfica. Quem, em que contexto, fazendo o quê.>`

### Early adopter (subgrupo mais doloroso)
`<Recorte ainda mais fino dentro do ICP — a quem você vende primeiro.>`

---

## Jobs-to-be-done

> Quando `<circunstância específica disparada por evento>`, eu quero `<motivação funcional ou emocional>`, para que eu possa `<resultado mensurável>`.

**Forças de progresso (push + pull):** `<...>`
**Forças de retenção (hábito + ansiedade):** `<...>`

---

## Lean Canvas

| Bloco | Conteúdo |
|---|---|
| Problema | `<top 3 dores>` |
| Segmentos | `<ICP + early adopter>` |
| Proposta de valor única | `<promessa específica e mensurável>` |
| Solução | `<top 3 features que mapeiam às dores>` |
| Canais | `<canal Bullseye prioritário + 2 secundários>` |
| Receita | `<modelo + preço + LTV alvo>` |
| Estrutura de custo | `<CAC alvo, infra, suporte, fixos>` |
| Métricas-chave | `<3–5 KPIs operacionais — não vanity>` |
| Vantagem injusta | `<o que não pode ser comprado nem copiado>` |

---

## Features para o MVP

### IN — máximo 5
1. **`<Feature>`** — JTBD que resolve: `<...>`. Critério de pronto: `<...>`.
2. **`<Feature>`** — `<...>`
3. **`<Feature>`** — `<...>`
4. **`<Feature>`** — `<...>`
5. **`<Feature>`** — `<...>`

### CUT — explicitamente fora do MVP
- **`<Feature comum>`** — motivo: `<não está no caminho crítico do JTBD principal / pode ser feito manualmente / risco de scope creep>`.
- **`<Feature comum>`** — motivo: `<...>`.
- **`<Feature comum>`** — motivo: `<...>`.

> Regra: se o usuário propor reincluir uma feature do CUT, exigir evidência comportamental (ICP perguntou ou recusou pagar sem ela).

---

## Matriz de concorrentes

**Eixos do 2x2:** `<eixo X — ex.: Vertical especializado ↔ Horizontal genérico>` × `<eixo Y — ex.: Self-serve barato ↔ Enterprise alto-toque>`.

| Player | Posicionamento | Preço | Stack/headcount | Pontos fortes | Pontos fracos verificados (citações) |
|---|---|---|---|---|---|
| `<nome>` | `<quadrante>` | `<R$X/mês>` | `<...>` | `<...>` | `<reviews 1–3* citadas>` |
| ... | | | | | |

**Onde a proposta entra:** `<quadrante + por que esse espaço é defensável dada a vantagem injusta>`.

---

## Plano de monetização

- **Modelo:** `<assinatura mensal/anual / per-seat / usage-based / híbrido>`. Justificativa: `<...>`.
- **Tiers:**

| Tier | Preço mensal | Preço anual | Para quem | Limites/inclusões |
|---|---|---|---|---|
| `<Starter>` | `<R$X>` | `<R$Y (~17% off)>` | `<early adopter>` | `<...>` |
| `<Pro>` | `<R$X>` | `<R$Y>` | `<ICP principal>` | `<...>` |
| `<Business>` | `<R$X>` | `<R$Y>` | `<contas maiores / âncora>` | `<...>` |

- **Justificativa por valor:** cliente economiza/gera ~`<R$X>` ao mês; preço-alvo ~10% disso.

### Unit economics-alvo
- ARPU alvo: `<R$X>`.
- CAC máximo tolerável: `<R$Y>` (regra LTV:CAC ≥ 3:1).
- Payback period alvo: `<≤ 6 meses para indie>`.
- Churn mensal aceitável: `<≤ 3% B2B SMB / ≤ 2% mid-market>`.
- Gross margin alvo: `<≥ 75%>`.

---

## Plano de execução em 3 fases

### Fase 0 — Validação pré-build (`<2–6 semanas>`)

**Objetivo:** decidir com dados se vale construir.

**Experimentos:**
1. `<X entrevistas com ICPs do early adopter>` — meta: ≥ 5; critério de sucesso: ≥ 3 já pagam por alternativa.
2. `<Landing + waitlist com proposta clara e preço visível>` — meta: ≥ 50 inscritos qualificados em 30 dias.
3. `<Pré-venda concierge>` — meta: ≥ 1 cliente pagante (mesmo manualmente atendido).

**Critério de Go para Fase 1:** `<combinação clara dos resultados acima>`.
**Critério de No-Go (matar ou pivotar):** `<...>`.

### Fase 1 — MVP cobrável (`<4–10 semanas>`)

**Escopo congelado:** as 3–5 features IN acima. Nada além.

**Definição de pronto:**
- Stripe/Pagar.me ativo, primeira cobrança real ocorrida.
- 1 cliente em produção pagando (idealmente o concierge da Fase 0 migrado).
- Dashboard mínimo de uso para conversas com cliente.

**Stack sugerida:** `<respeitando D1 do usuário>`.
**Anti-stack:** `<o que NÃO usar — microsserviços, K8s, multi-tenant complexo, etc.>`.

### Fase 2 — Tração (`<3–6 meses>`)

**Foco único:** canal Bullseye prioritário `<...>`.
**Métricas-alvo no fim do período:**
- MRR: `<R$X>`.
- Clientes pagantes: `<N>`.
- Retenção D90: `<≥ Y%>`.
- NPS: `<≥ 30>`.

**Ponto de decisão (mês `<N>`):**
- Se métricas batidas → escalar canal vencedor, abrir tier superior.
- Se 50–80% das metas → iterar produto/posicionamento por mais 90 dias.
- Se < 50% → encerrar ou pivotar para adjacente identificado.

---

## Experimentos de validação imediata (esta semana)

1. **`<Ação>`** — entregável: `<...>`. Critério de sucesso: `<número objetivo>`.
2. **`<Ação>`** — `<...>`.
3. **`<Ação>`** — `<...>`.
4. **`<Ação>`** — `<...>`.
5. **`<Ação>`** — `<...>`.

---

## Pontos abertos / hipóteses não resolvidas

`<Liste honestamente o que ainda não foi provado e que o fundador precisa investigar antes de comprometer capital significativo. Inclua fontes a checar e perguntas sem resposta.>`

---

## Anexos
- `<Links de evidência citados ao longo do relatório.>`
- `<Lista de ICPs entrevistados, datas, principais quotes.>`
- `<Lista de concorrentes pesquisados, com link e data de captura.>`
