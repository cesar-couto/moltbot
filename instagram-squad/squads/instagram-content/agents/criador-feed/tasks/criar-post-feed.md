---
task: "Criar Post de Feed"
order: 1
input: |
  - selected-angle.md: Ângulo editorial escolhido pelo usuário (obrigatório)
  - tone-of-voice.md: Tom de voz aprovado do squad (obrigatório)
  - company.md: Contexto da empresa e do público-alvo (obrigatório)
output: |
  - feed-content.md: Carrossel completo (formato, slides, legenda, hashtags) salvo em squads/instagram-content/output/feed-content.md
---

# Criar Post de Feed

Produz um carrossel completo para o Feed do Instagram a partir do ângulo editorial aprovado, seguindo as regras de `instagram-feed` best-practice injetadas pelo Pipeline Runner.

## Process

1. Ler `squads/instagram-content/output/selected-angle.md` para entender o ângulo, o driver psicológico e o tema. Ler `pipeline/data/tone-of-voice.md` para confirmar o tom (educativo, conforme definido para a César Couto Arquitetura) e `_opensquad/_memory/company.md` para contexto de negócio.
2. Escolher o formato de carrossel (Editorial, Listicle, Tutorial, Mito vs Realidade, Antes e Depois, Storytelling ou Problema→Solução) que melhor sirva ao driver psicológico do ângulo escolhido, e justificar a escolha em uma frase.
3. Escrever 3 opções de gancho para a capa, cada uma com driver estrutural diferente (pergunta provocativa, dado/estatística, afirmação contrária), com uma frase de racional cada. Escolher a mais forte e registrar a escolha.
4. Escrever todos os slides seguindo a estrutura do formato escolhido: headline em destaque + texto de apoio menor, 40 a 80 palavras por slide, alternando fundo claro/escuro/destaque a cada 2-3 slides.
5. Escrever a legenda: gancho nos primeiros 125 caracteres, corpo com quebras de linha curtas, fechamento com pergunta ou CTA específico.
6. Selecionar de 5 a 15 hashtags misturando nicho (arquitetura, financiamento imobiliário, Macapá/AP) e alcance médio.

## Output Format

```
=== GANCHOS AVALIADOS ===
Gancho A ({tipo estrutural}): "{texto}" — {racional em 1 linha}
Gancho B ({tipo estrutural}): "{texto}" — {racional em 1 linha}
Gancho C ({tipo estrutural}): "{texto}" — {racional em 1 linha}
Escolhido: {A/B/C} — {por que}

=== FORMATO ===
{Editorial | Listicle | Tutorial | Mito vs Realidade | Antes e Depois | Storytelling | Problema→Solução}

=== SLIDES ===
Slide 1 (Capa):
  Título: {gancho escolhido, máx 20 palavras}
  Foto: {direção de foto/render}
  Fundo: {cover photo / cor sólida}

Slide 2 ({papel do slide}):
  Headline: {texto grande}
  Foto: {direção, se aplicável}
  Texto de apoio: {texto menor — dado, contexto ou elaboração}
  Palavras em destaque: {palavras para cor de destaque}
  Fundo: {claro/escuro/destaque}

... continuar até o slide final (CTA) ...

Slide N (CTA):
  Foto: {imagem de fechamento}
  CTA: {ação específica — comentar palavra-chave, salvar, compartilhar}

=== LEGENDA ===
{Parágrafo de gancho — primeiros 125 caracteres compelem o "...mais"}

{Corpo — argumento expandido, quebras de linha curtas}

{Pergunta de fechamento — provocativa, aberta}

=== HASHTAGS ===
#hashtag1 #hashtag2 #hashtag3 ... (5 a 15 hashtags)
```

## Output Example

> Use como referência de qualidade, não como modelo rígido.

```
=== GANCHOS AVALIADOS ===
Gancho A (Pergunta provocativa): "Você sabia que dá pra financiar o terreno E a construção da sua casa numa operação só?" — Ativa curiosidade em quem acha que precisa fazer dois financiamentos separados.
Gancho B (Afirmação contrária): "Comprar o terreno antes de falar com um arquiteto pode travar o seu financiamento." — Cria tensão cognitiva ao contrariar a ordem que a maioria segue.
Gancho C (Dado): "9 em cada 10 pessoas que querem construir não sabem como funciona a liberação de crédito por etapa." — Estatística cria autoridade, mas achado não foi confirmado com fonte forte nesta pesquisa.
Escolhido: B — usa o driver de medo de perda de forma honesta (sem estatística não confirmada) e conecta direto com o serviço de avaliação técnica da César Couto Arquitetura.

=== FORMATO ===
Problema → Solução (7 slides)

=== SLIDES ===
Slide 1 (Capa):
  Título: Comprar o terreno antes de falar com um arquiteto pode travar o seu financiamento.
  Foto: Foto de um terreno vazio, luz de fim de tarde, ângulo baixo
  Fundo: cover photo com overlay escuro

Slide 2 (Problema):
  Headline: O erro mais comum de quem quer construir
  Texto de apoio: A maioria compra o terreno primeiro e só depois procura orientação técnica. O problema é que o banco avalia o terreno E o projeto juntos antes de liberar o crédito.
  Palavras em destaque: avalia, juntos
  Fundo: escuro

Slide 3 (Problema):
  Headline: O resultado? Financiamento travado ou condição pior
  Texto de apoio: Terreno em área com restrição, documentação incompleta ou projeto fora do padrão exigido: qualquer um desses pontos pode atrasar meses a liberação do seu crédito.
  Palavras em destaque: travado, meses
  Fundo: claro

Slide 4 (Ponte):
  Headline: Existe uma ordem certa para isso
  Texto de apoio: Antes de fechar a compra do terreno, dá pra saber se ele serve para o seu projeto e para o financiamento que você quer.
  Palavras em destaque: ordem certa
  Fundo: destaque

Slide 5 (Solução):
  Headline: Avaliação técnica antes da compra
  Texto de apoio: Um laudo de avaliação e perícia do imóvel mostra, antes de você assinar qualquer contrato, se aquele terreno é viável para o projeto e para o crédito.
  Palavras em destaque: antes de você assinar
  Fundo: claro

Slide 6 (Solução):
  Headline: Projeto pensado junto com o crédito
  Texto de apoio: O projeto de arquitetura já nasce dentro do que o financiamento de lote e construção permite, etapa por etapa.
  Palavras em destaque: etapa por etapa
  Fundo: escuro

Slide 7 (CTA):
  Foto: Foto de projeto residencial finalizado, fachada
  CTA: Comenta AVALIAÇÃO que eu te explico como funciona esse laudo técnico

=== LEGENDA ===
Comprar o terreno antes de falar com um arquiteto pode travar o seu financiamento. Ninguém te conta isso antes.

A ordem que a maioria segue é: acha o terreno, compra, só depois procura projeto e crédito.
O problema é que o banco avalia terreno e projeto juntos.

Se um dos dois não bate, o financiamento trava ou sai em condição pior.

Dá pra evitar isso com uma avaliação técnica antes de assinar qualquer contrato.

Você já passou (ou conhece alguém que passou) por esse perrengue de financiamento travado?

=== HASHTAGS ===
#financiamentoimobiliario #construirdocomecoaofim #arquiteturamacapa #casapropria #avaliacaodeimoveis #financiamentodeterreno #arquiteturaresidencial #macapaap
```

## Quality Criteria

- [ ] Três ganchos foram avaliados com racional e um foi escolhido explicitamente
- [ ] Formato de carrossel escolhido combina com o driver psicológico do ângulo
- [ ] Cada slide tem entre 40 e 80 palavras com headline + texto de apoio
- [ ] Legenda entrega valor nos primeiros 125 caracteres e fecha com pergunta/CTA
- [ ] Entre 5 e 15 hashtags relevantes ao nicho

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. O conteúdo promete resultado de aprovação de crédito ou taxa/prazo específico não confirmado pela pesquisa.
2. Algum slide tem menos de 40 ou mais de 80 palavras sem justificativa explícita do usuário para slides curtos.
