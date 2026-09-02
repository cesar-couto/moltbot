---
type: checkpoint
outputFile: squads/instagram-content/output/research-focus.md
---

# Step 1: Checkpoint — Foco da Pesquisa

Este é o primeiro passo do squad. Antes de a Bianca Bússola (pesquisadora) começar a trabalhar, o usuário define o tema e o intervalo de tempo desta rodada de conteúdo.

## O que fazer

1. Mostrar rapidamente o contexto do squad: propósito ("gerar conteúdo educativo para Instagram sobre construção via financiamento imobiliário e arquitetura residencial") e o nome da empresa (`_opensquad/_memory/company.md` → César Couto Arquitetura).
2. Perguntar (texto livre), usando `AskUserQuestion` com exemplos como opções e "Other" para resposta livre:
   > "Qual o foco específico da pesquisa de hoje? Exemplo: 'financiamento de lote e construção', 'avaliação técnica de imóveis', 'erros comuns na aprovação do projeto pelo banco'. Qual é o tema?"
3. Perguntar o intervalo de tempo da pesquisa, como lista numerada:
   1. Últimas 24 horas
   2. Últimos 7 dias
   3. Último mês
   4. Sem restrição de tempo (evergreen)
4. Escrever a resposta combinada no arquivo de saída antes de prosseguir para o Step 2.

## Formato do arquivo de saída

```markdown
# Foco da Pesquisa

**Tema:** {tema informado pelo usuário}
**Intervalo de tempo:** {opção escolhida}
**Data do checkpoint:** {YYYY-MM-DD}
```

## Regras

- Nunca pular este checkpoint — o agente pesquisador roda como subagent e não pode perguntar nada sozinho.
- Se o usuário não tiver um tema específico em mente, sugerir 2-3 exemplos do nicho (financiamento de lote e construção, avaliação técnica, mitos sobre aprovação de crédito) como ponto de partida, mas deixar a decisão final com o usuário.
