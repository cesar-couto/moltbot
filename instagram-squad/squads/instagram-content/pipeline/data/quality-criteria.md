# Quality Criteria — Squad "instagram-content"

Critérios usados pelo Revisor (Vinícius Vistoria) no Step 9, e referência para os demais agentes durante a criação.

## Critérios Globais (aplicam-se a todos os formatos)

1. **Fidelidade ao ângulo aprovado** — o conteúdo reflete o ângulo e o driver psicológico escolhidos no Step 3, sem desviar para outro tema ou emoção.
2. **Tom de voz (educativo)** — o conteúdo segue o tom definido em `pipeline/data/tone-of-voice.md`, nem formal-frio demais, nem vendedor-agressivo demais.
3. **Precisão técnica / sem promessas indevidas** — nenhuma promessa de aprovação de crédito, taxa ou prazo de financiamento como garantia. Vocabulário técnico (financiamento de lote e construção, avaliação técnica, perícia) usado corretamente.
4. **CTA e fechamento** — todo formato termina com uma ação específica e acionável, nunca um "saiba mais" genérico.

## Critérios por Formato

### Instagram Feed
- Formato de carrossel escolhido combina com o driver do ângulo.
- Cada slide tem entre 40 e 80 palavras, com headline em destaque + texto de apoio.
- Legenda entrega valor nos primeiros 125 caracteres.
- Entre 5 e 15 hashtags, sem spam.

### Instagram Reels
- Gancho nos 2 primeiros segundos, sem introdução lenta.
- Texto na tela presente em todos os blocos do roteiro.
- Duração projetada entre 15 e 30 segundos.
- Final projetado para loop (visual ou narrativo).

### Instagram Stories
- Sequência entre 3 e 7 frames.
- Pelo menos um elemento interativo com prompt específico.
- Nenhum frame excede 3 linhas de texto.
- Tom claramente mais informal que Feed e Reels.

### Design Visual
- Design system documentado (máximo 5 cores, valores exatos em hex) antes de qualquer slide individual.
- Nenhum texto abaixo dos mínimos de fonte da plataforma (58/43/34/24px para carrossel).
- HTML autocontido, sem dependência externa além de Google Fonts.
- Nenhum contador de slide ("3/7") presente no design.

## Regras de Decisão do Veredito

| Condição | Veredito |
|---|---|
| Média geral ≥ 7/10 e nenhum critério < 4/10 | APROVADO |
| Média geral ≥ 7/10, mas algum critério não-crítico entre 4-6/10 | APROVADO CONDICIONAL |
| Média geral < 7/10 | REJEITADO |
| Qualquer critério < 4/10 | REJEITADO (gatilho automático) |
| Promessa de resultado de crédito/financiamento presente em qualquer formato | REJEITADO (gatilho automático, independente da média) |
| 3+ ciclos de revisão com os mesmos problemas recorrentes | ESCALAR para decisão do usuário |
