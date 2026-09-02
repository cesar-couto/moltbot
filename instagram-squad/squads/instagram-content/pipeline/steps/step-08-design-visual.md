---
execution: subagent
agent: designer-visual
inputFile: squads/instagram-content/output/feed-content.md
outputFile: squads/instagram-content/output/design-manifest.md
model_tier: powerful
---

# Step 8: Design Visual dos Slides do Carrossel

## Context Loading

Carregar antes de executar:
- `squads/instagram-content/output/feed-content.md` — carrossel de Feed aprovado no Step 7
- `_opensquad/_memory/company.md` — identidade da marca (setor, público, diferenciais) para orientar o tom visual
- `pipeline/data/domain-framework.md` — framework de design visual do squad

## Instructions

### Process

1. Executar a tarefa `criar-slides-carrossel.md` do agente: documentar o design system (cores, tipografia, espaçamento, grid) antes de qualquer slide individual.
2. Gerar o HTML autocontido do slide 1, renderizar e verificar visualmente (texto legível, contraste, nada cortado) antes de prosseguir.
3. Gerar os demais slides com o mesmo design system, salvando em `squads/instagram-content/output/slides/slide-01.html` até `slide-NN.html`.
4. Escrever o `design-manifest.md` com o design system documentado e a tabela de slides gerados.

## Output Format

```markdown
# Design Manifest — {run}

## Design System
[Viewport, Cores, Tipografia, Espaçamento, Racional]

## Slides Gerados
| Arquivo | Papel | Verificado |
```

## Output Example

```markdown
# Design Manifest — instagram-content / run 2026-03-01

## Design System

**Viewport:** 1080 x 1440 (carrossel Instagram)

**Cores:**
- Primária: #1C2B33 (azul-petróleo escuro) — fundo, transmite solidez técnica
- Secundária: #C9A87C (dourado acinzentado) — detalhes e CTA, acabamento de alto padrão
- Destaque: #E4572E (terracota) — palavras-chave e alertas
- Fundo claro: #F5F1EA (bege claro) — slides alternados
- Texto: #FFFFFF sobre fundo escuro / #1C2B33 sobre fundo claro

**Tipografia:**
- Família: 'Fraunces' para headlines, 'Inter' para corpo (Google Fonts @import)
- Hero: 64px / 700 — Heading: 46px / 700 — Body: 36px / 500 — Caption: 26px / 500

**Espaçamento:** unidade base 24px, margem de conteúdo 72px

**Racional:** Azul-petróleo e dourado remetem a arquitetura sóbria e acabamento de alto padrão. Terracota cria contraste quente sem fugir da paleta sóbria. Serifada nos títulos remete a projeto/arquitetura; Inter no corpo garante legibilidade em mobile.

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

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. Algum slide usa fonte abaixo do mínimo da plataforma (58/43/34/24px) ou contraste abaixo de 4.5:1.
2. Algum HTML depende de recurso externo além de Google Fonts (CDN de CSS/JS, imagem hospedada fora do arquivo).

## Quality Criteria

- [ ] Design system documentado com no máximo 5 cores e valores exatos
- [ ] Todo HTML é autocontido, sem contador de slide
- [ ] Primeiro slide foi verificado visualmente antes do lote completo
