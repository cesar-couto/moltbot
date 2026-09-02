---
task: "Criar Slides do Carrossel"
order: 1
input: |
  - feed-content.md: Carrossel de Feed aprovado, com todos os slides e texto final (obrigatório)
  - company.md: Identidade da marca (cores, tom visual) (obrigatório)
output: |
  - design-manifest.md: Resumo do design system + lista de arquivos HTML gerados, salvo em squads/instagram-content/output/design-manifest.md
  - slide-01.html ... slide-NN.html: Um arquivo HTML autocontido por slide, em squads/instagram-content/output/slides/
---

# Criar Slides do Carrossel

Transforma o carrossel de Feed aprovado em arquivos HTML autocontidos, um por slide, seguindo o design system da marca.

## Process

1. Ler `squads/instagram-content/output/feed-content.md` para obter o texto final de cada slide (headline, texto de apoio, direção de foto). Ler `_opensquad/_memory/company.md` para tom visual da marca (sem paleta de cores definida formalmente, extrair um tom coerente com "arquitetura residencial de médio-alto padrão": sóbrio, elegante, confiável).
2. Definir e documentar o design system: cores (máximo 5: primária, secundária, destaque, fundo, texto), tipografia (família sans-serif via Google Fonts @import, escala hero/heading/body/caption respeitando os mínimos de 58/43/34/24px para carrossel 1080x1440), espaçamento (unidade base e margens), grid (estrutura de coluna).
3. Criar o HTML do slide 1, aplicando o design system. Body com `width: 1080px; height: 1440px; margin:0; padding:0; overflow:hidden`. Usar Flexbox/Grid para o layout. Nunca incluir contador de slide.
4. Renderizar (via skill `image-creator`/`template-designer`) e verificar visualmente o slide 1 antes de prosseguir: texto legível, contraste adequado, nada cortado.
5. Gerar os slides restantes com o mesmo design system, nomeando sequencialmente `slide-01.html`, `slide-02.html`, etc.
6. Escrever o `design-manifest.md` com o design system documentado e a lista de arquivos gerados.

## Output Format

```markdown
# Design Manifest — {nome do squad/run}

## Design System

**Viewport:** 1080 x 1440 (carrossel Instagram)

**Cores:**
- Primária: {hex} — {uso}
- Secundária: {hex} — {uso}
- Destaque: {hex} — {uso}
- Fundo: {hex} — {uso}
- Texto: {hex} — {uso}

**Tipografia:**
- Família: '{fonte}', sans-serif (Google Fonts @import)
- Hero: {px}px / {peso}
- Heading: {px}px / {peso}
- Body: {px}px / {peso}
- Caption: {px}px / {peso}

**Espaçamento:** unidade base {px}px, margem de conteúdo {px}px

**Racional:** {por que essas escolhas combinam com a marca}

## Slides Gerados

| Arquivo | Papel | Verificado |
|---|---|---|
| slides/slide-01.html | Capa | ✅ |
| slides/slide-02.html | {papel} | ✅ |
...
```

## Output Example

> Use como referência de qualidade, não como modelo rígido.

```markdown
# Design Manifest — instagram-content / run 2026-03-01

## Design System

**Viewport:** 1080 x 1440 (carrossel Instagram)

**Cores:**
- Primária: #1C2B33 (azul-petróleo escuro) — fundo, transmite solidez técnica
- Secundária: #C9A87C (dourado acinzentado) — detalhes e CTA, remete a acabamento de alto padrão
- Destaque: #E4572E (terracota) — palavras-chave e alertas
- Fundo claro: #F5F1EA (bege claro) — slides alternados
- Texto: #FFFFFF sobre fundo escuro / #1C2B33 sobre fundo claro

**Tipografia:**
- Família: 'Fraunces' para headlines, 'Inter' para corpo (Google Fonts @import)
- Hero: 64px / 700
- Heading: 46px / 700
- Body: 36px / 500
- Caption: 26px / 500

**Espaçamento:** unidade base 24px, margem de conteúdo 72px

**Racional:** Azul-petróleo e dourado remetem a arquitetura sóbria e acabamento de alto padrão, alinhados ao público de médio-alto padrão da César Couto Arquitetura. Terracota como destaque cria contraste quente sem fugir da paleta sóbria. Serifada (Fraunces) nos títulos remete a projeto/arquitetura; Inter no corpo garante legibilidade em mobile.

## Slides Gerados

| Arquivo | Papel | Verificado |
|---|---|---|
| slides/slide-01.html | Capa | ✅ |
| slides/slide-02.html | Problema | ✅ |
| slides/slide-03.html | Problema | ✅ |
| slides/slide-04.html | Ponte | ✅ |
| slides/slide-05.html | Solução | ✅ |
| slides/slide-06.html | Solução | ✅ |
| slides/slide-07.html | CTA | ✅ |
```

## Quality Criteria

- [ ] Design system documentado com no máximo 5 cores e valores exatos em hex
- [ ] Todos os tamanhos de fonte respeitam os mínimos da plataforma (58/43/34/24px)
- [ ] Todo HTML é autocontido, sem dependência externa além de Google Fonts
- [ ] Primeiro slide foi verificado visualmente antes do lote completo
- [ ] Nenhum slide contém contador de posição

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. Algum slide usa fonte abaixo do mínimo da plataforma ou contraste abaixo de 4.5:1.
2. Algum HTML depende de recurso externo além de Google Fonts (CDN de CSS/JS, imagem hospedada fora do arquivo).
