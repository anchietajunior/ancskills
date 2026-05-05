# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Propósito do repositório

`ancskills` é uma coleção de **skills** do Claude Code. Cada skill encapsula expertise profunda em um domínio específico e é acionada por um comando/gatilho próprio. O repositório não tem build, testes ou runtime tradicional — o "código" são os artefatos de skill (`SKILL.md` + scripts/templates de apoio) que o Claude Code carrega sob demanda.

Toda comunicação, comentários e conteúdo de skills devem ser escritos em **PT-BR** (mantendo termos técnicos e identificadores no original).

## Estrutura

```
.claude/skills/<nome-da-skill>/
  SKILL.md          # frontmatter + corpo procedimental (obrigatório)
  scripts/          # scripts executáveis opcionais (Python, Bash, etc.)
  references/       # docs longas, exemplos, cheatsheets carregados sob demanda
  templates/        # templates/boilerplate gerados pela skill
```

Skills são descobertas automaticamente pelo Claude Code a partir de `.claude/skills/`. O nome do diretório é o identificador da skill (kebab-case).

## Regras de autoria de SKILL.md

A qualidade de uma skill é determinada quase inteiramente por dois fatores: o **`description`** do frontmatter (decide *quando* a skill é invocada) e a **estrutura procedimental do corpo** (decide *como* o resultado fica).

### Frontmatter obrigatório

```yaml
---
name: nome-da-skill            # idêntico ao nome do diretório
description: |
  Frase 1: o que a skill faz, em voz ativa e objetiva.
  Frase 2: gatilhos explícitos — verbos/frases que o usuário tipicamente diz
  ("crie X", "/comando Y", "preciso de Z"), domínios e formatos de saída.
  Frase 3 (opcional): contraste com skills vizinhas para evitar overlap.
---
```

- O `description` é a única coisa que o modelo vê ao decidir invocar a skill — deve ser **específico, com exemplos de fraseado real do usuário**, e deixar claro o escopo (e o que *não* faz).
- Evite descrições genéricas tipo "ajuda com X". Inclua verbos de gatilho, formato de entrega, e diferenciadores.

### Corpo da SKILL.md

Estrutura recomendada:

1. **Objetivo (1 parágrafo)** — o problema que a skill resolve e o resultado esperado.
2. **Quando usar / quando não usar** — lista curta com fronteiras claras.
3. **Procedimento** — passos numerados, imperativos, verificáveis. Cada passo declara o que fazer e como saber que terminou. Evite prosa descritiva.
4. **Padrões e templates** — blocos de código/markdown prontos para reuso, idealmente carregados de `templates/` em vez de inline quando longos.
5. **Saída esperada** — o que a skill *entrega* (arquivo gerado, mensagem, decisão).
6. **Referências** — links para `references/<arquivo>.md` para conteúdo longo, em vez de inflar o SKILL.md.

### Princípios de profundidade

O usuário desta coleção exige que cada skill incorpore as **melhores técnicas de aprofundamento** do seu domínio. Ao criar/editar uma skill:

- **Pesquise antes de escrever.** Use `mcp__plugin_compound-engineering_context7__query-docs` para docs de bibliotecas/frameworks atuais; use `WebSearch`/`WebFetch` para padrões reconhecidos do domínio (ISO, RFCs, papers, style guides oficiais). Não escreva por memória quando há fonte autoritativa.
- **Codifique heurísticas, não só passos.** Inclua critérios de decisão ("se X, prefira Y porque Z"), armadilhas conhecidas, e contra-exemplos.
- **Seja específico sobre formato de saída.** Se a skill produz um documento, defina seções, voz, comprimento e exemplos canônicos.
- **Prefira ações verificáveis.** Cada passo deve ter um critério objetivo de conclusão (arquivo existe, comando retorna 0, regex casa, etc.).
- **Mantenha o SKILL.md enxuto.** Ofusque conteúdo extenso (tabelas grandes, exemplos completos, prompts auxiliares) em `references/` e referencie por caminho relativo.

### Convenção de comandos

Todos os slash-commands deste repositório vivem sob o namespace `anc:`. Concretamente:

- Arquivos em `.claude/commands/anc/<comando>.md` são invocados como `/anc:<comando>`.
- Cada skill em `.claude/skills/<nome>/SKILL.md` tem um slash-command correspondente em `.claude/commands/anc/<nome>.md`.
- O `description` do frontmatter da SKILL.md também permite invocação implícita por linguagem natural; o slash-command é o atalho explícito.

Não criar comandos fora do namespace `anc:`.

## Fluxo de criação de uma nova skill

1. Defina o objetivo em uma frase: "esta skill produz X a partir de Y, em formato Z".
2. Crie `.claude/skills/<nome>/SKILL.md` com frontmatter completo.
3. Pesquise fontes autoritativas do domínio (docs oficiais, padrões consolidados) e destile heurísticas no procedimento.
4. Extraia conteúdo longo para `references/` e templates para `templates/`.
5. Teste a skill invocando-a por seu gatilho explícito e por linguagem natural plausível — ajuste o `description` se a invocação implícita falhar.
6. Commit por skill (um diretório = um commit), com mensagem `skill(<nome>): descrição curta`.

## Skills existentes

- **`saas-idealizer`** — `/anc:saas-idealizer [área opcional]` — atua como investidor-pesquisador honesto para idealizar e validar micro-SaaS; sem área pesquisa 3 nichos, com área conduz entrevista cirúrgica e emite veredito (SEGUIR/ITERAR/MATAR) com plano em 3 fases.
- **`researcher`** — `/anc:researcher [tema opcional]` — professor que ensina assunto complexo de forma simples com aprofundamento gradual e referências verificáveis; entrega arquivo Markdown auto-contido (`aula-<slug>.md`, com Mermaid e LaTeX embutidos) em 5 blocos: contextualização, aprofundamento, exemplos práticos, exercício proposto, bibliografia comentada.
