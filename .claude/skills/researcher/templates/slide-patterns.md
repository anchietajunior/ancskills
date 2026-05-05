# Padrões de slide — researcher

Padrões reutilizáveis para cada tipo de slide. Use junto com [`presentation.html`](presentation.html) substituindo placeholders `{{...}}`.

Regra macro: **um slide = uma ideia**. Máximo ~40 palavras de texto visível. O extra vai para `<aside class="notes">`.

---

## Capa

**Função:** orientar o leitor sobre o que vai consumir.

**Conter:**
- Título declarativo (não "Introdução a X" — use "X: por que falha em alta concorrência").
- Subtítulo com recorte específico.
- Pré-requisitos em uma linha.
- Tempo estimado de leitura.
- Atalhos de teclado.

**Notas de palestrante:** público-alvo declarado, objetivo de aprendizagem em 1 frase, decisões de recorte (o que deliberadamente ficou de fora).

---

## Por que importa (gancho)

**Função:** dar ao leitor uma razão concreta para continuar.

**Padrões:**
- **Pergunta-armadilha** que parece fácil mas não é. ("Por que `0.1 + 0.2 !== 0.3` em JavaScript?")
- **História curta** de um caso real (com fonte). ("Em 1999 a Mars Climate Orbiter perdeu-se por confusão de unidades — diff. métrico vs imperial. NASA, 1999.")
- **Custo do desconhecimento** quantificado. ("Bug de tipo em sistema X custou Y horas de downtime.")

**Não use:** "Hoje vamos falar sobre…", "X é muito importante", "no mundo atual…".

---

## Contexto histórico

**Função:** ancorar o conceito no tempo e nas pessoas.

**Padrão:**
1. Quando, onde, por quem o conceito foi proposto.
2. Que problema concreto resolveu na época.
3. Citação direta da obra fundadora.

**Cuidado:** verificar datas e nomes via WebSearch. Se a história é mítica/lendária ("Newton e a maçã"), reconhecer como tal.

---

## Definição central

**Função:** fixar o conceito em uma frase de autoridade + uma frase em linguagem simples.

**Padrão:**
1. Citação direta da obra-âncora (excerto curto entre aspas, com atribuição).
2. **Tradução para linguagem simples** logo abaixo, começando por "Em outras palavras:" ou "Em linguagem simples:".

**Anti-padrão:** definição autorreferente ("X é uma técnica de X") ou puro jargão sem tradução.

---

## Camada de aprofundamento (Bloco 2)

**Função:** apresentar uma camada nova apoiada na anterior.

**Estrutura recomendada (3 sub-slides verticais):**
1. **"A ideia desta camada"** — 1 frase + analogia.
2. **Detalhamento** — 3 bullets de mecanismo, ou esquema visual.
3. **Mini-exemplo** — instância concreta menor que o exemplo do Bloco 3.

**Notas:** referência bibliográfica que sustenta a camada (autor, ano, página).

---

## Citação direta

```html
<blockquote>
  <em>"Excerto literal, máximo 3 frases."</em>
  <footer>— Sobrenome, <cite>Título</cite>, ano, p. XX</footer>
</blockquote>
```

**Quando usar:**
- Definição central que ganha autoridade da fonte.
- Frase histórica icônica que perde força se parafraseada.
- Posição polêmica que precisa ser atribuída a autor específico.

**Quando não usar:**
- Conteúdo descritivo trivial (parafraseie e cite).
- Citações longas (>3 frases — quebre em duas ou parafraseie).

---

## Checkpoint de recuperação ativa

**Função:** transformar leitura passiva em recuperação ativa (princípio de pedagogy.md).

**Padrão:**
```html
<div class="checkpoint">
  <p>Antes de seguir, responda mentalmente:</p>
  <ol>
    <li>Pergunta sobre a camada anterior.</li>
    <li>Pergunta de aplicação simples.</li>
  </ol>
</div>
```

Coloque o **gabarito nas notas de palestrante** — o leitor abre com `S` apenas após tentar.

**Quando incluir:** entre camadas do Bloco 2; no fim do Bloco 2 antes dos exemplos práticos.

---

## Síntese visual

**Função:** dar ao leitor um modelo mental conectando as camadas vistas até aqui.

**Formatos preferenciais:**
- **Diagrama SVG inline** (relação de dependência entre conceitos, fluxo, hierarquia).
- **Tabela** comparando os pontos das camadas.
- **Mermaid** quando complexidade justificar.

**Anti-padrão:** apenas um bullet "vimos X, Y, Z". Síntese precisa mostrar **relação**, não lista.

---

## Exemplo prático (Bloco 3)

**Função:** mostrar o conceito em ação, completo, passo a passo.

**Estrutura recomendada (3 sub-slides verticais):**
1. **Contexto** — qual problema concreto, por que esse exemplo é representativo.
2. **Aplicação** — código, cálculo, ou procedimento *completo*. Worked example.
3. **Resultado e leitura** — o que aconteceu, o que isso ensina, conexão de volta com a camada teórica.

**Códigos:** sintaxe correta, comentários enxutos, sem `// TODO` ou pseudocódigo enganoso.

**Cálculos:** mostrar o passo intermediário, não só o resultado.

---

## Exercício proposto (Bloco 4)

**Função:** dar ao leitor algo executável que solidifica o aprendizado.

**Estrutura obrigatória (sub-slides verticais):**
1. **Objetivo** — entregável claro e dimensionado.
2. **Pré-requisitos materiais** — linguagem, dados, ferramenta.
3. **Passos sugeridos** — 3 a 6 passos numerados.
4. **Critérios de pronto** — objetivos, verificáveis (saída esperada, propriedade que deve valer, métrica).
5. **Extensões opcionais** — 2–3 caminhos para quem quiser aprofundar.

**Bom critério de pronto:**
- "A função retorna a sequência ordenada para entrada de até 10⁴ elementos em < 100 ms."
- "O texto produzido cita ao menos 3 fontes primárias verificáveis."

**Mau critério:**
- "Você sente que entendeu o assunto."
- "Pesquise mais sobre o tema."

---

## Bibliografia comentada (Bloco 5)

**Função:** entregar a trilha verificável.

**Padrão por item:**
1. Referência completa em formato APA 7 (ou ABNT se contexto exigir).
2. **Comentário curto em itálico**: para quem é útil, em qual nível, por quê.

**Exemplo:**
> Sweller, J., van Merriënboer, J. J. G., & Paas, F. (2019). *Cognitive Load Theory*. Springer.
> *Síntese atualizada do campo. Para quem quer ir além de Feynman e entender por que exemplos resolvidos funcionam. Nível intermediário-avançado.*

**Trilha por nível** (slide separado):
- **Introdutório** — 1 obra acessível.
- **Intermediário** — 1 obra que aprofunda sem ser árida.
- **Avançado** — 1 paper/livro denso para quem persistir.

---

## Próximos passos

**Função:** redirecionar o leitor para ação.

**Padrão:** 3 ações concretas, ordenadas:
1. Imediata (executar exercício hoje).
2. Curto prazo (ler X capítulo da obra Y nos próximos 7 dias).
3. Médio prazo (projeto pessoal, leitura paralela, comunidade a entrar).

---

## Slides técnicos especiais

### Código longo
Quebre em sub-slides verticais com `data-line-numbers="2,4-6"` para ir destacando linhas conforme avança.

### Equações
Use KaTeX. Para derivações longas, fragmentos `\\(\\rightarrow\\)` por etapa em sub-slides verticais.

### Diagramas grandes
SVG inline com `viewBox` para escalar; ou Mermaid (mas o Mermaid não vem por padrão — ative apenas se necessário).

### Tabelas
Manter ≤ 5 colunas e ≤ 8 linhas. Tabelas grandes vão para notas de palestrante ou para o Markdown complementar (`aula-<slug>.md`).
