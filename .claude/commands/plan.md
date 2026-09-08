---
description: Roda a Architecture Review e quebra uma spec aprovada em tarefas de implementação
---

Planeje a implementação da spec: $ARGUMENTS (slug ou descrição para localizar em `.claude/specs/`)

Passos:

1. Localize a spec correspondente em `.claude/specs/<slug>/spec.md`. Se não existir, pare e sugira `/spec` primeiro.
2. Delegue ao agente `software-architect` a Architecture Review da spec. Se o veredito for "rejeitado" ou "aprovado com ressalvas" que exigem mudança de escopo, atualize a spec e pare para o usuário revisar antes de continuar.
3. Com a spec aprovada, produza um plano de tarefas concreto, ordenado, mapeando cada tarefa ao agente responsável (`backend-engineer`, `database-architect`, `devops-engineer`, e outros agentes específicos do domínio deste projeto se existirem).
4. Se a spec envolve modelagem de dados nova/complexa, inclua uma tarefa explícita para `database-architect` antes das tarefas de `backend-engineer` que dependem do schema.
5. Salve o plano como `.claude/specs/<slug>/plan.md`.
6. Apresente o plano ao usuário e pare — a próxima etapa é `/implement`, não automática.

Não escreva código de aplicação nesta fase.
