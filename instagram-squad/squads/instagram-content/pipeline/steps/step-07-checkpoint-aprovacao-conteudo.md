---
type: checkpoint
---

# Step 7: Checkpoint — Aprovação de Conteúdo

## O que fazer

1. Apresentar ao usuário um resumo dos três formatos produzidos: gancho escolhido do Feed, gancho do Reels, abertura dos Stories — com os caminhos dos arquivos completos (`output/feed-content.md`, `output/reels-script.md`, `output/stories-sequence.md`) para leitura na íntegra.
2. Perguntar, via `AskUserQuestion`:
   1. Aprovar os três formatos como estão — segue para o design visual do carrossel
   2. Pedir ajustes em um ou mais formatos — volta para o Step 4 (recriação completa do(s) formato(s) indicado(s))
   3. Cancelar esta rodada de conteúdo

## Regras

- Este checkpoint é obrigatório antes de qualquer etapa que gera visual ou publica conteúdo (Gate de Aprovação de Conteúdo) — nunca pular direto para o design.
- Se o usuário pedir ajuste em apenas um formato (ex.: só o Reels), reexecutar o(s) agente(s) criador(es) correspondente(s) e voltar a este checkpoint antes de prosseguir para o design.
- Se aprovado, nada precisa ser escrito em arquivo de saída — a aprovação libera a execução do Step 8.
