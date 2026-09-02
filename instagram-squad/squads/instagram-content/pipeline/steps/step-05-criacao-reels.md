---
execution: subagent
agent: criador-reels
format: instagram-reels
inputFile: squads/instagram-content/output/selected-angle.md
outputFile: squads/instagram-content/output/reels-script.md
model_tier: powerful
---

# Step 5: Criação de Conteúdo — Instagram Reels

## Context Loading

Carregar antes de executar:
- `squads/instagram-content/output/selected-angle.md` — ângulo, driver psicológico e tema aprovados no Step 3
- `pipeline/data/tone-of-voice.md` — tom de voz educativo do squad
- `_opensquad/_memory/company.md` — contexto da César Couto Arquitetura
- Regras de `instagram-reels` (injetadas automaticamente pelo Pipeline Runner via o campo `format` deste step)

## Instructions

### Process

1. Executar a tarefa `criar-roteiro-reels.md` do agente: escrever o gancho dos 2 primeiros segundos sem introdução lenta.
2. Escrever o roteiro completo em blocos cronometrados (Gancho, Setup, Entrega, CTA), com texto na tela em todos os blocos e cortes a cada 3-5 segundos na Entrega.
3. Projetar o final para conectar de volta ao gancho (loop) e indicar direção de áudio.

## Output Format

```
=== ROTEIRO REEL ===
GANCHO (0-2s): [Visual] [Fala] [Texto na tela]
SETUP (2-5s): [Visual] [Roteiro]
ENTREGA (5-60s): [Visual] [Roteiro] [Textos na tela]
CTA (últimos 3-5s): [Visual] [Roteiro] [Texto na tela]

=== LEGENDA ===
[Gancho + contexto + CTA]

=== HASHTAGS ===
[5-15 hashtags]

=== NOTA DE ÁUDIO ===
[Direção de áudio]
```

## Output Example

```
=== ROTEIRO REEL ===

GANCHO (0-2s):
[Visual]: Terreno vazio, câmera se aproximando rápido
[Fala]: "Se você vai construir, para AGORA antes de comprar o terreno."
[Texto na tela]: "PARA antes de comprar o terreno"

SETUP (2-5s):
[Visual]: Corte para o arquiteto falando direto pra câmera
[Roteiro]: "Tem uma coisa que quase ninguém verifica antes de fechar a compra."

ENTREGA (5-25s):
[Visual]: Tela dividida terreno + documento de avaliação; depois corte para plantas de projeto
[Roteiro]: "O banco não avalia só o seu crédito. Ele avalia o terreno e o projeto juntos.
Se o terreno tem restrição, ou o projeto não encaixa no financiamento, o processo trava.
A avaliação técnica antes da compra mostra isso tudo antes de você assinar qualquer contrato."
[Textos na tela]: "Banco avalia terreno + projeto", "Avaliação técnica ANTES de comprar"

CTA (últimos 3-5s):
[Visual]: Volta para o terreno do início, agora com marcação de "aprovado"
[Roteiro]: "Comenta a palavra AVALIAÇÃO que eu te explico como pedir esse laudo."
[Texto na tela]: "Comenta AVALIAÇÃO 👇"

=== LEGENDA ===
Para antes de comprar o terreno. Sério.

O banco avalia terreno e projeto juntos, e isso pode travar seu financiamento se ninguém checar antes.

Você já ouviu falar da avaliação técnica antes de comprar?

=== HASHTAGS ===
#financiamentoimobiliario #construirdocomecoaofim #arquiteturamacapa #avaliacaodeimoveis #casapropria #arquiteturaresidencial

=== NOTA DE ÁUDIO ===
Áudio original (fala direta para câmera). Se houver som em alta de tom "revelação/alerta" compatível, usar em volume baixo durante a Entrega.
```

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. O gancho começa com saudação, logo ou introdução genérica em vez de ir direto ao ponto.
2. O roteiro promete resultado de aprovação de crédito como garantia.

## Quality Criteria

- [ ] Gancho entrega curiosidade/valor nos primeiros 2 segundos
- [ ] Todos os blocos indicam texto na tela
- [ ] Duração projetada entre 15 e 30 segundos, com direção de áudio explícita
