# Frameworks de referência — saas-idealizer

Conteúdo destilado de obras canônicas. Citado ao longo de SKILL.md. Não é doutrina cega — é vocabulário comum para análise rigorosa.

---

## Lean Canvas

Adaptação por Ash Maurya (*Running Lean*) do Business Model Canvas para startups. Nove blocos, preencher em 1–2 linhas cada:

1. **Problema** — top 3 dores do ICP. Inclua "alternativas existentes" (o que ele faz hoje).
2. **Segmentos de cliente** — ICP em 1 frase comportamental + early adopter (subgrupo mais doloroso).
3. **Proposta de valor única** — promessa específica e mensurável, não slogan.
4. **Solução** — top 3 features que resolvem os 3 problemas. Não a lista completa do produto.
5. **Canais** — caminho até o cliente (orgânico, parceria, cold outbound, conteúdo, marketplace).
6. **Fluxo de receita** — modelo + preço + LTV alvo.
7. **Estrutura de custo** — CAC, infra, suporte, custos fixos.
8. **Métricas-chave** — 3–5 métricas que provam se o motor está funcionando (não vanity metrics).
9. **Vantagem injusta** — algo que não pode ser facilmente comprado ou copiado (rede, marca, dado, expertise vertical, comunidade, distribuição).

**Heurística:** se o bloco "vantagem injusta" estiver vazio ou genérico ("equipe foda"), o projeto provavelmente não tem fosso. Investigue antes de seguir.

---

## Jobs To Be Done (JTBD)

Clayton Christensen + Bob Moesta. Pessoas não compram produtos — "contratam" produtos para fazer um progresso em uma circunstância específica.

**Formato canônico:**
> Quando *[circunstância]*, eu quero *[motivação]*, para que eu possa *[resultado esperado]*.

Exemplo: *"Quando recebo uma demanda fiscal urgente de cliente PJ, quero conferir todas as obrigações pendentes em até 5 minutos, para que eu possa responder antes da multa cair."*

**Diagnóstico de JTBD bem feito:**
- A circunstância é específica e disparada por evento, não por demografia.
- A motivação é funcional ou emocional — não "ter o produto X".
- O resultado é mensurável.
- Existem **forças de progresso** (push da situação, pull da nova solução) e **forças de retenção** (hábito atual, ansiedade de mudança). Mapeá-las.

**Anti-padrão:** "JTBD" formulado como feature ("quero um dashboard de métricas") em vez de progresso ("quero saber se vou bater meta antes do dia 25 do mês").

---

## Mom Test

Rob Fitzpatrick. Como conduzir entrevistas de cliente sem coletar mentiras educadas.

**Três regras:**
1. Fale da **vida deles**, não da sua ideia.
2. Pergunte sobre **comportamento passado específico**, não opiniões ou hipóteses futuras.
3. Fale **menos**, escute mais.

**Perguntas que mentem (evitar):**
- "Você usaria um produto que…?" → resposta polida, sem valor.
- "Quanto pagaria por…?" → número fantasioso.
- "Acha que essa ideia é boa?" → o entrevistado vira torcedor.

**Perguntas que extraem evidência:**
- "Conta da última vez que você teve esse problema. O que aconteceu?"
- "O que você fez para resolver? Quanto tempo gastou? Quanto custou?"
- "Quem mais na sua empresa/vida sente isso? Como você sabe?"
- "Você já pagou para resolver isso? Para quem? Quanto? Continua pagando?"
- "O que te impediu de resolver isso até hoje?"

**Sinais de validação real:**
- Entrevistado dá tempo de qualidade (resposta de 5+ minutos com detalhes específicos).
- Apresenta outras pessoas com o mesmo problema sem ser pedido.
- Pede para ser avisado quando estiver pronto, ou pergunta preço.
- Já gasta tempo/dinheiro no problema atualmente.

**Sinais de falsa validação ("compliments"):**
- "Adorei a ideia."
- "Eu compraria."
- "Isso seria muito útil."
- "Você devia falar com X."

Recuse esses como evidência. Eles são ruído social.

---

## Unit Economics SaaS

Métricas mínimas para sanidade financeira:

- **MRR** — Monthly Recurring Revenue. Receita recorrente normalizada por mês.
- **ARR** — MRR × 12.
- **CAC** — Customer Acquisition Cost. Total gasto em aquisição ÷ novos clientes no período.
- **LTV** — Lifetime Value. ARPU × margem bruta ÷ churn mensal. Para SaaS B2B saudável: LTV > 3 × CAC.
- **Churn mensal** — clientes perdidos / clientes no início do mês. SaaS B2B saudável: < 2%/mês. SMB: 3–5%. B2C: 5–10%.
- **Payback period** — meses para recuperar CAC. Indie/bootstrap saudável: < 6 meses. VC-backed: < 12.
- **ARPU** — Average Revenue Per User.
- **Gross margin** — receita − custos variáveis (infra, payment, suporte direto). SaaS deve estar > 70%.

**Heurística para micro-SaaS bootstrap:**
- Preço mínimo viável: **$20–50/mês** para B2C indie, **$50–500/mês** para B2B SMB. Abaixo disso, CAC mata.
- Evite freemium puro sem upgrade óbvio — drena suporte e infra sem retorno.
- Anual com desconto (~2 meses grátis) reduz churn percebido e melhora cash.

---

## Bullseye — 19 canais de traction

Gabriel Weinberg, *Traction*. Para um produto cedo, listar todos os canais e priorizar:

1. Targeting blogs
2. Publicity (PR)
3. Unconventional PR (stunts)
4. SEM (search ads)
5. Social and display ads
6. Offline ads
7. SEO
8. Content marketing
9. Email marketing
10. Engineering as marketing (free tools)
11. Targeting blogs (refinado por nicho)
12. Business development (parcerias)
13. Sales (outbound)
14. Affiliate programs
15. Existing platforms (App Store, marketplaces, plugins)
16. Trade shows
17. Offline events
18. Speaking engagements
19. Community building

**Processo:**
- **Outer ring** — listar hipótese para cada canal.
- **Middle ring** — escolher 3 mais promissores; rodar testes baratos (~ $100–500).
- **Inner ring (bullseye)** — focar 80% do esforço no canal vencedor.

**Heurística:** o canal certo geralmente é **não óbvio** — concorrente já saturou os óbvios. Procure canal subexplorado pelo mainstream do nicho.

---

## Modelos de pricing

| Modelo | Quando usa | Risco principal |
|---|---|---|
| Flat assinatura mensal | Valor previsível, uso uniforme | Underprice se uso variar muito |
| Tiered (Good/Better/Best) | Valor escala com sofisticação | Complexidade de empacotamento |
| Per-seat | B2B com colaboração | Cliente esconde usuários para economizar |
| Usage-based (consumption) | Custo variável alto (API, infra, IA) | Receita imprevisível, ansiedade de fatura |
| Híbrido (base + uso) | Combina previsibilidade e upside | Modelagem complexa |
| Anual com desconto | Reduzir churn, melhorar cash | Refunds, reduz flexibilidade |
| Freemium | Aquisição viral, classes de uso bem separadas | Drena suporte, baixa conversão (~2–5%) |
| Free trial 14d/30d | Produto "experiencial", time-to-value < trial | Trial sem ativação = lead morto |

**Princípios de precificação por valor:**
- Preço deve ser ≤ 10% do valor entregue mensurável ao cliente. Se cliente economiza $1.000/mês, preço-alvo ~$100/mês.
- Tier mais barato deve ser **escolha óbvia para o ICP principal** — não isca.
- Tier mais caro existe para "ancorar" o tier do meio (efeito-âncora) e capturar enterprise.
- Sempre mostre **anual** ao lado de mensal, com desconto de ~16–20% (dois meses).
- Evite preço terminado em 9. Use números cheios — sinaliza B2B sério.

---

## Priorização de features (RICE)

Quando houver mais features do que MVP suporta:

**RICE = (Reach × Impact × Confidence) / Effort**

- **Reach** — quantos ICPs afetados por mês.
- **Impact** — magnitude por cliente (1=mínimo, 3=alto).
- **Confidence** — % de certeza nas estimativas.
- **Effort** — pessoas-semana.

Use como organizador de discussão, não como verdade absoluta. Para MVP, regra simples: incluir só features sem as quais o cliente não pagaria. Tudo mais → backlog "Fase 2".

---

## Sinais de Product-Market Fit

- **Sean Ellis Test** — pergunte aos usuários ativos: "Como se sentiria se não pudesse mais usar este produto?". PMF quando ≥ 40% respondem "muito desapontado".
- **Retenção D30/D90 estabilizada** — curva de retenção achata em platô não-zero.
- **NPS > 30** em B2B SMB; > 50 é excelente.
- **Demanda orgânica** — clientes chegam sem você empurrar (referral, busca direta, boca a boca).
- **Churn voluntário < 2%/mês** consistente.

Antes de PMF: foco em conversas e iteração. Não escalar marketing.
