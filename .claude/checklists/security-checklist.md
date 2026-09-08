# Checklist — Segurança (OWASP Top 10)

- [ ] Sem injeção (SQL/query/comando/template) via input não sanitizado
- [ ] Autenticação e autorização aplicadas no backend em toda operação sensível (não só checagem no frontend/cliente)
- [ ] Sem segredo/dado sensível hardcoded ou logado
- [ ] Respostas de API usam DTO/serializador específico (sem vazar campos internos da entidade)
- [ ] CORS configurado restritivamente (sem `*` em produção)
- [ ] Headers de segurança presentes (CSP, X-Content-Type-Options, etc. conforme aplicável)
- [ ] Sem stacktrace/debug info exposto em resposta de produção
- [ ] Dependências sem CVEs conhecidos não tratados
- [ ] Validação de entrada no backend para todo dado vindo do cliente
- [ ] Conteúdo renderizado como HTML é sanitizado contra XSS
- [ ] Sem SSRF/XXE/deserialização insegura em pontos que aceitam URL/payload externo
- [ ] Rate limiting em endpoints/operações públicas, especialmente as de maior custo
