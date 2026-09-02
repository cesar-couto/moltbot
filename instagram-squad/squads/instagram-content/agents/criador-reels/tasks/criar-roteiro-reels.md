---
task: "Criar Roteiro de Reels"
order: 1
input: |
  - selected-angle.md: Ângulo editorial escolhido pelo usuário (obrigatório)
  - tone-of-voice.md: Tom de voz aprovado do squad (obrigatório)
  - company.md: Contexto da empresa e do público-alvo (obrigatório)
output: |
  - reels-script.md: Roteiro completo do Reels salvo em squads/instagram-content/output/reels-script.md
---

# Criar Roteiro de Reels

Produz um roteiro completo de Reels a partir do ângulo editorial aprovado, seguindo as regras de `instagram-reels` best-practice injetadas pelo Pipeline Runner.

## Process

1. Ler `squads/instagram-content/output/selected-angle.md` para entender ângulo, driver psicológico e tema. Ler `pipeline/data/tone-of-voice.md` e `_opensquad/_memory/company.md` para tom e contexto.
2. Escrever o gancho dos primeiros 2 segundos: texto na tela + ação/fala que crie curiosidade ou prometa valor imediato, sem introdução lenta.
3. Escrever o roteiro completo em blocos cronometrados: Setup (2-5s), Entrega (5-60s, cortes a cada 3-5s), CTA (últimos 3-5s), indicando visual, fala e texto na tela em cada bloco.
4. Projetar o final para conectar de volta ao gancho (loop visual ou narrativo).
5. Escrever a legenda (gancho nos primeiros 125 caracteres + CTA) e selecionar de 5 a 15 hashtags relevantes ao nicho.
6. Indicar direção de áudio: som em alta relevante ao tema, ou áudio original com direção de tom.

## Output Format

```
=== ROTEIRO REEL ===

GANCHO (0-2s):
[Visual]: {o que aparece na tela}
[Fala]: {palavras ditas, som em alta, ou cue de música}
[Texto na tela]: {texto que prende o espectador — máx 10 palavras}

SETUP (2-5s):
[Visual]: {cena ou transição de contexto}
[Roteiro]: {fala de contexto — 1-2 frases}

ENTREGA (5-60s):
[Visual]: {plano por plano, cortes a cada 3-5 segundos}
[Roteiro]: {fala completa da entrega}
[Textos na tela]: {pontos-chave destacados}

CTA (últimos 3-5s):
[Visual]: {quadro final ou gesto}
[Roteiro]: {fala do CTA — um pedido específico}
[Texto na tela]: {texto do CTA}

=== LEGENDA ===
{Linha de gancho — cabe em 125 caracteres}

{Contexto ou valor expandido — 2-3 linhas curtas}

{CTA — pergunta ou pedido de ação}

=== HASHTAGS ===
#hashtag1 #hashtag2 ... (5 a 15 hashtags)

=== NOTA DE ÁUDIO ===
{Sugestão de áudio em alta ou direção de áudio original}
```

## Output Example

> Use como referência de qualidade, não como modelo rígido.

```
=== ROTEIRO REEL ===

GANCHO (0-2s):
[Visual]: Terreno vazio, câmera se aproximando rápido
[Fala]: "Se você vai construir, para AGORA antes de comprar o terreno."
[Texto na tela]: "PARA antes de comprar o terreno"

SETUP (2-5s):
[Visual]: Corte para o arquiteto (ou apresentador) falando direto pra câmera
[Roteiro]: "Tem uma coisa que quase ninguém verifica antes de fechar a compra."

ENTREGA (5-25s):
[Visual]: Corte para tela dividida terreno + documento de avaliação; depois corte para plantas de projeto
[Roteiro]: "O banco não avalia só o seu crédito. Ele avalia o terreno e o projeto juntos.
Se o terreno tem alguma restrição, ou o projeto não encaixa no que o financiamento permite,
o processo trava ou sai em condição pior.
A avaliação técnica antes da compra mostra isso tudo antes de você assinar qualquer contrato."
[Textos na tela]: "Banco avalia terreno + projeto", "Avaliação técnica ANTES de comprar"

CTA (últimos 3-5s):
[Visual]: Volta para o terreno vazio do início, agora com uma marcação de "aprovado"
[Roteiro]: "Comenta AVALIAÇÃO que eu te explico como pedir esse laudo."
[Texto na tela]: "Comenta AVALIAÇÃO 👇"

=== LEGENDA ===
Para antes de comprar o terreno. Sério.

O banco avalia terreno e projeto juntos, e isso pode travar seu financiamento se ninguém checar antes.

Você já ouviu falar da avaliação técnica antes de comprar? Comenta aqui embaixo.

=== HASHTAGS ===
#financiamentoimobiliario #construirdocomecoaofim #arquiteturamacapa #avaliacaodeimoveis #casapropria #arquiteturaresidencial

=== NOTA DE ÁUDIO ===
Áudio original (fala direta para câmera). Se houver som em alta de tom "revelação/alerta" compatível com o gancho, usar como camada de fundo em volume baixo durante a Entrega.
```

## Quality Criteria

- [ ] Gancho nos 2 primeiros segundos sem introdução lenta
- [ ] Todos os blocos indicam texto na tela
- [ ] Duração projetada entre 15 e 30 segundos
- [ ] CTA final é específico e acionável
- [ ] Direção de áudio está explícita

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. O gancho começa com saudação, logo ou introdução genérica em vez de ir direto ao ponto.
2. O roteiro promete resultado de aprovação de crédito como garantia.
