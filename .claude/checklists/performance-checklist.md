# Checklist — Performance

## Backend

- [ ] Sem queries N+1 ou consultas custosas evitáveis
- [ ] Índices presentes para colunas usadas em filtro/junção/ordenação frequentes
- [ ] Cache aplicado onde há leitura repetida de dado caro/pouco mutável, com TTL definido
- [ ] Paginação em endpoints/operações que retornam listas potencialmente grandes
- [ ] Timeouts e connection pooling configurados para chamadas externas

## Frontend (se houver)

- [ ] Core Web Vitals dentro de limite aceitável (LCP, CLS, INP)
- [ ] Nenhuma lib pesada importada inteira quando só uma função é usada
- [ ] Renderização no servidor (se aplicável) entrega conteúdo útil no HTML inicial, não só um shell vazio
- [ ] Lazy loading de rotas/imagens abaixo da dobra
