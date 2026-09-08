# Checklist — Code Review

- [ ] Nomes de variável/função claros; funções pequenas, uma responsabilidade
- [ ] Sem duplicação genuína de regra de negócio (extraída quando repetida em 3+ lugares)
- [ ] Sem abstração especulativa para caso hipotético não pedido (YAGNI)
- [ ] Consistente com padrões já estabelecidos no módulo/projeto
- [ ] Comentários só onde o "porquê" não é óbvio pelo código
- [ ] Tratamento de erro só para cenários que podem realmente ocorrer
- [ ] Sem `catch` genérico escondendo falha
- [ ] Respeita os limites de módulo/camada definidos em `.claude/context/architecture.md`
- [ ] Nenhuma dependência nova sem passar por Architecture Review
