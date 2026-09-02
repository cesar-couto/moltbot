---
type: checkpoint
---

# Step 10: Checkpoint — Aprovação Final

## O que fazer

1. Apresentar o veredito de `squads/instagram-content/output/review.md` e a lista de entregáveis finais:
   - `output/feed-content.md` (+ `output/slides/*.html`)
   - `output/reels-script.md`
   - `output/stories-sequence.md`
2. Se o veredito foi APROVADO CONDICIONAL, confirmar com o usuário que as correções obrigatórias listadas na revisão foram aplicadas antes de fechar o run.
3. Perguntar, via `AskUserQuestion`:
   1. Aprovar e encerrar este run — conteúdo pronto para publicação manual
   2. Pedir mais uma rodada de ajustes (volta ao Step 4)
4. Ao aprovar, registrar o resultado em `_memory/runs.md` (data, tema pesquisado, formatos gerados, resultado) e atualizar `_memory/memories.md` com aprendizados relevantes desta rodada (o que funcionou no gancho, no ângulo, no design).

## Regras

- Este é o último checkpoint do pipeline — depois dele o squad não executa nenhuma ação adicional automaticamente (não publica, não agenda; a publicação em si é manual ou via skill `instagram-publisher`, que não está incluída neste squad por padrão).
- Nunca marcar o run como concluído em `_memory/runs.md` sem a aprovação explícita do usuário neste checkpoint.
