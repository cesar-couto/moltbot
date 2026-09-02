---
task: "Criar Sequência de Stories"
order: 1
input: |
  - selected-angle.md: Ângulo editorial escolhido pelo usuário (obrigatório)
  - tone-of-voice.md: Tom de voz aprovado do squad (obrigatório)
  - company.md: Contexto da empresa e do público-alvo (obrigatório)
output: |
  - stories-sequence.md: Sequência de Stories completa salva em squads/instagram-content/output/stories-sequence.md
---

# Criar Sequência de Stories

Produz uma sequência curta de Stories (3-7 frames) a partir do ângulo editorial aprovado, com pelo menos um elemento interativo, seguindo as regras de `instagram-stories` best-practice injetadas pelo Pipeline Runner.

## Process

1. Ler `squads/instagram-content/output/selected-angle.md` para entender ângulo e driver psicológico. Ler `pipeline/data/tone-of-voice.md` e `_opensquad/_memory/company.md`.
2. Definir o arco da sequência: abertura (gancho), 1-3 frames de contexto, 1 frame interativo, frame de fechamento com CTA.
3. Escrever cada frame com no máximo 2-3 linhas de texto, tom coloquial e primeira pessoa.
4. Definir o elemento interativo (enquete, quiz, caixa de pergunta ou slider) com prompt específico e concreto, nunca vago.
5. Escrever o frame de fechamento com CTA claro: link da bio com contexto, "responde na DM" ou convite direto.

## Output Format

```
=== SEQUÊNCIA DE STORIES ===

FRAME 1 (Abertura):
[Visual]: {foto/vídeo ou cor de fundo}
[Texto na tela]: {texto de gancho — máx 2 linhas, fonte grande}
[Sticker/Elemento]: {Nenhum / Música / Localização / Menção}

FRAME 2 (Contexto):
[Visual]: {descrição}
[Texto na tela]: {contexto de apoio — máx 3 linhas}
[Sticker/Elemento]: {opcional}

FRAME 3 (Interativo):
[Visual]: {fundo ou visual de apoio}
[Texto na tela]: {texto que introduz o elemento interativo}
[Elemento Interativo]: {Enquete: "Opção A" vs "Opção B" / Quiz: "Pergunta?" com alternativas / Caixa de pergunta: "Me pergunta sobre..." / Slider de emoji}

FRAME 4 (Fechamento/CTA):
[Visual]: {visual final}
[Texto na tela]: {conclusão, entrega ou CTA — máx 2 linhas}
[Sticker/Elemento]: {Sticker de link com URL / "Me chama na DM" / Sticker de contagem}

=== NOTAS DA SEQUÊNCIA ===
Total de frames: {3-7}
Tempo estimado de visualização: {X segundos}
Objetivo principal: {Engajamento / Tráfego / Feedback / Anúncio}
```

## Output Example

> Use como referência de qualidade, não como modelo rígido.

```
=== SEQUÊNCIA DE STORIES ===

FRAME 1 (Abertura):
[Visual]: Selfie/vídeo direto pra câmera, fundo de escritório ou canteiro de obra
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
[Sticker/Elemento]: "Me chama na DM" + sticker de menção @cto.mcp

=== NOTAS DA SEQUÊNCIA ===
Total de frames: 5
Tempo estimado de visualização: 20 segundos
Objetivo principal: Engajamento e geração de conversa em DM (topo de funil de leads)
```

## Quality Criteria

- [ ] Sequência tem entre 3 e 7 frames
- [ ] Nenhum frame excede 3 linhas de texto
- [ ] Há pelo menos um elemento interativo com prompt específico
- [ ] Sequência segue arco narrativo completo (abertura, contexto, interação, fechamento)
- [ ] Tom é coloquial e em primeira pessoa

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. A sequência não tem nenhum elemento interativo.
2. Algum frame tem mais de 3 linhas de texto ou linguagem formal destoante do tom de Stories.
