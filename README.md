# Claude Code SDD Starter

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Esqueleto genérico de Spec Driven Development (SDD) para projetos conduzidos com Claude Code — extraído de um projeto real, em produção, que já passou por dezenas de rodadas de expansão sem perder consistência arquitetural entre sessões de IA sem memória compartilhada entre si.

## Por que isso existe

Em qualquer projeto de longa duração conduzido por múltiplas sessões de IA, o risco não é "a IA escreve código ruim" — é a IA **implementar direto a partir de um pedido informal**, sem registrar intenção, sem passar por revisão de arquitetura, sem critério objetivo de "pronto". Isso funciona uma vez. Na vigésima sessão, sem memória das dezenove anteriores, o projeto já divergiu de si mesmo.

Este esqueleto resolve isso impondo uma disciplina simples: **nenhuma implementação começa sem uma spec aprovada, e nenhuma spec é aprovada sem passar pelas revisões que o risco do projeto exige.** A spec é o que carrega intenção entre sessões — não a memória de quem está codando.

## O que é genérico aqui vs. o que você precisa preencher

Este repositório é deliberadamente **a espinha dorsal, não um projeto pronto**. Ele não sabe qual é a sua stack, seu domínio de negócio, ou o perfil de risco do seu projeto — isso só você sabe. Todo lugar marcado com `<placeholder>` precisa da sua decisão.

O que fica pronto:
- A estrutura de documento de entrada (`CLAUDE.md`) que referencia o resto sem duplicar.
- O conceito de documentação viva (`context/`) que qualquer sessão lê antes de propor mudança estrutural.
- O workflow de fases nomeadas com critério de saída objetivo.
- Agentes especializados "núcleo" (arquitetura, backend, banco de dados, infra, segurança, performance, qualidade de código, testes, documentação) — presentes na maioria dos projetos de software, independente de domínio.
- Templates de spec, ADR e PR.
- Checklists universais (code review, performance, segurança, pull request, deploy, release).
- Comandos que mapeiam para cada fase (`/spec`, `/plan`, `/implement`, `/review`, `/ship`).

O que **não** está aqui de propósito, porque é específico demais para generalizar sem virar ruído:
- Agentes de frontend/UI/acessibilidade/SEO — só fazem sentido se o seu projeto tem interface pública.
- Agentes de growth/monetização/conteúdo — só fazem sentido se o seu projeto é um produto com aquisição/monetização própria.
- Qualquer scaffolding de domínio (ex: "criar uma nova ferramenta", "criar uma nova página") — isso nasce do seu produto, não de um template genérico.

Se o seu projeto precisar desses papéis, escreva-os seguindo o mesmo formato dos agentes núcleo (frontmatter `name`/`description`/`tools`/`model` + responsabilidade + como trabalha + o que não faz) — o padrão se generaliza fácil, só o conteúdo é específico.

## Como usar

Um detalhe importante de mecânica antes dos passos: o Claude Code carrega `CLAUDE.md` e descobre tudo em `.claude/` (agentes, comandos, skills) **automaticamente**, em toda sessão, assim que esses arquivos existem na raiz do projeto. Não existe um passo de "ativar o padrão" — a partir do momento em que os arquivos estão lá, qualquer sessão já opera sob essas regras.

O caminho muda dependendo se o projeto já existe ou não.

### Projeto novo (seu, começando do zero)

1. Clone este repositório e copie `.claude/` e `CLAUDE.md` para a raiz do projeto novo:
   ```bash
   git clone https://github.com/jonathnawill/claude-code-sdd-starter /tmp/sdd-starter
   cp -r /tmp/sdd-starter/.claude /tmp/sdd-starter/CLAUDE.md /caminho/do/seu/projeto/
   ```
   (ou `gh repo clone jonathnawill/claude-code-sdd-starter`, se preferir o GitHub CLI)
2. Abra uma sessão de Claude Code dentro do projeto e peça ajuda pra preencher, **nesta ordem** (cada um depende do anterior):
   - `.claude/context/tech-stack.md` — a stack real, com versões.
   - `.claude/context/architecture.md` — como o código está organizado, convenções, o que é proibido.
   - `.claude/context/product.md` — o que o projeto é, para quem, o critério de decisão de negócio (se aplicável).
   - `CLAUDE.md` — o resumo/entrada, referenciando os três acima.
3. Revise `.claude/workflows/sdd-workflow.md` e decida quais fases fazem sentido para o **perfil de risco** deste projeto especificamente — nem todo projeto precisa de todas as fases.
4. Revise cada agente em `.claude/agents/` e substitua os `<placeholder>` de stack/convenção pelos valores reais. Delete o que não se aplica, adicione o que falta.
5. Ajuste `.claude/checklists/` removendo itens que não se aplicam e adicionando os que faltam (ex: compliance, LGPD/GDPR, requisitos regulatórios do seu domínio).
6. A partir daqui, todo pedido de feature/mudança começa com `/spec` — o comando já é reconhecido automaticamente.

### Projeto existente (time, empresa, código já em produção)

**Não copie o esqueleto direto aqui.** Um projeto existente já tem convenções, processo de review, talvez um fluxo informal que funciona — atropelar isso de uma vez é pior do que não ter padrão nenhum, e afeta o time todo, não só quem está rodando o agente.

Use o prompt pronto em [`.claude/prompts/adoption-audit.md`](.claude/prompts/adoption-audit.md): ele instrui o agente a **primeiro diagnosticar o que já existe** (o que já funciona, onde surgem os erros hoje, que convenções respeitar) e só depois **propor** uma versão adaptada deste padrão — nunca implementar ou reestruturar arquivos sem aprovação explícita de quem está pedindo.

## Princípio para adaptar, não copiar

O valor deste padrão não está no conteúdo específico de outro projeto que você não viu — está na disciplina: **fases obrigatórias, critério de saída objetivo, documentação viva, revisão especializada por dimensão de risco**. Preserve isso. Descarte o resto sem culpa.

## Contribuindo

Contribuições são bem-vindas — veja [CONTRIBUTING.md](CONTRIBUTING.md) antes de abrir um PR (o repositório é deliberadamente pequeno e genérico; nem toda contribuição útil pertence ao núcleo). Este projeto segue o [Código de Conduta do Contribuidor](CODE_OF_CONDUCT.md).

## Licença

[MIT](LICENSE).
