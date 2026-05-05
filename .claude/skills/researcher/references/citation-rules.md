# Regras de citação e protocolo anti-alucinação — researcher

A maior falha possível desta skill é **inventar referências bibliográficas**. Aluno engana-se acreditando ter fonte; professor (humano ou agente) que fabrica fonte comete fraude intelectual. Este documento define o protocolo para impedir isso.

---

## Protocolo anti-alucinação

**Regra de ouro:** nenhuma obra entra na apresentação sem ter sido verificada por busca pública.

### Fluxo obrigatório

Para cada referência candidata:

1. **Buscar via WebSearch** com a query: `"<sobrenome do autor>" "<título exato ou parte distintiva>" <ano>`. Exigir ao menos 2 resultados independentes confirmando autor + título + ano.
2. **Confirmar editora/journal** — fonte confiável (catálogo de biblioteca, página da editora, DOI resolvível, página oficial do autor).
3. **Capturar dados completos:** sobrenome do autor, iniciais, ano, título, edição (se livro), editora ou journal+volume+páginas, DOI/ISBN quando disponível.
4. **Capturar excerto** apenas quando for verificável — preferencialmente do Google Books preview, do site da editora, ou do PDF público. Se não for possível verificar o excerto literal, **não cite verbatim** — descreva a ideia sem aspas.
5. **Registrar a URL/DOI consultada** nas notas de palestrante do slide correspondente, para auditabilidade.

### Sinais de alerta (descartar a referência)

- Resultado único na busca, em site genérico (blog, agregador de cursos, "world of books" sem catálogo).
- Título plausível mas autor "Anônimo" ou nome incomum sem outras publicações.
- Ano que não bate com a vida ativa do autor (ex.: obra de 1990 atribuída a autor que faleceu em 1985).
- Citação que aparece sempre com a mesma frase exata em vários sites — sinal de propagação de citação fabricada.
- "Citado por" sem fonte primária localizável.

### Quando não há fonte primária verificável

Três opções, em ordem de preferência:

1. **Substituir** por outra obra que cubra a ideia e seja verificável.
2. **Reformular** a afirmação como conhecimento de domínio sem citação ("É consenso na área que…", "Convencionalmente, define-se…").
3. **Marcar explicitamente** no slide e nas notas: *"Referência de tradição da área; fonte primária não localizada nesta sessão."*

Nunca: inventar citação para preencher slide.

---

## Padrão de citação visual nos slides

A skill usa **APA 7** simplificado para legibilidade em slides, com adaptações:

### Citação no corpo do slide
- **Paráfrase:** texto do conceito *(Sobrenome, ano, p. XX)*.
- **Citação direta:** bloco `<blockquote>` com o excerto + atribuição embaixo:

```html
<blockquote>
  <em>"Excerto literal da obra, de no máximo 3 frases, em itálico."</em>
  <footer>— Sobrenome, <cite>Título da obra</cite>, ano, p. XX</footer>
</blockquote>
```

### Slide de bibliografia (Bloco 5)
Lista com formato APA 7 completo:

- **Livro:** Sobrenome, N. N. (Ano). *Título do livro: subtítulo* (Edição, se ≠ 1ª). Editora.
- **Capítulo em livro:** Sobrenome, N. N. (Ano). Título do capítulo. Em N. N. Sobrenome (Ed.), *Título do livro* (pp. XX–YY). Editora.
- **Artigo:** Sobrenome, N. N. (Ano). Título do artigo. *Nome do Journal*, volume(número), páginas. https://doi.org/...
- **Documento online:** Sobrenome, N. N. (Ano, dia mês). *Título*. Site/Org. URL

Cada item recebe **um comentário curto** em itálico abaixo: para quem é útil, em que nível, por quê.

### Adaptação para ABNT (sob demanda)
Se o usuário declarar contexto brasileiro acadêmico estrito, oferecer alternativa ABNT (NBR 6023:2018):

- **Livro:** SOBRENOME, Nome. **Título da obra**: subtítulo. Edição. Cidade: Editora, ano.
- **Artigo:** SOBRENOME, Nome. Título do artigo. **Nome do Periódico**, Cidade, v. X, n. Y, p. ZZ-WW, mês ano.

Manter consistência: ou tudo APA, ou tudo ABNT — não misturar no mesmo deck.

---

## Quando preferir cada tipo de fonte

| Tipo de fonte | Usar como âncora quando | Cuidado |
|---|---|---|
| **Livro canônico do campo** | Definição central, contexto histórico, marco fundador | Verificar edição e ano da edição citada |
| **Paper seminal peer-reviewed** | Resultado experimental, método, descoberta | Checar se foi superado por meta-análise mais recente |
| **Norma técnica / RFC / lei** | Definições oficiais em domínios regulados | Confirmar versão vigente |
| **Documentação oficial de software** | Sintaxe, API, comportamento de ferramenta | Pinar versão consultada |
| **Obra de divulgação reconhecida** | Analogia acessível, gancho histórico | Não confiar para detalhes técnicos finos |
| **Survey/review recente** | Visão de campo amplo, tendências | Idealmente ≤ 5 anos para tópicos ativos |

---

## Citação direta — limites de uso justo

Para evitar problemas de direitos autorais e respeitar o autor:

- Excertos curtos (até ~3 frases) são geralmente cobertos por uso justo / direito de citação para fins educativos, com atribuição.
- Sempre incluir: autor, título, ano, página/seção.
- Não reproduzir tabelas/figuras inteiras sem permissão; descrever em palavras próprias e citar a fonte.
- Para textos clássicos em domínio público (anteriores a ~1928 nos EUA, ou ≥ 70 anos após morte do autor no Brasil — Lei 9.610/98), reprodução é livre — mesmo assim, citar.

---

## Lista canônica que costuma aparecer (verificar antes de citar)

Apenas para orientação rápida — **sempre revalidar via WebSearch** antes de citar nos slides:

- Kuhn, T. S. *The Structure of Scientific Revolutions*. University of Chicago Press, 1962.
- Knuth, D. E. *The Art of Computer Programming*. Addison-Wesley, vols. 1962–.
- Russell, S. & Norvig, P. *Artificial Intelligence: A Modern Approach*. Pearson, 4ª ed., 2020.
- Kahneman, D. *Thinking, Fast and Slow*. Farrar, Straus and Giroux, 2011.
- Shannon, C. E. "A Mathematical Theory of Communication". *Bell System Technical Journal*, 27, 1948.
- Turing, A. M. "Computing Machinery and Intelligence". *Mind*, 59(236), 433–460, 1950.
- Hennessy, J. L. & Patterson, D. A. *Computer Architecture: A Quantitative Approach*. Morgan Kaufmann.
- Cormen, T. H. et al. *Introduction to Algorithms*. MIT Press.

Esses títulos existem; verifique edição/ano antes de fixar no slide.
