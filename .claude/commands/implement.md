---
description: Executa o plano de tarefas de uma spec aprovada
---

Implemente o plano de: $ARGUMENTS (slug ou descrição para localizar em `.claude/specs/`)

Passos:

1. Localize `.claude/specs/<slug>/plan.md`. Se não existir, pare e sugira `/plan` primeiro.
2. Trabalhe a lista de tarefas de forma sistemática, uma de cada vez, marcando progresso.
3. Delegue cada tarefa ao agente indicado no plano.
4. Cada agente já escreve testes básicos ao implementar (não deixe para depois "tudo de uma vez").
5. Se durante a implementação surgir a necessidade de algo fora do escopo da spec (nova dependência, mudança estrutural), pare e volte para `/spec`/`/plan` — não expanda escopo silenciosamente.
6. Ao terminar todas as tarefas, confirme que o build passa e os testes rodam antes de declarar a implementação concluída.
7. Ao final, informe ao usuário que a implementação está pronta para `/review` — não rode a bateria de reviews automaticamente aqui.
