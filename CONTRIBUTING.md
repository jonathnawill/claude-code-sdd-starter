# Como contribuir

Obrigado pelo interesse em melhorar este starter. Antes de abrir um PR, vale entender o que este repositório é e o que ele deliberadamente não é.

## O espírito do repositório

Este é o **esqueleto núcleo** de um padrão de Spec Driven Development — não um framework completo, não uma ferramenta com opinião forte sobre toda stack possível. O valor está em ser pequeno, genérico e adaptável. Contribuições que aumentam a generalidade ou a clareza são bem-vindas; contribuições que tornam o núcleo mais específico de um domínio/stack não são, mesmo que sejam úteis — esse tipo de conteúdo pertence a um projeto que *usa* este starter, não ao starter em si.

## O que é bem-vindo

- Corrigir link quebrado, erro de digitação, inconsistência entre arquivos.
- Melhorar a clareza de um agente/checklist/template sem adicionar especificidade de domínio.
- Generalizar algo que hoje está sutilmente amarrado a uma stack específica.
- Propor um novo agente/checklist/template **opcional** — desde que documentado como opcional (ver `README.md`, seção "O que não está aqui de propósito") e seguindo o mesmo formato dos arquivos existentes.
- Melhorar `.claude/prompts/adoption-audit.md` com base em experiência real de adoção.

## O que não é bem-vindo aqui

- Conteúdo específico de uma stack (ex: "sempre use X framework") dentro dos agentes **núcleo** — esses usam `<placeholder>` deliberadamente.
- Fases de workflow obrigatórias que só fazem sentido pra um tipo de projeto (ex: SEO Review como fase núcleo) — isso vira comentário-guia opcional, não conteúdo fixo.
- Ferramentas/automação que dependam de um ambiente específico não documentado.

## Formato de PR

- Um PR por mudança conceitual — não misture "corrigir link" com "adicionar agente novo".
- Se estiver adicionando um agente/checklist/template opcional, siga exatamente o formato dos arquivos existentes (frontmatter `name`/`description`/`tools`/`model` para agentes; estrutura de checkbox para checklists).
- Descreva no PR *por que* a mudança pertence ao núcleo genérico e não a um projeto específico que a adota.

`.github/PULL_REQUEST_TEMPLATE.md` é o template para contribuir *neste* repositório — não confunda com `.claude/templates/pr-template.md`, que é o template que um projeto adotando este padrão usa para as próprias PRs dele.

## Código de conduta

Este projeto segue o [Código de Conduta](CODE_OF_CONDUCT.md). Participando, você concorda em respeitá-lo.
