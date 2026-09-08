# Prompt — Adotar SDD num projeto existente

Use este prompt (cole numa sessão de Claude Code dentro do projeto que já existe) quando quiser adotar o padrão deste starter em um projeto que **já tem código, time e convenções** — não um projeto novo começando do zero. Para projeto novo, siga direto o passo a passo do [`README.md`](../../README.md) principal.

A diferença importante: aqui o agente **audita antes de propor**, e **propõe antes de implementar**. Um projeto existente pode já ter processo bom rodando — o objetivo é adaptar, nunca atropelar.

---

```markdown
Quero adotar neste projeto um padrão de desenvolvimento orientado por especificação (Spec-Driven Development) — mas adaptado à realidade daqui, não copiado de outro lugar sem crítica.

Antes de propor ou criar qualquer arquivo, faça um diagnóstico do que já existe neste projeto:
- Há algum processo de design/spec antes de implementar, ou o time vai direto pro código?
- Que documentação viva existe hoje (arquitetura, stack, decisões técnicas, ADRs)? Está atualizada ou defasada?
- Como é o processo de review hoje (code review, segurança, performance, acessibilidade se aplicável)? É informal ou tem critério objetivo de aprovação?
- Existem convenções de time já estabelecidas (CONTRIBUTING, guia de estilo, checklist de PR) que eu devo respeitar e não atropelar?
- Onde hoje surgem mais erros/retrabalho: falta de clareza de escopo, falta de revisão de arquitetura antes de implementar, falta de teste, falta de revisão de segurança, outra coisa?

Depois desse diagnóstico, me proponha (sem implementar ainda) uma versão adaptada deste padrão:

1. **Um documento de entrada único** (ex: CLAUDE.md, AGENTS.md, ou o que fizer sentido pra stack daqui) que qualquer sessão de agente lê primeiro — ele referencia o resto da documentação, nunca duplica conteúdo.

2. **Documentação viva de contexto** (visão de produto/serviço, arquitetura, stack técnica) — não como documento estático que apodrece, mas como algo que toda sessão de trabalho estrutural precisa ler antes de propor mudança.

3. **Um workflow com fases nomeadas e critério de saída objetivo por fase** — não é sobre copiar um conjunto fixo de fases, é sobre decidir quais fazem sentido pro risco e natureza deste projeto especificamente. Um serviço de backend interno provavelmente não precisa de revisão de SEO/Acessibilidade, mas quase certamente precisa de revisão de segurança e, dependendo do domínio, de compliance. A regra geral a preservar: nenhuma implementação começa sem uma spec aprovada, e nenhuma feature é considerada pronta sem passar pelas revisões que o risco do projeto exige.

4. **Agentes/personas especializados por disciplina** (arquitetura, backend, segurança, performance, testes, documentação, e o que mais fizer sentido aqui) — em vez de uma IA generalista tentando cobrir tudo de uma vez, cada fase é conduzida com a lente certa.

5. **Templates para artefatos recorrentes** (spec, ADR, descrição de PR) — pra manter consistência sem reinventar formato a cada vez.

6. **Checklists objetivos de saída por disciplina** — não "parece bom", e sim critérios verificáveis (ex: "cobertura de teste no código novo", "sem segredo hardcoded", "endpoints novos com rate limit definido").

7. **Comandos/atalhos que mapeiam pras fases** — pra tornar a invocação do processo consistente entre sessões e pessoas do time.

Regras importantes:
- **Adapte o conteúdo, não copie a estrutura cegamente.** O valor está na disciplina (fases obrigatórias, critério objetivo, documentação viva), não no conteúdo específico de outro projeto que você não viu.
- **Preserve o que já funciona aqui.** Se já existe processo de review ou convenção boa, incorpore — não substitua por vaidade de "novo processo".
- **Isso afeta o time todo, não só uma sessão de IA.** Não crie ou reestruture arquivos de verdade até eu revisar e aprovar explicitamente o plano. Me entregue primeiro o diagnóstico + a proposta adaptada, e só depois — com meu aval — parta pra criar a estrutura.

Quero terminar essa conversa com: um diagnóstico honesto do estado atual, uma proposta de estrutura adaptada (com justificativa de cada peça incluída ou deliberadamente descartada), e uma lista do que precisa da minha decisão antes de qualquer arquivo ser criado.
```
