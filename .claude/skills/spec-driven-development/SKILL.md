---
name: spec-driven-development
description: Use sempre que um pedido de feature/mudança chegar sem uma spec aprovada em .claude/specs/ — antes de escrever qualquer código, para produzir/validar a spec seguindo o workflow SDD deste projeto. Trigger em pedidos como "adicione uma funcionalidade que faz X", "implemente Y", "crie Z".
---

# Spec Driven Development

Este projeto nunca implementa direto a partir de um pedido informal. Todo trabalho estrutural segue o ciclo documentado em `.claude/workflows/sdd-workflow.md`:

```
Idea → Specification → Architecture Review → Task Breakdown → Implementation
     → Testing → Performance Review → Security Review → Ship
```

## Ao receber um pedido novo

1. Verifique se já existe uma spec para isso em `.claude/specs/`. Se não, crie uma usando `.claude/templates/spec-template.md`, preenchendo especialmente a seção de impacto em negócio (se aplicável — ver `.claude/context/product.md`).
2. Não avance para código antes que a spec tenha passado pelo agente `software-architect` (Architecture Review).
3. Use `/plan` para quebrar a spec aprovada em tarefas antes de `/implement`.
4. Depois de implementado, a mudança passa pela bateria de reviews (`test-engineer` → `performance-reviewer` → `security-reviewer` → outras fases específicas deste projeto, se existirem) antes de `/ship`.
5. No Ship, a spec migra de `.claude/specs/<slug>/` para `docs/specs/<slug>/` como arquivo histórico (ver agente `documentation-engineer`).

## Por que isso importa aqui especificamente

Este projeto é de longa duração, construído ao longo do tempo por sessões de IA sem memória compartilhada entre si. A spec é o que carrega intenção e contexto entre sessões — pular essa etapa quebra a consistência do projeto silenciosamente, uma mudança de cada vez.
