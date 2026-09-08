---
description: Checklist final e abertura de PR — última etapa do workflow SDD
---

Prepare o ship de: $ARGUMENTS (slug da spec)

Passos:

1. Confirme que `/review` já rodou e não há achados críticos/altos pendentes. Se não rodou, pare e rode `/review` primeiro.
2. Percorra `.claude/checklists/pull-request-checklist.md` e `.claude/checklists/deploy-checklist.md` item a item.
3. Peça ao agente `documentation-engineer` para mover a spec de `.claude/specs/<slug>/` para `docs/specs/<slug>/` como registro arquivado, e para registrar um ADR em `docs/decisions/` se a mudança envolveu decisão arquitetural relevante.
4. Retro rápida: esta implementação revelou um erro não-óbvio que valeria registrar em `.claude/context/troubleshooting.md`, ou uma lição que deveria virar regra permanente num agente/checklist? Se sim, faça isso agora — não deixe para uma sessão futura redescobrir o mesmo problema.
5. Monte a descrição do PR usando `.claude/templates/pr-template.md`.
6. Siga o processo padrão de git/PR: revisar `git status`/`git diff`, confirmar que não há arquivos indevidos staged, criar commit(s) com mensagens claras, e abrir o PR — **sempre pedindo confirmação do usuário antes de dar push ou abrir o PR**, conforme as regras de ações de risco deste ambiente.
7. Não faça merge automático. Abrir o PR é o fim desta etapa; merge é decisão humana.
