---
execution: subagent
agent: criador-stories
format: instagram-stories
inputFile: squads/instagram-content/output/selected-angle.md
outputFile: squads/instagram-content/output/stories-sequence.md
model_tier: powerful
---

# Step 6: Criação de Conteúdo — Instagram Stories

## Context Loading

Carregar antes de executar:
- `squads/instagram-content/output/selected-angle.md` — ângulo, driver psicológico e tema aprovados no Step 3
- `pipeline/data/tone-of-voice.md` — tom de voz educativo do squad
- `_opensquad/_memory/company.md` — contexto da César Couto Arquitetura
- Regras de `instagram-stories` (injetadas automaticamente pelo Pipeline Runner via o campo `format` deste step)

## Instructions

### Process

1. Executar a tarefa `criar-sequencia-stories.md` do agente: definir o arco da sequência (abertura, contexto, interativo, fechamento) com 3-7 frames.
2. Escrever cada frame com no máximo 2-3 linhas, tom coloquial e primeira pessoa, evitando repetir o conteúdo do Feed sem adaptação.
3. Definir o elemento interativo (enquete/quiz/caixa de pergunta) com prompt específico e o CTA de fechamento.

## Output Format

```
=== SEQUÊNCIA DE STORIES ===
FRAME 1 (Abertura): [Visual] [Texto na tela] [Sticker/Elemento]
FRAME 2 (Contexto): [Visual] [Texto na tela] [Sticker/Elemento]
FRAME 3 (Interativo): [Visual] [Texto na tela] [Elemento Interativo]
FRAME 4 (Fechamento/CTA): [Visual] [Texto na tela] [Sticker/Elemento]

=== NOTAS DA SEQUÊNCIA ===
Total de frames: [3-7]
Tempo estimado: [X segundos]
Objetivo principal: [Engajamento/Tráfego/Feedback/Anúncio]
```

## Output Example

```
=== SEQUÊNCIA DE STORIES ===

FRAME 1 (Abertura):
[Visual]: Selfie/vídeo direto pra câmera, fundo de escritório
[Texto na tela]: "Real: quase ninguém sabe disso antes de comprar o terreno 👀"
[Sticker/Elemento]: Nenhum

FRAME 2 (Contexto):
[Visual]: Foto de um terreno
[Texto na tela]: "O banco não avalia só você. Ele avalia o terreno E o projeto juntos."
[Sticker/Elemento]: Nenhum

FRAME 3 (Contexto):
[Visual]: Foto de um laudo/documento técnico (sem dados sensíveis)
[Texto na tela]: "Uma avaliação técnica antes de comprar já te mostra se dá certo."
[Sticker/Elemento]: Nenhum

FRAME 4 (Interativo):
[Visual]: Fundo neutro com ícone de casa
[Texto na tela]: "E você, em que fase tá?"
[Elemento Interativo]: Enquete: "Já tenho o terreno" vs "Ainda tô procurando"

FRAME 5 (Fechamento/CTA):
[Visual]: Foto de projeto residencial finalizado
[Texto na tela]: "Me chama na DM que eu te explico como pedir essa avaliação"
[Sticker/Elemento]: "Me chama na DM" + menção @cto.mcp

=== NOTAS DA SEQUÊNCIA ===
Total de frames: 5
Tempo estimado: 20 segundos
Objetivo principal: Engajamento e geração de conversa em DM (topo de funil de leads)
```

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. A sequência não tem nenhum elemento interativo.
2. Algum frame tem mais de 3 linhas de texto ou linguagem formal destoante do tom de Stories.

## Quality Criteria

- [ ] Sequência tem entre 3 e 7 frames com arco narrativo completo
- [ ] Pelo menos um frame tem elemento interativo com prompt específico
- [ ] Tom é claramente mais informal que o Feed e o Reels
