---
execution: subagent
agent: criador-feed
format: instagram-feed
inputFile: squads/instagram-content/output/selected-angle.md
outputFile: squads/instagram-content/output/feed-content.md
model_tier: powerful
---

# Step 4: Criação de Conteúdo — Instagram Feed

## Context Loading

Carregar antes de executar:
- `squads/instagram-content/output/selected-angle.md` — ângulo, driver psicológico e tema aprovados no Step 3
- `pipeline/data/tone-of-voice.md` — tom de voz educativo do squad
- `_opensquad/_memory/company.md` — contexto da César Couto Arquitetura
- Regras de `instagram-feed` (injetadas automaticamente pelo Pipeline Runner via o campo `format` deste step)

## Instructions

### Process

1. Executar a tarefa `criar-post-feed.md` do agente: escolher o formato de carrossel mais adequado ao driver do ângulo, avaliar 3 ganchos e escolher um.
2. Escrever todos os slides com hierarquia de duas camadas (headline + texto de apoio), 40-80 palavras cada, alternando fundo a cada 2-3 slides.
3. Escrever a legenda (gancho nos primeiros 125 caracteres + fechamento com pergunta/CTA) e selecionar 5-15 hashtags.

## Output Format

```
=== GANCHOS AVALIADOS ===
[3 opções com racional e escolha]

=== FORMATO ===
[Formato de carrossel escolhido]

=== SLIDES ===
[Um bloco por slide: Título/Headline, Foto, Texto de apoio, Palavras em destaque, Fundo]

=== LEGENDA ===
[Gancho + corpo + pergunta de fechamento]

=== HASHTAGS ===
[5-15 hashtags]
```

## Output Example

```
=== GANCHOS AVALIADOS ===
Gancho A (Pergunta provocativa): "Você sabia que dá pra financiar o terreno E a construção da sua casa numa operação só?" — ativa curiosidade em quem acha que precisa de dois financiamentos.
Gancho B (Afirmação contrária): "Comprar o terreno antes de falar com um arquiteto pode travar o seu financiamento." — cria tensão ao contrariar a ordem que a maioria segue.
Gancho C (Dado): "9 em cada 10 pessoas que querem construir não sabem como funciona a liberação por etapa." — estatística não confirmada pela pesquisa, descartada.
Escolhido: B — usa medo de perda de forma honesta e conecta com o serviço de avaliação técnica.

=== FORMATO ===
Problema → Solução (7 slides)

=== SLIDES ===
Slide 1 (Capa):
  Título: Comprar o terreno antes de falar com um arquiteto pode travar o seu financiamento.
  Foto: Terreno vazio, luz de fim de tarde
  Fundo: cover photo com overlay escuro

Slide 2 (Problema):
  Headline: O erro mais comum de quem quer construir
  Texto de apoio: A maioria compra o terreno primeiro e só depois procura orientação técnica. O banco avalia o terreno e o projeto juntos antes de liberar o crédito.
  Fundo: escuro

Slide 3 (Problema):
  Headline: O resultado? Financiamento travado ou condição pior
  Texto de apoio: Terreno com restrição, documentação incompleta ou projeto fora do padrão exigido podem atrasar meses a liberação do crédito.
  Fundo: claro

Slide 4 (Ponte):
  Headline: Existe uma ordem certa para isso
  Texto de apoio: Antes de fechar a compra do terreno, dá pra saber se ele serve para o seu projeto e para o financiamento que você quer.
  Fundo: destaque

Slide 5 (Solução):
  Headline: Avaliação técnica antes da compra
  Texto de apoio: Um laudo de avaliação e perícia do imóvel mostra, antes de você assinar qualquer contrato, se o terreno é viável.
  Fundo: claro

Slide 6 (Solução):
  Headline: Projeto pensado junto com o crédito
  Texto de apoio: O projeto de arquitetura já nasce dentro do que o financiamento de lote e construção permite, etapa por etapa.
  Fundo: escuro

Slide 7 (CTA):
  Foto: Projeto residencial finalizado, fachada
  CTA: Comenta AVALIAÇÃO que eu te explico como funciona esse laudo técnico

=== LEGENDA ===
Comprar o terreno antes de falar com um arquiteto pode travar o seu financiamento.

A ordem que a maioria segue é: acha o terreno, compra, só depois procura projeto e crédito.
O banco avalia terreno e projeto juntos. Se um dos dois não bate, o financiamento trava.

Dá pra evitar isso com uma avaliação técnica antes de assinar qualquer contrato.

Você já passou por esse perrengue de financiamento travado?

=== HASHTAGS ===
#financiamentoimobiliario #construirdocomecoaofim #arquiteturamacapa #casapropria #avaliacaodeimoveis #financiamentodeterreno #arquiteturaresidencial #macapaap
```

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. O conteúdo promete resultado de aprovação de crédito ou taxa/prazo de financiamento não confirmado pela pesquisa.
2. Algum slide tem menos de 40 ou mais de 80 palavras sem pedido explícito do usuário para slides curtos.

## Quality Criteria

- [ ] Três ganchos foram avaliados e um foi escolhido com justificativa
- [ ] Formato de carrossel escolhido combina com o driver do ângulo
- [ ] Legenda entrega valor nos primeiros 125 caracteres e fecha com CTA específico
