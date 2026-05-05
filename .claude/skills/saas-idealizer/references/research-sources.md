# Fontes de pesquisa — saas-idealizer

Onde caçar evidência comportamental real, não opinião. Use sempre `WebSearch`/`WebFetch` para buscar fontes vivas; cite link e data. Se uma alegação não tem fonte verificável, marque como "não verificado".

## Sinal de dor real (qualitativo)

| Fonte | O que extrair | Como buscar |
|---|---|---|
| **Reddit** (subreddits do nicho) | Threads "what tool do you use for…", "anyone else hate…", "best alternative to X" | `site:reddit.com/r/<sub> "<problema>"` ou busca interna |
| **Indie Hackers** | Posts de fundadores no espaço, milestones de MRR, post-mortems | `site:indiehackers.com "<nicho>"` |
| **Hacker News** | "Show HN" do espaço, comentários em "Ask HN" sobre dor | `site:news.ycombinator.com "<nicho>"` |
| **X/Twitter** | Builder threads, "wish there was a tool that…", queixas públicas | Busca por palavras-chave + filtro "Latest" |
| **Fóruns de nicho** | Conselhos profissionais (OAB, CRC, CRM), comunidades verticais | Pesquisar fórum específico do setor |
| **YouTube comentários** | Tutoriais que ICP assiste — comentários revelam dores | Vídeos com 50k+ views no nicho |
| **Reviews 1–3 estrelas** em G2/Capterra/Trustpilot | Queixas específicas dos incumbentes — gold para gap analysis | `site:g2.com "<concorrente>" reviews` |
| **App Store / Play Store** | Reviews de apps adjacentes; mesma técnica | Filtrar por reviews recentes negativas |

**Regra:** nada vale como evidência se não tiver pelo menos 5 ocorrências independentes do mesmo padrão de dor.

## Sinal de demanda quantitativa

| Fonte | O que mostra |
|---|---|
| **Google Trends** | Curva de interesse por termo ao longo do tempo, geografia |
| **Exploding Topics** | Termos com crescimento acelerado |
| **Ahrefs / SEMrush / Ubersuggest** (free tier) | Volume de busca mensal, dificuldade SEO |
| **Reddit metrics / Subreddit stats** | Tamanho da comunidade, posts/dia |
| **Statista, IBGE, Sebrae, OECD** | Dados macro de mercado |
| **LinkedIn Sales Navigator** (busca livre) | Headcount estimado de ICP por categoria/geografia |
| **Crunchbase / Pitchbook** | Funding em concorrentes — sinal de capital chegando |

## Concorrentes e tração

| Fonte | Uso |
|---|---|
| **G2 / Capterra / SoftwareSuggest** | Listar players, ler reviews, comparar tiers |
| **Product Hunt** (histórico) | Launches no espaço — quem tentou, quem morreu, quem cresceu |
| **AlternativeTo.net** | Mapeamento de alternativas a um produto-âncora |
| **Indie Hackers — produtos públicos** | MRR auto-reportado de bootstrappers do nicho |
| **BuiltWith / Wappalyzer** | Stack tecnológico de concorrentes (sinaliza maturidade) |
| **SimilarWeb** | Tráfego estimado de concorrentes (free tier limitado, mas serve para ordenação) |
| **LinkedIn da empresa** | Headcount, contratações recentes (sinal de área que está apostando) |
| **Wayback Machine** | Pricing histórico — mudanças revelam estratégia |
| **Reddit + "scam" / "alternative"** | Frustração ativa com incumbente = oportunidade |

## Validação de pricing

| Fonte | Uso |
|---|---|
| **Pricing pages de concorrentes** | Range de mercado, empacotamento padrão |
| **Wayback Machine sobre pricing pages** | Como concorrentes ajustaram preço — sinaliza elasticidade |
| **G2 reviews mencionando preço** | "Acho caro/barato" comportamental |
| **Pré-venda landing** | Cobrar antes de construir — única validação real de WTP |

## Regulação e barreiras

| Nicho típico | Verificar |
|---|---|
| Saúde | LGPD-Saúde, ANVISA, CFM, ISO 27799, dados sensíveis |
| Financeiro | Bacen, CVM, PIX/Open Finance, KYC/AML |
| Jurídico | OAB (publicidade), sigilo profissional |
| Educação | MEC, LDB, parcerias com IES |
| Trabalhista/RH | CLT, eSocial, LGPD |
| Tributário | Receita Federal (NF-e, SPED, EFD) |
| Pagamentos | PCI-DSS, adquirentes, sub-acquiring |
| Internacional (EUA) | HIPAA (saúde), SOC 2, GDPR (UE) |

**Heurística:** se o nicho tem regulação pesada e o usuário não tem expertise legal nem capital para compliance, **vire o jogo** — recomende um adjacente menos regulado.

## Distribuição (canais Bullseye específicos)

| Canal | Fonte para mapear |
|---|---|
| SEO | Ahrefs/SEMrush para keywords longas do nicho |
| Comunidades | Reddit, Discord, Slack workspaces, fóruns verticais |
| Marketplaces | Shopify App Store, Notion, Slack, Atlassian, WordPress, etc. |
| Parcerias | Influenciadores B2B do nicho (LinkedIn, YouTube de nicho) |
| Cold outbound | Apollo, Hunter, LinkedIn Sales Navigator |
| Conteúdo | Substacks/newsletters do nicho com 5k+ assinantes |
| Eventos | Calendários setoriais, associações profissionais |

## Templates de busca rápidos

```
"<problema>" site:reddit.com
"<concorrente>" site:g2.com reviews
"<nicho>" site:indiehackers.com
"<problema>" intitle:"alternative to"
"<termo>" site:news.ycombinator.com
"how do you handle <problema>" site:reddit.com
```

## O que NÃO usar como evidência

- Posts de marketing dos próprios concorrentes (podem inflar números).
- "Pesquisa de mercado" de consultorias com paywall sem amostra divulgada.
- ChatGPT/Claude estimando TAM — não tem dado primário.
- Você mesmo, ou amigos do usuário, dizendo "eu compraria".
- Surveys com pergunta enviesada ("você pagaria por…?").
