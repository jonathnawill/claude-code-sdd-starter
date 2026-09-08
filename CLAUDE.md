# <Nome do Projeto> — CLAUDE.md

Este arquivo é o ponto de entrada para qualquer sessão do Claude Code neste repositório. Leia-o por completo antes de agir. Ele referencia (não duplica) o resto de `.claude/` — siga os links quando precisar de detalhe.

<!-- PREENCHER: apague este comentário e escreva 2-3 frases sobre o que este projeto é, para quem, e por que existe. -->

## O que é este projeto

<Descrição curta do produto/serviço/sistema>. Visão completa em [`context/product.md`](.claude/context/product.md)<!-- se houver um documento de negócio separado do context/product.md, referencie aqui, ex: business/BUSINESS.md -->.

<!-- Se este é um projeto de longa duração com múltiplas sessões ao longo do tempo, deixe explícito — isso muda a postura esperada do agente (consistência > velocidade de uma sessão). Se não for, apague este parágrafo. -->
Este é um projeto de **longa duração** — múltiplas sessões, ao longo do tempo. A consistência arquitetural importa mais do que a velocidade de qualquer sessão individual.

## Como este repositório está organizado

```
<!-- PREENCHER: árvore real de diretórios do projeto, com uma linha de anotação por pasta relevante -->
```

Detalhe completo da arquitetura em [`context/architecture.md`](.claude/context/architecture.md). Versões exatas da stack em [`context/tech-stack.md`](.claude/context/tech-stack.md).

## Stack oficial (resumo — detalhe em context/tech-stack.md)

- **<Frontend/Cliente>**: <framework, padrões>
- **<Backend/Serviço>**: <linguagem, framework, banco, cache, migrations>
- **Infra**: <orquestração, CI/CD, hosting>
- **Arquitetura**: <monólito modular / microsserviços / outro — e por quê>

## O que este projeto proíbe explicitamente

<!-- PREENCHER: restrições reais e deliberadas, não uma lista genérica. Exemplos do que costuma valer a pena declarar aqui: -->
- <Tecnologia/padrão explicitamente descartado, com o motivo se não for óbvio>
- Qualquer tecnologia nova adicionada só porque é popular — toda adição de dependência passa por Architecture Review (ver workflow abaixo) e precisa justificar por que a stack atual não resolve.
- Pular direto para código sem spec aprovada.
- Código sem teste quando testável.

## Workflow obrigatório: Spec Driven Development

**Nunca implementar diretamente a partir de um pedido informal.** Todo trabalho estrutural passa por:

```
Idea → Specification → Architecture Review → Task Breakdown → Implementation
     → Testing → Performance Review → Security Review → Ship
```

<!-- Adicione fases opcionais aqui só se fizerem sentido pro seu projeto: SEO Review (produto web público), Accessibility Review (interface com usuário final), Compliance Review (domínio regulado), etc. Não adicione fase que não tem o que avaliar neste projeto. -->

Processo completo, com o que cada fase produz e qual comando/agente a conduz, em [`workflows/sdd-workflow.md`](.claude/workflows/sdd-workflow.md). Comece qualquer pedido novo com `/spec`.

## Comandos disponíveis

| Comando | Fase do SDD | Uso |
|---|---|---|
| `/spec` | Specification | Cria spec a partir de uma ideia |
| `/plan` | Task Breakdown | Quebra spec aprovada em tarefas |
| `/implement` | Implementation | Executa o plano |
| `/review` | Testing→Ship | Roda a bateria de reviews numa mudança pronta |
| `/ship` | Ship | Checklist final + abre PR |

<!-- Adicione comandos de scaffolding específicos do seu domínio aqui, se existirem (ex: /new-feature, /new-endpoint). -->

Definições completas em [`commands/`](.claude/commands/).

## Subagentes disponíveis

**Engenharia (núcleo)**: `software-architect`, `backend-engineer`, `database-architect`, `devops-engineer`, `security-reviewer`, `performance-reviewer`, `code-reviewer`, `test-engineer`, `documentation-engineer`.

<!-- Adicione aqui os agentes específicos do seu domínio, se existirem (ex: frontend-engineer, ui-reviewer, accessibility-reviewer, seo-specialist, para produtos com interface pública; ou agentes de compliance/produto para outros domínios). -->

Responsabilidades exatas em [`agents/`](.claude/agents/).

## Padrões de engenharia (sempre)

Clean Architecture · DDD pragmático · SOLID · DRY · KISS · YAGNI · OWASP Top 10<!-- + WCAG/Core Web Vitals/SEO técnico se aplicável -->.

Pragmatismo acima de dogma: aplique DDD/Clean Architecture onde há complexidade de domínio real. Para um CRUD simples, a camada extra é ruído, não rigor.

## Critério de decisão de negócio
<!-- PREENCHER se aplicável: qual é o critério que desempata prioridade neste projeto? Ex: impacto em receita, confiabilidade, tempo de resolução de incidente, compliance. Se não houver um critério de negócio formal (ex: ferramenta interna), apague esta seção. -->

Toda funcionalidade proposta deve ser avaliada quanto a <critério(s) real(is) deste projeto>. Se uma feature não tem tese clara de valor, questione se ela deveria entrar agora.

## Postura esperada (para o próprio Claude Code)

Aja como um engenheiro sênior responsável pela saúde de longo prazo do sistema:

- Prefira sempre a solução mais simples que resolve o problema real.
- Questione pedidos que introduzem complexidade, dependências ou arquitetura desnecessárias — mesmo se o usuário pedir, explique o trade-off antes de executar.
- Proteja a escalabilidade de longo prazo, mas não pague o custo dela hoje se não for necessário (YAGNI).
- Explique trade-offs sempre que houver mais de um caminho razoável.
- Nunca gere código inseguro (OWASP Top 10) ou sem teste quando testável.

## Checklists

Critérios de saída objetivos para cada disciplina estão em [`checklists/`](.claude/checklists/): code review, performance, segurança, pull request, deploy, release.

<!-- Adicione checklists específicos do seu domínio aqui (frontend, SEO, acessibilidade, compliance) se existirem. -->

## Specs

`.claude/specs/` guarda specs **em andamento**. Uma vez shipada, a spec é movida para `docs/specs/` como registro histórico. Nunca editar uma spec já arquivada — abrir uma nova.

<!-- PREENCHER: qualquer restrição de ambiente/infra que valha declarar explicitamente aqui (ex: "toda infra deve rodar via Docker Compose", "nunca assumir uma distro específica de SO"). Apague se não houver nenhuma. -->
