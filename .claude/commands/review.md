---
description: Roda a bateria de reviews do workflow SDD (testing → performance → security → outras fases do projeto) sobre uma mudança implementada
---

Revise a mudança de: $ARGUMENTS (slug da spec, ou descrição do que revisar se não houver spec formal)

Rode, em sequência, as fases de review do workflow SDD (`.claude/workflows/sdd-workflow.md`):

1. **Testing** — agente `test-engineer`: confirma cobertura adequada, preenche lacunas. (pular se a mudança não toca código testável — ex: só documentação/config)
2. **Performance Review** — agente `performance-reviewer`, usando `.claude/checklists/performance-checklist.md`. (pular se a mudança não toca código de aplicação)
3. **Security Review** — agente `security-reviewer`, usando `.claude/checklists/security-checklist.md`. (pular se a mudança não toca autenticação, entrada de usuário, dados sensíveis, dependências novas, ou qualquer código de aplicação)
<!-- Adicione aqui outras fases específicas deste projeto, se existirem: SEO Review, Accessibility Review, Compliance Review — no mesmo formato (agente, checklist, condição de pular). -->
4. **Code Review** geral — agente `code-reviewer`, para qualidade estrutural do código. (pular se a mudança não toca código)

Antes de disparar a bateria, classifique a mudança (puramente documentação/config, ou toca código) e pule as fases que não têm o que avaliar. Não rode uma fase "por hábito" quando ela não tem o que avaliar.

Para cada fase, colete os achados. Se houver achados críticos/altos, devolva ao agente de implementação responsável para correção antes de prosseguir para a próxima fase — não acumule dívida.

Ao final, apresente um resumo consolidado: o que foi encontrado, o que foi corrigido, o que ainda está pendente. Isso é o que informa se a mudança está pronta para `/ship`.
