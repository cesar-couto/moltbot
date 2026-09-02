---
task: "Revisar Conteúdo"
order: 1
input: |
  - feed-content.md: Carrossel de Feed produzido (obrigatório)
  - reels-script.md: Roteiro de Reels produzido (obrigatório)
  - stories-sequence.md: Sequência de Stories produzida (obrigatório)
  - design-manifest.md: Slides visuais gerados (obrigatório)
  - quality-criteria.md: Critérios de qualidade do squad (obrigatório)
output: |
  - review.md: Veredito estruturado com pontuação, feedback e correções, salvo em squads/instagram-content/output/review.md
---

# Revisar Conteúdo

Avalia os três formatos de conteúdo e os slides visuais contra os critérios de qualidade do squad, produzindo um veredito estruturado.

## Process

1. Carregar `pipeline/data/quality-criteria.md` e entender o que "bom" significa antes de avaliar qualquer conteúdo.
2. Ler por completo, do início ao fim, os quatro entregáveis (feed-content.md, reels-script.md, stories-sequence.md, design-manifest.md) antes de pontuar qualquer critério.
3. Pontuar cada critério individualmente de 1 a 10 com justificativa. Nunca deixar uma boa nota em um critério compensar uma nota ruim em outro — cada critério é independente.
4. Identificar a localização exata (slide, bloco, frame) de cada observação, positiva ou negativa.
5. Calcular o veredito: APROVADO se média geral ≥ 7/10 e nenhum critério < 4/10; APROVADO CONDICIONAL se média ≥ 7/10 mas algum critério não-crítico entre 4-6/10; REJEITADO se média < 7/10 ou qualquer critério < 4/10 (gatilho de rejeição automática).
6. Se REJEITADO, listar o caminho para aprovação: lista numerada de correções obrigatórias.

## Output Format

```
==============================
 VEREDITO DA REVISÃO: {APROVADO | APROVADO CONDICIONAL | REJEITADO}
==============================

Squad: instagram-content
Data da revisão: {YYYY-MM-DD}
Revisão: {N} de 3

------------------------------
 TABELA DE PONTUAÇÃO
------------------------------
| Critério                        | Nota   | Resumo                                    |
|----------------------------------|--------|-------------------------------------------|
| Fidelidade ao ângulo aprovado    | X/10   | ...                                        |
| Tom de voz (educativo)           | X/10   | ...                                        |
| Qualidade do gancho (3 formatos) | X/10   | ...                                        |
| Precisão técnica / sem promessas indevidas | X/10 | ...                              |
| CTA e fechamento                 | X/10   | ...                                        |
| Qualidade visual dos slides      | X/10   | ...                                        |
------------------------------
 MÉDIA GERAL: X/10
------------------------------

FEEDBACK DETALHADO:

Ponto forte: {observação específica}

Correção obrigatória: {o que está errado, onde, e como corrigir}

Sugestão (não bloqueante): {melhoria recomendada}

CAMINHO PARA APROVAÇÃO (se REJEITADO):
1. {correção específica}
2. {correção específica}

VEREDITO: {APROVADO/REJEITADO} — {resumo de uma frase}
```

## Output Example

> Use como referência de qualidade, não como modelo rígido.

```
==============================
 VEREDITO DA REVISÃO: APROVADO CONDICIONAL
==============================

Squad: instagram-content
Data da revisão: 2026-03-01
Revisão: 1 de 3

------------------------------
 TABELA DE PONTUAÇÃO
------------------------------
| Critério                        | Nota   | Resumo                                       |
|----------------------------------|--------|----------------------------------------------|
| Fidelidade ao ângulo aprovado    | 9/10   | Os três formatos seguem o ângulo "ordem certa antes de comprar" com consistência |
| Tom de voz (educativo)           | 8/10   | Tom educativo mantido; Reels ligeiramente mais vendedor no CTA final |
| Qualidade do gancho (3 formatos) | 8/10   | Gancho do Feed e Reels fortes; Stories abre bem mas frame 2 é redundante com o Feed |
| Precisão técnica / sem promessas indevidas | 9/10 | Nenhuma promessa de aprovação de crédito encontrada |
| CTA e fechamento                 | 6/10   | Feed e Stories têm CTA específico; Reels usa "comenta AVALIAÇÃO" mas não reforça no texto na tela |
| Qualidade visual dos slides      | 8/10   | Design system consistente; fonte do slide 4 está a 32px, abaixo do mínimo de corpo (34px) |
------------------------------
 MÉDIA GERAL: 8.0/10
------------------------------

FEEDBACK DETALHADO:

Ponto forte: O ângulo "avaliação técnica antes de comprar o terreno" está muito bem amarrado entre os três formatos, o que reforça a mensagem sem repetir a mesma frase.

Ponto forte: Nenhum dos três formatos promete aprovação de crédito ou prazo específico, respeitando a regra da empresa sobre não garantir resultado financeiro.

Correção obrigatória: No slide 4 do carrossel (design-manifest.md), o corpo de texto está definido a 32px. O mínimo de corpo para carrossel do Instagram é 34px. Ajustar o CSS do slide-04.html para `font-size: 36px` (mesmo valor usado nos demais slides) antes da aprovação final.

Correção obrigatória: No roteiro de Reels, o texto na tela do bloco de CTA repete apenas "Comenta AVALIAÇÃO 👇" mas a fala não reforça a mesma palavra-chave. Ajustar a fala do CTA para "Comenta a palavra AVALIAÇÃO que eu te explico" para reforçar a ação em áudio e texto.

Sugestão (não bloqueante): No frame 2 dos Stories, o texto é quase idêntico ao slide 2 do Feed. Considerar trocar por um bastidor real (foto do escritório ou de uma vistoria) para diferenciar o formato, conforme o anti-padrão "reaproveitar slide do Feed sem adaptação" do agente de Stories.

VEREDITO: APROVADO CONDICIONAL — Conteúdo pode seguir para o checkpoint de aprovação final após as duas correções obrigatórias (fonte do slide 4 e reforço de CTA no Reels).
```

## Quality Criteria

- [ ] Todos os critérios de `quality-criteria.md` foram avaliados individualmente
- [ ] Toda nota tem justificativa específica com localização exata
- [ ] O veredito é consistente com as notas (sem contradição entre pontuação e veredito)
- [ ] Toda rejeição ou aprovação condicional lista correções acionáveis
- [ ] Pelo menos um "Ponto forte" está presente mesmo em revisões com correções obrigatórias

## Veto Conditions

Rejeitar e refazer a própria revisão se QUALQUER uma for verdadeira:

1. Algum critério recebeu nota sem justificativa por escrito.
2. O veredito final contradiz as notas individuais (ex: critério abaixo de 4/10 mas veredito é APROVADO).
