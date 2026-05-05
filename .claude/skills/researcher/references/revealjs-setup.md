# Reveal.js — setup técnico para a skill

Reveal.js é um framework HTML para apresentações. A skill gera **um único arquivo HTML auto-contido** que carrega o framework via CDN e expõe slides legíveis por navegador.

Versão de referência: **5.x** (estável em 2026). Sempre pinar versão exata na CDN para reprodutibilidade.

---

## Esqueleto mínimo (referência)

```html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" />
  <title>Aula — <Tema></title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reset.css" />
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.css" />
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/theme/white.css" id="theme" />
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/monokai.css" />
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.11/dist/katex.min.css" />
</head>
<body>
  <div class="reveal">
    <div class="slides">
      <!-- slides aqui -->
    </div>
  </div>
  <script src="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/markdown/markdown.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/highlight.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/notes/notes.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/math/math.js"></script>
  <script>
    Reveal.initialize({
      hash: true,
      controls: true,
      progress: true,
      slideNumber: 'c/t',
      transition: 'fade',
      width: 1280,
      height: 800,
      margin: 0.08,
      plugins: [ RevealMarkdown, RevealHighlight, RevealNotes, RevealMath.KaTeX ]
    });
  </script>
</body>
</html>
```

---

## Configuração recomendada

| Opção | Valor | Justificativa |
|---|---|---|
| `hash: true` | habilita URL âncora por slide — facilita compartilhar slide específico |
| `controls: true` | setas de navegação visíveis |
| `progress: true` | barra de progresso na borda inferior |
| `slideNumber: 'c/t'` | indicador "12/40" útil em leitura |
| `transition: 'fade'` | menos enjoativo que slide/zoom; bom para acessibilidade |
| `width: 1280, height: 800` | proporção 16:10, equilibra densidade e zoom em laptops 13" |
| `margin: 0.08` | respiro visual; impede texto colado nas bordas |
| `pdfSeparateFragments: false` | quando exportar PDF, evita explodir fragmentos em múltiplas páginas |

Para modo escuro a pedido: trocar `theme/white.css` por `theme/black.css` ou `theme/night.css` e o CSS de highlight de `monokai.css` para `github-dark.css`.

---

## Sintaxe de slides

### Slide horizontal simples
```html
<section>
  <h2>Título do slide</h2>
  <p>Conteúdo curto.</p>
  <aside class="notes">
    Notas de palestrante: contexto extra que o leitor abre com tecla S.
  </aside>
</section>
```

### Slides verticais (sub-slides)
Use para aprofundar um conceito sem encher o eixo horizontal:
```html
<section>
  <section><h2>Conceito</h2><p>Visão geral</p></section>
  <section><h3>Detalhe 1</h3><p>...</p></section>
  <section><h3>Detalhe 2</h3><p>...</p></section>
</section>
```

### Markdown inline (alternativa, útil para textos longos)
```html
<section data-markdown>
  <textarea data-template>
## Título
- Bullet 1
- Bullet 2

Note: notas de palestrante depois de "Note:".
  </textarea>
</section>
```

### Citação
```html
<blockquote>
  <em>"Excerto literal."</em>
  <footer>— Sobrenome, <cite>Título</cite>, ano, p. 42</footer>
</blockquote>
```

### Código com highlight
```html
<pre><code class="language-python" data-trim data-noescape>
def hello():
    print("oi")
</code></pre>
```

Linhas destacáveis: `data-line-numbers="2,4-6"` para chamar atenção a linhas específicas.

### Math (KaTeX)
- Inline: `\\(E = mc^2\\)`
- Display: `\\[ \\int_0^1 x^2\\,dx = \\tfrac{1}{3} \\]`
- Equações numeradas: usar `\\begin{equation}...\\end{equation}` quando necessário.

### Diagramas
- **SVG inline** — preferencial, totalmente self-contained.
- **Mermaid** — habilitar plugin `reveal.js-mermaid-plugin` se necessário; aumenta peso do HTML.
- Evitar `<img src="...">` apontando para CDN externo, exceto Wikimedia/Unsplash com URL estável e sob licença adequada (cite a licença).

### Fragmentos (revelar progressivamente)
```html
<ul>
  <li class="fragment">Aparece primeiro</li>
  <li class="fragment">Depois</li>
  <li class="fragment">Por último</li>
</ul>
```
Use com parcimônia em apresentação para leitura; melhor para palestra ao vivo.

---

## Atalhos úteis para o leitor

| Tecla | Ação |
|---|---|
| `→` `←` `↑` `↓` ou `Espaço` | navegar |
| `S` | abrir notas de palestrante (segunda janela) |
| `F` | fullscreen |
| `ESC` ou `O` | visão geral (overview) com todos os slides |
| `B` ou `.` | escurecer tela |
| `?` | ajuda |
| `Alt+clique` | zoom |

Inclua estes atalhos em uma nota no slide de capa ou em rodapé do primeiro bloco.

---

## Exportar para PDF

Adicionar `?print-pdf` à URL e imprimir via Chrome/Edge → "Salvar como PDF":
- Tamanho papel: A4 paisagem ou Letter paisagem.
- Margens: nenhuma.
- Background graphics: ativado.

---

## Acessibilidade

- Contraste mínimo AA — temas `white`, `simple`, `serif` atendem.
- Tamanho de fonte mínimo: ~28pt para corpo (Reveal já cuida no default).
- Navegação por teclado já é nativa.
- Para leitores de tela, manter hierarquia `h1`/`h2`/`h3` corretamente.
- Evitar transições agressivas (`transition: 'fade'`).

---

## Fontes legíveis para leitura prolongada

Quando o tema for academic/serio, sobrescrever fontes via CSS inline antes de `</head>`:

```html
<style>
  :root { --r-main-font: 'Source Serif 4', 'Georgia', serif;
          --r-heading-font: 'Inter', system-ui, sans-serif; }
</style>
```

Self-host das fontes só se ofline; caso contrário, Google Fonts via `<link>` é aceitável (carrega rápido, não é tracking de usuário em apresentação local).

---

## Anti-padrões técnicos

- **Não usar versão `latest`** na CDN — quebra reprodutibilidade.
- **Não enviar mais de ~80 slides** em um único deck — divida em múltiplas aulas.
- **Não inserir vídeo grande embedded** — link externo é melhor; manter HTML leve.
- **Não confiar em fontes externas que podem cair** — quando possível, embeber CSS/JS críticos.
- **Não usar `transition: 'zoom'` ou `'rotate'`** — desorientam leitor que está estudando.
