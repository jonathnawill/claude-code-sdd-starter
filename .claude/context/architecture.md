# Arquitetura — <Nome do Projeto>

<!-- Este é o documento que o agente software-architect lê antes de aprovar qualquer spec. Precisa ser específico e verificável, não aspiracional — descreva o que o código REALMENTE faz hoje, não o que "deveria" fazer. Apague os comentários guia ao preencher. -->

## Estilo arquitetural

<!-- Monólito modular? Monólito simples? Microsserviços (e por quê, já que é uma decisão com custo real)? Serverless? Declare e justifique brevemente. -->

## Convenção de módulos/pacotes

<!-- Se há uma convenção de organização de código (ex: "cada domínio vive em <namespace>.<dominio>, com subpastas domain/application/infrastructure"), descreva aqui com exemplo real do repo. -->

## Comunicação entre módulos/serviços

<!-- Como um módulo/serviço fala com outro? Import direto é proibido entre certas camadas? Eventos? Fila? HTTP interno? Declare a regra e o que ela proíbe explicitamente. -->

## O que este projeto proíbe explicitamente (e por quê)

<!-- Liste restrições arquiteturais reais e deliberadas — não uma lista genérica de boas práticas. Ex: "sem microsserviços — o time é pequeno demais pro overhead operacional", "sem ORM novo — já usamos X e trocar não se justifica sem gatilho real de escala". -->

## Nível de rigor DDD/Clean Architecture esperado

<!-- Pragmatismo > dogma: em que áreas do domínio a complexidade real justifica camadas ricas (ex: billing, autenticação, cálculo de risco), e onde um CRUD simples é suficiente? -->

## Decisões arquiteturais registradas

Decisões arquiteturais significativas (nova dependência, novo módulo, mudança de padrão de comunicação) são registradas como ADR em `docs/decisions/`, usando [`../templates/adr-template.md`](../templates/adr-template.md). Consulte antes de propor algo que pareça já ter sido decidido.
