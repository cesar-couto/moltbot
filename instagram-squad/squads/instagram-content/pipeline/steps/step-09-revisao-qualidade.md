---
execution: subagent
agent: revisor-qualidade
inputFile: squads/instagram-content/output/design-manifest.md
outputFile: squads/instagram-content/output/review.md
model_tier: powerful
---

# Step 9: Revisão de Qualidade

## Context Loading

Carregar antes de executar:
- `squads/instagram-content/output/feed-content.md`, `.../reels-script.md`, `.../stories-sequence.md`, `.../design-manifest.md` — todos os entregáveis produzidos até aqui
- `pipeline/data/quality-criteria.md` — critérios de avaliação do squad
- `_opensquad/_memory/company.md` — regras de negócio (ex: nunca prometer resultado de financiamento)

## Instructions

### Process

1. Executar a tarefa `revisar-conteudo.md` do agente: ler todos os entregáveis por completo antes de pontuar.
2. Pontuar cada critério de `quality-criteria.md` individualmente, com justificativa e localização exata das observações.
3. Calcular o veredito (APROVADO / APROVADO CONDICIONAL / REJEITADO) segundo as regras de decisão (rejeição automática se qualquer critério < 4/10 ou média < 7/10).

## Output Format

```
==============================
 VEREDITO DA REVISÃO: {APROVADO | APROVADO CONDICIONAL | REJEITADO}
==============================
[Tabela de pontuação, feedback detalhado, caminho para aprovação se REJEITADO]
```

## Output Example

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
| Fidelidade ao ângulo aprovado    | 9/10   | Os três formatos seguem o ângulo com consistência |
| Tom de voz (educativo)           | 8/10   | Tom mantido; Reels ligeiramente mais vendedor no CTA |
| Qualidade do gancho (3 formatos) | 8/10   | Gancho do Feed e Reels fortes; Stories frame 2 redundante com o Feed |
| Precisão técnica / sem promessas indevidas | 9/10 | Nenhuma promessa de aprovação de crédito encontrada |
| CTA e fechamento                 | 6/10   | Reels usa "comenta AVALIAÇÃO" mas não reforça no texto na tela |
| Qualidade visual dos slides      | 8/10   | Design consistente; fonte do slide 4 está a 32px, abaixo do mínimo (34px) |
------------------------------
 MÉDIA GERAL: 8.0/10
------------------------------

FEEDBACK DETALHADO:

Ponto forte: O ângulo está muito bem amarrado entre os três formatos, reforçando a mensagem sem repetir a mesma frase.

Ponto forte: Nenhum dos três formatos promete aprovação de crédito ou prazo específico.

Correção obrigatória: No slide 4 do carrossel, o corpo de texto está a 32px. O mínimo de corpo é 34px. Ajustar o CSS do slide-04.html para `font-size: 36px`.

Correção obrigatória: No roteiro de Reels, reforçar a palavra AVALIAÇÃO também na fala do CTA, não só no texto na tela.

Sugestão (não bloqueante): No frame 2 dos Stories, trocar o texto quase idêntico ao Feed por um bastidor real.

VEREDITO: APROVADO CONDICIONAL — Segue para o checkpoint final após as duas correções obrigatórias.
```

## Veto Conditions

Rejeitar e refazer a própria revisão se QUALQUER uma for verdadeira:

1. Algum critério recebeu nota sem justificativa por escrito.
2. O veredito final contradiz as notas individuais.

## Quality Criteria

- [ ] Todos os critérios de `quality-criteria.md` foram avaliados
- [ ] Toda rejeição ou aprovação condicional lista correções acionáveis
- [ ] Pelo menos um "Ponto forte" está presente mesmo com correções obrigatórias

## Regra de Rejeição do Pipeline

Se o veredito for REJEITADO, o pipeline volta ao **Step 4** (recriação completa dos três formatos de conteúdo — não apenas ajustes pontuais). Após 3 ciclos de revisão com os mesmos problemas recorrentes, escalar para decisão do usuário em vez de reprovar indefinidamente.
