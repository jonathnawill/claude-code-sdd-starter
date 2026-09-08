---
description: Cria uma especificação a partir de uma ideia, iniciando o workflow SDD
---

Crie (ou continue) uma spec para: $ARGUMENTS

Passos:

1. Se `$ARGUMENTS` for vago, faça as perguntas necessárias antes de escrever a spec — não assuma escopo.
2. Determine o slug (kebab-case) e crie `.claude/specs/<slug>/spec.md` a partir de `.claude/templates/spec-template.md`.
3. Preencha todas as seções, especialmente:
   - Escopo (o que está e não está incluído)
   - Impacto em negócio, se aplicável (consulte `.claude/context/product.md`)
   - Critérios de aceite objetivos e verificáveis
4. Leia `.claude/context/architecture.md` e `.claude/context/tech-stack.md` antes de propor qualquer solução técnica na spec, para não sugerir algo que já existe ou que viola as restrições do projeto.
5. Ao final, apresente a spec para o usuário e pare — **não avance para `/plan` ou código automaticamente**. A próxima etapa é a Architecture Review (agente `software-architect`), tipicamente disparada por `/plan`.

Não escreva código nesta fase.
