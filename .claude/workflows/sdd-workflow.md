# Spec Driven Development — Workflow

Todo desenvolvimento estrutural neste projeto segue este fluxo. **Nunca implementar diretamente a partir de um pedido informal.** Se alguém (usuário ou o próprio Claude) pular direto para código sem uma spec aprovada, pare e volte ao início do fluxo.

```
Idea
  ↓
Specification         (/spec)
  ↓
Architecture Review    (agente software-architect)
  ↓
Task Breakdown         (/plan)
  ↓
Implementation          (/implement)
  ↓
Testing                  (agente test-engineer)
  ↓
Performance Review        (/performance-review, agente performance-reviewer)
  ↓
Security Review             (/security-review, agente security-reviewer)
  ↓
Ship                          (/ship)
```

> As fases acima são o núcleo que se aplica a praticamente qualquer projeto de software. Se o seu projeto tem interface pública, considere inserir **SEO Review** e **Accessibility Review** antes do Ship. Se o seu projeto é regulado, considere uma **Compliance Review**. Não adicione uma fase que não tem o que avaliar neste projeto especificamente — cada fase existe porque o risco que ela cobre é real aqui.

## O que acontece em cada fase

### 1. Idea
Qualquer pedido em linguagem natural do usuário, ou item de roadmap. <!-- Se o projeto tem um agente de produto/negócio que valida ideias antes da spec, descreva aqui contra qual documento ele avalia (ex: business/BUSINESS.md). Se não houver essa fase formal, pode seguir direto para Specification. --> Ainda sem compromisso de escopo técnico.

### 2. Specification — `/spec`
Produz um documento em `.claude/specs/<slug>/spec.md` a partir do template [`templates/spec-template.md`](../templates/spec-template.md). Define: problema, objetivo, escopo (o que é e o que não é), critérios de aceite. **Sem código nesta fase.**

### 3. Architecture Review
O agente `software-architect` lê a spec e valida: está alinhada com [`context/architecture.md`](../context/architecture.md)? Introduz complexidade desnecessária? Precisa de nova dependência (e se sim, se justifica)? Aprova, pede ajuste na spec, ou rejeita com motivo.

### 4. Task Breakdown — `/plan`
Quebra a spec aprovada em tarefas concretas e ordenadas, mapeando cada uma para os agentes/arquivos relevantes.

### 5. Implementation — `/implement`
Execução das tarefas do plano, delegando para os agentes de engenharia conforme o domínio (`backend-engineer`, `database-architect`, etc.). Segue os checklists relevantes em [`checklists/`](../checklists/) durante a implementação, não só no final.

### 6. Testing
`test-engineer` garante cobertura adequada (unit + integração onde fizer sentido). Código sem teste quando aplicável não é considerado pronto.

### 7. Performance Review — `/performance-review`
`performance-reviewer` avalia tempo de resposta, uso de recursos e (se houver frontend) Core Web Vitals/bundle size, usando [`checklists/performance-checklist.md`](../checklists/performance-checklist.md)<!-- este checklist não está incluído no starter — crie um se o projeto precisar --->.

### 8. Security Review — `/security-review`
`security-reviewer` audita contra OWASP Top 10 usando [`checklists/security-checklist.md`](../checklists/security-checklist.md).

### 9. Ship — `/ship`
Checklist final de PR/deploy ([`checklists/pull-request-checklist.md`](../checklists/pull-request-checklist.md), [`checklists/deploy-checklist.md`](../checklists/deploy-checklist.md)), abre o PR. A spec é movida de `.claude/specs/<slug>/` para `docs/specs/<slug>/` como registro histórico arquivado.

## Regra de bypass zero

Nenhuma fase é pulada por "ser pequena". Uma spec pode ser curta (poucas linhas) para uma mudança trivial, mas ela existe. Isso é o que permite que múltiplas sessões, ao longo do tempo, mantenham consistência sem depender de memória humana ou de IA.
