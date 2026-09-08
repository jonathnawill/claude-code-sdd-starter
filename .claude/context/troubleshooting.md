# Troubleshooting — <Nome do Projeto>

<!-- Isto não é um ADR (que registra uma decisão tomada de propósito). É um log de erros reais que já morderam o projeto — coisa que uma sessão futura, sem memória das anteriores, redescobriria do zero se isso não estivesse escrito. Mantido por documentation-engineer sempre que um bug não-trivial (o tipo que não é óbvio pela mensagem de erro) for corrigido. Apague este comentário e o exemplo abaixo ao começar a preencher de verdade. -->

## Como usar este arquivo

Antes de investigar um bug estranho, procure aqui primeiro — pode já ter sido resolvido. Depois de corrigir um bug não-trivial, adicione uma entrada usando o formato abaixo.

## Formato de entrada

### <Sintoma curto e buscável — o que alguém digitaria procurando isto>

- **Quando acontece**: <contexto/condição específica que dispara o problema>
- **Causa raiz**: <por que acontece — não só o sintoma, o mecanismo>
- **Solução**: <o que resolve, concretamente>
- **Como evitar de novo**: <se isso deveria virar uma regra num checklist/agente, diga qual e atualize-o junto>

<!-- Exemplo real de formato (apague ao usar este arquivo pra valer):

### Timeout intermitente em chamada externa sob carga

- **Quando acontece**: só em produção, sob mais de ~50 req/s simultâneas.
- **Causa raiz**: connection pool do cliente HTTP configurado com o default da lib (2 conexões), não o valor real de concorrência esperado.
- **Solução**: connection pool dimensionado explicitamente no client, com timeout de conexão separado do timeout de leitura.
- **Como evitar de novo**: adicionado item em `.claude/checklists/performance-checklist.md` — "timeouts e connection pooling configurados para chamadas externas".
-->
