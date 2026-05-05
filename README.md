# ancskills

> Coleção de skills do Claude Code para objetivos múltiplos.
> A collection of Claude Code skills for multiple objectives.

---

## 🇧🇷 Português

`ancskills` é um repositório de **skills** do [Claude Code](https://claude.ai/code) — pacotes de expertise carregados sob demanda que estendem o agente com procedimentos especializados, frameworks de referência e templates de saída.

Cada skill vive em `.claude/skills/<nome>/` e é acionada por:

- **Comando dedicado** — slash-command em `.claude/commands/<nome>.md` (invocação explícita: `/<nome>`).
- **Invocação implícita** — o Claude Code lê o `description` do frontmatter da SKILL.md e decide invocar quando o pedido do usuário casa com os gatilhos.

Toda skill segue uma postura de **profundidade real**: pesquisa em fontes autoritativas, heurísticas verificáveis, output procedimental — sem prosa decorativa. Detalhes da convenção de autoria estão em [`CLAUDE.md`](CLAUDE.md).

### Como usar

1. Clone o repositório dentro do diretório de trabalho onde você usa Claude Code, ou copie o conteúdo de `.claude/` para o `.claude/` do seu projeto.
2. Inicie o Claude Code no diretório.
3. Invoque uma skill pelo seu slash-command sob o namespace `anc:` (ex.: `/anc:saas-idealizer`, `/anc:researcher`) ou descreva sua necessidade em linguagem natural — o agente decidirá se usa a skill aplicável.

---

## 🇺🇸 English

`ancskills` is a [Claude Code](https://claude.ai/code) **skills** repository — on-demand expertise packages that extend the agent with specialized procedures, reference frameworks, and output templates.

Each skill lives in `.claude/skills/<name>/` and is triggered by:

- **Dedicated command** — slash-command at `.claude/commands/<name>.md` (explicit invocation: `/<name>`).
- **Implicit invocation** — Claude Code reads the SKILL.md frontmatter `description` and decides to invoke when the user's request matches the triggers.

Every skill follows a posture of **genuine depth**: research from authoritative sources, verifiable heuristics, procedural output — no decorative prose. Authoring conventions are detailed in [`CLAUDE.md`](CLAUDE.md).

### How to use

1. Clone this repository into the working directory where you use Claude Code, or copy the contents of `.claude/` into your project's `.claude/`.
2. Start Claude Code in that directory.
3. Invoke a skill by its slash-command under the `anc:` namespace (e.g. `/anc:saas-idealizer`, `/anc:researcher`) or describe your need in natural language — the agent will decide whether to apply the matching skill.

> **Note:** the skills themselves are written in PT-BR per author preference. They work seamlessly with English prompts, but generated artifacts (reports, plans) will be delivered in Portuguese unless you explicitly request another language.

---

## Skills disponíveis · Available skills

| Skill | Comando · Command | Objetivo (PT-BR) | Purpose (EN) |
|---|---|---|---|
| [`saas-idealizer`](.claude/skills/saas-idealizer/SKILL.md) | `/anc:saas-idealizer [área opcional]` | Atua como investidor-pesquisador honesto para idealizar e validar micro-SaaS. Sem área, pesquisa 3 nichos promissores e pede escolha. Com área/projeto, conduz entrevista cirúrgica estilo Mom Test, faz pesquisa externa de concorrentes e mercado, e emite veredito acionável (`SEGUIR` / `ITERAR` / `MATAR`) com Lean Canvas, ICP, monetização, matriz competitiva e plano de execução em 3 fases (validação pré-build → MVP cobrável → tração). | Acts as an honest investor-researcher to ideate and validate micro-SaaS opportunities. Without an area, it researches 3 promising niches and asks the user to pick one. With an area/project, it runs a Mom Test–style surgical interview, performs external competitor and market research, and delivers an actionable verdict (`PROCEED` / `ITERATE` / `KILL`) with Lean Canvas, ICP, monetization, competitive matrix, and a 3-phase execution plan (pre-build validation → billable MVP → traction). |
| [`researcher`](.claude/skills/researcher/SKILL.md) | `/anc:researcher [tema opcional]` | Professor que explica assuntos complexos de forma simples, com aprofundamento gradual e lógico, ancorado em referências bibliográficas verificáveis (com excertos das obras). Entrega final: apresentação Reveal.js auto-contida (`aula-<slug>.html`) com 5 blocos — contextualização teórica → aprofundamento em camadas → exemplos práticos → 1 exercício/projeto proposto → bibliografia comentada com trilha de leitura. Sem tema, pergunta ao usuário antes de prosseguir. | Acts as a professor explaining complex subjects clearly, with gradual logical depth and verifiable bibliographic references (including excerpts from primary works). Final deliverable: a self-contained Reveal.js presentation (`aula-<slug>.html`) with 5 blocks — theoretical contextualization → layered deepening → practical examples → 1 proposed exercise/project → annotated bibliography with reading path. Without a topic, it asks the user first. |

---

## Estrutura · Structure

```
ancskills/
├── CLAUDE.md                       # diretrizes para Claude Code · Claude Code guidelines
├── README.md                       # este arquivo · this file
└── .claude/
    ├── commands/anc/               # slash-commands no namespace anc: (1 por skill · 1 per skill)
    │   └── <skill>.md              # invocado como /anc:<skill>
    └── skills/
        └── <skill>/
            ├── SKILL.md            # frontmatter + procedimento · frontmatter + procedure
            ├── references/         # frameworks, fontes, conteúdo longo · frameworks, sources, long content
            └── templates/          # templates de entrega · output templates
```

---

## Contribuindo · Contributing

Convenções de autoria de skill estão documentadas em [`CLAUDE.md`](CLAUDE.md). Resumo:

- Um diretório de skill = um commit, mensagem `skill(<nome>): descrição curta`.
- Frontmatter com `description` específico, com gatilhos de invocação.
- Corpo procedimental, imperativo, com critérios de conclusão por passo.
- Conteúdo longo extraído para `references/` e `templates/`.

Skill authoring conventions are documented in [`CLAUDE.md`](CLAUDE.md). Summary:

- One skill directory = one commit, message `skill(<name>): short description`.
- Frontmatter with a specific `description` containing invocation triggers.
- Imperative, procedural body with completion criteria per step.
- Long-form content extracted into `references/` and `templates/`.
