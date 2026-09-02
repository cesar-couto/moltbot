---
task: "Pesquisar Tendências e Ângulos"
order: 1
input: |
  - tema: Tema/foco da pesquisa definido pelo usuário no checkpoint (obrigatório)
  - intervalo_tempo: Janela temporal da pesquisa — 24h / 7 dias / 1 mês / evergreen (obrigatório)
output: |
  - research-brief.md: Brief estruturado com achados, ângulos e lacunas, salvo em squads/instagram-content/output/research-brief.md
---

# Pesquisar Tendências e Ângulos

Pesquisa o tema focal dentro do nicho de arquitetura residencial e financiamento imobiliário de lote + construção, e devolve um brief com achados verificados mais 3 a 5 ângulos editoriais distintos sobre o MESMO tema, para o usuário escolher no checkpoint seguinte.

## Process

1. Ler `squads/instagram-content/output/research-focus.md` para confirmar tema e intervalo de tempo. Se o tema estiver ambíguo, restringir o escopo à interpretação mais provável dado o perfil da empresa em `_opensquad/_memory/company.md` e declarar essa interpretação no início do brief.
2. Rodar uma varredura focada com WebSearch/WebFetch: 5 a 10 fontes candidatas sobre o tema, priorizando fontes em português, brasileiras, e dentro do intervalo de tempo pedido. Preferir fontes primárias (associações do setor, bancos/Caixa/bancos privados sobre financiamento, CAU/CREA, dados oficiais) sobre blogs genéricos de marketing.
3. Selecionar as 3 a 5 fontes mais relevantes e extrair achados específicos — nunca genéricos. Cada achado leva fonte, URL, data de publicação, data de acesso e nível de confiança (alta: 2+ fontes concordam; média: 1 fonte sólida; baixa: fonte única ou dado desatualizado).
4. A partir dos achados, gerar de 3 a 5 ângulos editoriais sobre o MESMO tema. Cada ângulo usa um driver psicológico diferente (medo de errar/perder oportunidade, desejo de status, prova social, educacional/curiosidade, contrário a uma crença comum). Nunca gerar ângulos que sejam, na prática, temas diferentes.
5. Documentar lacunas: o que não foi possível confirmar com uma fonte confiável dentro do intervalo de tempo pedido.

## Output Format

```yaml
tema: "{tema pesquisado, conforme confirmado no passo 1}"
intervalo_tempo: "{intervalo usado na pesquisa}"
achados:
  - achado: "{afirmação objetiva}"
    fonte: "{nome da fonte}"
    url: "{url}"
    data_publicacao: "{data ou 'não informada'}"
    data_acesso: "{YYYY-MM-DD}"
    confianca: "alta | média | baixa"
angulos:
  - nome: "{nome curto do ângulo}"
    driver: "{driver psicológico}"
    resumo: "{a perspectiva em 1-2 frases}"
    porque_funciona: "{1 frase sobre por que esse ângulo ressoa com o público de médio-alto padrão da César Couto Arquitetura}"
lacunas:
  - "{o que não foi encontrado ou não pôde ser confirmado}"
```

## Output Example

> Use como referência de qualidade, não como modelo rígido.

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
  - achado: "Conteúdo de bastidor de obra (fotos e vídeos reais do canteiro) funciona como prova social e reduz a objeção de confiança natural em um investimento de alto valor, especialmente para público de médio-alto padrão."
    fonte: "Pássaro Digital — Estratégias para arquitetos"
    url: "https://passarodigital.com.br/2024/03/18/estrategias-para-arquitetos-atrairem-clientes-de-alto-padrao-no-instagram/"
    data_publicacao: "2024-03-18"
    data_acesso: "2026-03-01"
    confianca: "média"
angulos:
  - nome: "O medo de travar no banco"
    driver: "medo de perder o terreno/condição de crédito"
    resumo: "Mostrar o erro comum de comprar o terreno antes de entender a exigência técnica do banco, e como isso trava ou encarece o financiamento depois."
    porque_funciona: "Ativa medo de perda em quem já tem ou está de olho num terreno, gerando urgência de buscar orientação técnica antes de avançar."
  - nome: "O processo passo a passo, sem mistério"
    driver: "educacional/redução de incerteza"
    resumo: "Explicar de forma simples as etapas entre 'escolher o terreno' e 'primeira liberação de recurso', desmistificando a burocracia."
    porque_funciona: "Público de médio-alto padrão valoriza entender o processo antes de comprometer capital; reduz a insegurança que impede a decisão."
  - nome: "Bastidor de uma aprovação real"
    driver: "prova social"
    resumo: "Contar, sem expor dados do cliente, a jornada real de um projeto que passou pela avaliação técnica e teve o crédito liberado por etapas."
    porque_funciona: "Prova social concreta reduz a objeção de confiança típica em investimentos altos, conforme achado de pesquisa."
  - nome: "O mito de que projeto e crédito são etapas separadas"
    driver: "contrário a uma crença comum"
    resumo: "Desconstruir a ideia de que primeiro se aprova o crédito e depois se pensa no projeto — na prática as duas coisas andam juntas."
    porque_funciona: "Gera debate e comentários por confrontar uma crença difundida, além de posicionar a César Couto Arquitetura como quem domina as duas pontas do processo."
lacunas:
  - "Não foi possível confirmar, com fonte pública recente, taxas de juros ou prazos específicos atualizados para financiamento de lote+construção — esse dado deve vir do agente financeiro/banco parceiro, não deve ser afirmado no conteúdo."
```

## Quality Criteria

- [ ] Todos os achados citam fonte, URL, data de acesso e nível de confiança
- [ ] Os ângulos propostos usam drivers psicológicos distintos entre si
- [ ] Nenhum ângulo é, na prática, um tema diferente do tema pesquisado
- [ ] Lacunas de pesquisa são declaradas explicitamente
- [ ] O brief respeita o intervalo de tempo definido pelo usuário

## Veto Conditions

Rejeitar e refazer se QUALQUER uma for verdadeira:

1. Algum achado é apresentado como fato sem fonte rastreável.
2. Dois ou mais ângulos usam essencialmente o mesmo driver psicológico e a mesma perspectiva com palavras diferentes.
