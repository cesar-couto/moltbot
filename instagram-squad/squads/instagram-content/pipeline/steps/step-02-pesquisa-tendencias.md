---
execution: subagent
agent: pesquisador-tendencias
inputFile: squads/instagram-content/output/research-focus.md
outputFile: squads/instagram-content/output/research-brief.md
model_tier: powerful
---

# Step 2: Pesquisa de Tendências e Ângulos

## Context Loading

Carregar antes de executar:
- `squads/instagram-content/output/research-focus.md` — tema e intervalo de tempo definidos pelo usuário no Step 1
- `_opensquad/_memory/company.md` — contexto da César Couto Arquitetura, público-alvo e diferenciais
- `pipeline/data/domain-framework.md` — framework de pesquisa e geração de ângulos do squad

## Instructions

### Process

1. Confirmar o tema e o intervalo de tempo lidos de `research-focus.md`. Se o tema for ambíguo, restringir ao recorte mais provável dado o negócio da empresa e declarar essa interpretação no início do brief.
2. Executar a tarefa `pesquisar-tendencias-e-angulos.md` do agente: varredura focada de 5-10 fontes, seleção das 3-5 mais relevantes, extração de achados com fonte/data/confiança.
3. Gerar de 3 a 5 ângulos editoriais distintos sobre o MESMO tema, cada um com driver psicológico diferente, e documentar lacunas de pesquisa.

## Output Format

O output deve seguir exatamente esta estrutura:
```
tema: "{tema}"
intervalo_tempo: "{intervalo}"
achados:
  - achado: "..."
    fonte: "..."
    url: "..."
    data_publicacao: "..."
    data_acesso: "YYYY-MM-DD"
    confianca: "alta | média | baixa"
angulos:
  - nome: "..."
    driver: "..."
    resumo: "..."
    porque_funciona: "..."
lacunas:
  - "..."
```

## Output Example

```yaml
tema: "Como funciona o financiamento de lote + construção numa operação só"
intervalo_tempo: "evergreen (sem restrição de tempo)"
achados:
  - achado: "O financiamento de terreno e construção pode ser contratado numa única operação de crédito em alguns bancos, com liberação de recursos por etapas conforme a obra avança e é vistoriada."
    fonte: "Caixa Econômica Federal — linha Pró-Cotista/SBPE (material institucional)"
    url: "https://www.caixa.gov.br/voce/habitacao/financiamento-imoveis/construcao/Paginas/default.aspx"
    data_publicacao: "não informada"
    data_acesso: "2026-03-01"
    confianca: "alta"
  - achado: "A maior parte dos clientes que buscam construir a casa própria desiste ou atrasa o processo por não entender a etapa de aprovação técnica do projeto e da avaliação do imóvel/terreno exigida pelo banco."
    fonte: "Vobi — Blog do setor de construção"
    url: "https://www.vobi.com.br/portal-vobi-empreenda/construindo-um-instagram-de-sucesso-para-conquistar-mais-projetos-e-obras"
    data_publicacao: "2024"
    data_acesso: "2026-03-01"
    confianca: "média"
angulos:
  - nome: "O medo de travar no banco"
    driver: "medo de perder o terreno/condição de crédito"
    resumo: "Mostrar o erro comum de comprar o terreno antes de entender a exigência técnica do banco."
    porque_funciona: "Ativa medo de perda em quem já tem ou está de olho num terreno."
  - nome: "O processo passo a passo, sem mistério"
    driver: "educacional/redução de incerteza"
    resumo: "Explicar as etapas entre 'escolher o terreno' e 'primeira liberação de recurso'."
    porque_funciona: "Reduz a insegurança que impede a decisão de avançar."
  - nome: "Bastidor de uma aprovação real"
    driver: "prova social"
    resumo: "Contar a jornada real de um projeto que teve o crédito liberado por etapas."
    porque_funciona: "Reduz a objeção de confiança típica em investimentos altos."
  - nome: "O mito de que projeto e crédito são etapas separadas"
    driver: "contrário a uma crença comum"
    resumo: "Desconstruir a ideia de que primeiro se aprova o crédito e depois se pensa no projeto."
    porque_funciona: "Gera debate por confrontar uma crença difundida."
lacunas:
  - "Não foi possível confirmar taxas de juros ou prazos atualizados; esse dado deve vir do banco, não deve ser afirmado no conteúdo."
```

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. Algum achado é apresentado como fato sem fonte rastreável (URL + data de acesso).
2. Dois ou mais ângulos usam essencialmente o mesmo driver psicológico com palavras diferentes — não são opções reais de escolha.

## Quality Criteria

- [ ] O brief cobre exatamente o tema e o intervalo de tempo definidos no checkpoint anterior
- [ ] Entre 3 e 5 ângulos são propostos, cada um com driver distinto
- [ ] Lacunas de pesquisa aparecem explicitamente, mesmo que pequenas
