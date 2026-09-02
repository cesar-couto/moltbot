# Anti-Patterns — Squad "instagram-content"

Erros a evitar em qualquer etapa do pipeline, compilados da pesquisa de mercado e dos best-practices internos.

## Pesquisa e Ângulos

- **Confundir notícia com ângulo:** listar temas diferentes como se fossem "ângulos" do mesmo tema. Um ângulo é uma perspectiva emocional sobre UM tema, nunca um assunto novo.
- **Achado sem fonte:** qualquer estatística ou afirmação factual sem URL rastreável e data de acesso.
- **Ângulos repetidos com palavras diferentes:** dois "ângulos" que exploram o mesmo driver psicológico não são opções reais de escolha para o usuário.

## Criação de Conteúdo (Feed, Reels, Stories)

- **Prometer resultado de financiamento:** nenhum formato pode sugerir garantia de aprovação de crédito, taxa ou prazo — isso é decisão do banco, não da César Couto Arquitetura.
- **Escrever o corpo antes do gancho:** compromete a estrutura inteira; o gancho decide o driver e o formato do resto do conteúdo.
- **Hashtag spam:** mais de 15 hashtags, ou hashtags genéricas sem relação com o nicho, sinaliza spam ao algoritmo e ao público de alto padrão.
- **Introdução lenta em Reels:** logo, saudação ou contexto genérico nos primeiros 2 segundos derruba a retenção antes do conteúdo começar.
- **Reaproveitar conteúdo do Feed em Stories sem adaptação:** parece preguiça e desperdiça o formato mais informal e de maior frequência de postagem.
- **CTA genérico:** "saiba mais", "me segue" ou "clique no link" sem contexto específico geram muito menos ação do que um pedido concreto.

## Design Visual

- **Design ad-hoc sem sistema:** criar slides sem antes documentar cores, tipografia e espaçamento gera inconsistência visual perceptível.
- **Dependência externa no HTML:** CDN de CSS/JS ou imagem hospedada fora do arquivo quebra a renderização isolada do motor de captura de tela.
- **Texto abaixo do mínimo de fonte:** compromete a legibilidade em mobile, que é onde praticamente todo o público consome o conteúdo.
- **Contador de slide no design:** informação redundante, já que o Instagram mostra navegação nativa do carrossel.

## Revisão

- **Aprovar sem ler o conteúdo por completo:** revisão superficial deixa passar promessa indevida ou erro técnico sobre financiamento.
- **Rejeitar sem correção acionável:** apontar um problema sem dizer como corrigi-lo não move o conteúdo adiante.
- **Inflar a nota para evitar confronto:** aprovar conteúdo fraco derruba a barra de qualidade de todo o squad.

## Processo do Squad

- **Pular um checkpoint:** qualquer etapa de execução visual (design) ou avanço de ângulo/tema sem confirmação explícita do usuário quebra o controle de qualidade do pipeline.
- **Loop de revisão sem limite:** reprovar o mesmo conteúdo repetidamente pelos mesmos motivos sem escalar para o usuário após 3 ciclos desperdiça tempo e tokens.
