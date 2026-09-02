---
type: checkpoint
outputFile: squads/instagram-content/output/selected-angle.md
---

# Step 3: Checkpoint — Seleção de Ângulo

## O que fazer

1. Ler `squads/instagram-content/output/research-brief.md` e apresentar ao usuário os ângulos propostos pela Bianca Bússola, usando `AskUserQuestion` como lista de opções (cada ângulo é uma opção, com o resumo e o driver psicológico na descrição).
2. Se houver mais de 4 ângulos, priorizar os 3-4 mais fortes na pergunta e mencionar que os demais estão disponíveis no brief completo (`output/research-brief.md`) caso o usuário prefira outro.
3. Registrar a escolha do usuário no arquivo de saída, incluindo o resumo e o driver do ângulo escolhido (copiado do brief), para que os três criadores de conteúdo (Feed, Reels, Stories) tenham o mesmo insumo.

## Formato do arquivo de saída

```markdown
# Ângulo Selecionado

**Nome do ângulo:** {nome}
**Driver psicológico:** {driver}
**Resumo:** {resumo do brief}
**Por que funciona:** {justificativa do brief}
**Tema original:** {tema pesquisado no Step 2}

**Data da escolha:** {YYYY-MM-DD}
```

## Regras

- Nunca prosseguir para a criação de conteúdo (Step 4) sem essa escolha explícita do usuário.
- Se o usuário pedir para combinar elementos de dois ângulos, registrar a combinação no arquivo de saída como um ângulo único e coerente, mantendo apenas um driver psicológico dominante (nunca misturar dois drivers no mesmo conteúdo).
