# Padrões de seção — researcher

Padrões reutilizáveis para cada tipo de seção do documento Markdown. Use junto com [`aula.md`](aula.md) substituindo placeholders `{{...}}`.

Regra macro: **um cabeçalho = uma ideia**. Parágrafos curtos (2–5 frases). Listas para enumerar; prosa para explicar relação.

---

## Cabeçalho da aula

**Função:** orientar o leitor sobre o que vai consumir.

**Conter (no template):**
- `# Aula — Título declarativo` (não "Introdução a X" — use "X: por que falha em alta concorrência").
- Blockquote curto com gancho ou subtítulo.
- Tabela de metadados: recorte, pré-requisitos, objetivo, duração, nível.
- Sumário com âncoras para os blocos.

**Anti-padrão:** título genérico tipo "Aula sobre X". Use o ângulo, não o tema.

---

## Por que importa (gancho)

**Função:** dar ao leitor uma razão concreta para continuar.

**Padrões:**
- **Pergunta-armadilha** que parece fácil mas não é. (`Por que `0.1 + 0.2 !== 0.3` em JavaScript?`)
- **História curta** de um caso real (com fonte). ("Em 1999 a Mars Climate Orbiter perdeu-se por confusão de unidades…")
- **Custo do desconhecimento** quantificado. ("Bug de tipo em sistema X custou Y horas de downtime.")

**Não use:** "Hoje vamos falar sobre…", "X é muito importante", "no mundo atual…".

---

## Contexto histórico

**Função:** ancorar o conceito no tempo e nas pessoas.

**Padrão:**
1. Parágrafo curto (3–5 frases): quando, onde, por quem o conceito foi proposto, qual problema resolveu.
2. Citação direta da obra fundadora em blockquote.

**Cuidado:** verificar datas e nomes via WebSearch. Se a história é mítica/lendária ("Newton e a maçã"), reconhecer como tal no texto.

---

## Definição central

**Função:** fixar o conceito em uma frase de autoridade + uma frase em linguagem simples.

**Padrão:**

```markdown
> *"Excerto literal definindo o conceito, máximo 3 frases."*
>
> — Sobrenome, *Título*, ano, p. XX

**Em linguagem simples:** tradução em 1–2 frases acessíveis ao nível declarado do leitor.
```

**Anti-padrão:** definição autorreferente ("X é uma técnica de X") ou puro jargão sem tradução.

---

## Camada de aprofundamento (Bloco 2)

**Função:** apresentar uma camada nova apoiada na anterior.

**Padrão por camada:**

```markdown
### Camada N — Nome curto

Parágrafo de 2–4 frases explicando a *ideia desta camada* em linguagem simples,
com analogia se ajudar.

**Detalhamento:**

- Bullet 1 — mecanismo concreto.
- Bullet 2 — mecanismo concreto.
- Bullet 3 — relação com a camada anterior.

**Mini-exemplo:** instância concreta menor que o exemplo do Bloco 3 — só o suficiente
para sedimentar a camada.

> *"Citação que ancora a camada (opcional)."*
>
> — Autor, *Obra*, ano, p. XX
```

**Quantidade típica:** 3 a 6 camadas. Mais que isso, dividir em duas aulas.

---

## Citação direta

```markdown
> *"Excerto literal, máximo 3 frases."*
>
> — Sobrenome, *Título*, ano, p. XX
```

**Quando usar:**
- Definição central que ganha autoridade da fonte.
- Frase histórica icônica que perde força se parafraseada.
- Posição polêmica que precisa ser atribuída a autor específico.

**Quando não usar:**
- Conteúdo descritivo trivial — parafraseie e cite no final do parágrafo: `… (Sobrenome, ano, p. XX).`
- Citações longas (>3 frases) — quebre em duas ou parafraseie.

**Sempre verificar a obra antes de citar.** Ver [citation-rules.md](../references/citation-rules.md#protocolo-anti-alucinação).

---

## Checkpoint de recuperação ativa

**Função:** transformar leitura passiva em recuperação ativa (princípio de pedagogy.md).

**Padrão:**

```markdown
> **🔄 Checkpoint** — antes de seguir, responda mentalmente:
>
> 1. Pergunta sobre a camada anterior.
> 2. Pergunta de aplicação simples.
>
> <details><summary>Gabarito</summary>
>
> Resposta esperada — pode incluir múltiplos parágrafos, listas, código.
>
> </details>
```

O `<details>` é renderizado como bloco colapsável em GitHub, VSCode, Obsidian e a maioria dos visualizadores Markdown — o leitor abre só após tentar responder.

**Quando incluir:** entre camadas do Bloco 2 (a partir da segunda); no fim do Bloco 2 antes dos exemplos práticos.

---

## Síntese visual

**Função:** dar ao leitor um modelo mental conectando as camadas vistas até aqui.

**Formatos preferenciais:**

### Mermaid (preferido)

```markdown
` ` `mermaid
graph LR
    A[Camada 1] --> B[Camada 2]
    B --> C[Camada 3]
    C --> D[Aplicação]
` ` `
```

Tipos úteis: `graph LR`/`TD`, `sequenceDiagram`, `classDiagram`, `flowchart`, `stateDiagram-v2`, `erDiagram`.

### Tabela

```markdown
| Camada | Ideia | Quando aplica |
|---|---|---|
| 1 | … | … |
| 2 | … | … |
```

### ASCII art simples
Quando o diagrama é muito específico para Mermaid e uma figura externa não é viável.

**Anti-padrão:** apenas um bullet "vimos X, Y, Z". Síntese precisa mostrar **relação**, não lista.

---

## Exemplo prático (Bloco 3)

**Função:** mostrar o conceito em ação, completo, passo a passo.

**Padrão:**

```markdown
### Exemplo N — Nome descritivo

**Contexto:** qual problema concreto, por que esse exemplo é representativo.

**Aplicação:**

` ` `python
# código completo, executável, com comentários enxutos
def exemplo():
    return resultado
` ` `

**Resultado e leitura:** o que aconteceu, o que isso ensina, conexão de volta com a camada teórica.

**O que aprender com este exemplo:** lição em 1 frase.
```

**Códigos:** sintaxe correta, comentários enxutos, sem `// TODO` ou pseudocódigo enganoso.

**Cálculos:** mostrar o passo intermediário, não só o resultado.

**Mínimo 2 exemplos** cobrindo casos diferentes (típico + limite, ou domínio A + domínio B).

---

## Exercício proposto (Bloco 4)

**Função:** dar ao leitor algo executável que solidifica o aprendizado.

**Estrutura obrigatória:**

```markdown
## Bloco 4 — Exercício proposto

### Objetivo
Frase única descrevendo o entregável.

### Pré-requisitos materiais
- Linguagem/ferramenta X versão Y.
- Dataset Z (link ou geração local).

### Passos sugeridos
1. Passo concreto.
2. Passo concreto.
3. …

### Critérios de pronto
- [ ] Critério verificável 1.
- [ ] Critério verificável 2.
- [ ] Critério verificável 3.

### Extensões opcionais
- Caminho A para aprofundar.
- Caminho B para aprofundar.
```

**Bom critério de pronto:**
- "A função retorna a sequência ordenada para entrada de até 10⁴ elementos em < 100 ms."
- "O texto produzido cita ao menos 3 fontes primárias verificáveis."

**Mau critério:**
- "Você sente que entendeu o assunto."
- "Pesquise mais sobre o tema."

**Use checkboxes** (`- [ ]`) — o leitor pode marcar progresso direto no editor.

---

## Bibliografia comentada (Bloco 5)

**Função:** entregar a trilha verificável.

**Padrão por item:**

```markdown
1. **Sobrenome, N. N.** (Ano). *Título do livro: subtítulo* (Edição). Editora.
   *Comentário em itálico explicando para quem é útil, em qual nível, por quê.*
```

**Exemplo:**

```markdown
1. **Sweller, J., van Merriënboer, J. J. G., & Paas, F.** (2019). *Cognitive Load Theory*. Springer.
   *Síntese atualizada do campo. Para quem quer ir além de Feynman e entender por que exemplos resolvidos funcionam. Nível intermediário-avançado.*
```

**Trilha por nível:**

```markdown
### Trilha de leitura

- **Introdutório:** obra acessível ao iniciante.
- **Intermediário:** obra que aprofunda sem ser árida.
- **Avançado:** paper/livro denso para quem persistir.
```

---

## Próximos passos

**Função:** redirecionar o leitor para ação.

**Padrão:** 3 ações concretas, ordenadas:

1. **Imediata** — executar exercício hoje.
2. **Curto prazo (≤ 1 semana)** — ler X capítulo da obra Y.
3. **Médio prazo (≤ 1 mês)** — projeto pessoal, leitura paralela, comunidade a entrar.

---

## Padrões técnicos especiais

### Math
- Inline: `$E = mc^2$`
- Display:
  ```markdown
  $$
  \int_0^1 x^2\,dx = \frac{1}{3}
  $$
  ```
GitHub renderiza nativamente desde 2022; VSCode, Obsidian e Typora também.

### Código longo
Mantenha blocos abaixo de ~40 linhas. Para algoritmos longos, dividir em subseções com explicação entre blocos.

### Tabelas
Manter ≤ 5 colunas e ≤ 8 linhas para legibilidade. Tabelas grandes vão em apêndice ou link externo.

### Notas de rodapé (opcional)
GFM suporta:
```markdown
Texto principal[^1].

[^1]: Conteúdo da nota.
```
Útil para esclarecimentos que quebrariam o fluxo se inseridos no texto principal.
