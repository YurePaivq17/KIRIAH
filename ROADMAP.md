# ROADMAP — KIRIA

## Fase 0 — Descoberta e validação
- [ ] Auditar repositório e ambiente atual.
- [ ] Ler Skills relevantes: UI UX Pro Max, Design, Engineering, frontend-design e Superpowers.
- [ ] Verificar stack e versões com Context7.
- [ ] Prototipar importação e persistência no Android.
- [ ] Decidir PWA pura ou Capacitor com evidências.

**Saída:** relatório de viabilidade e decisões registradas.

## Fase 1 — Fundação
- [ ] Criar estrutura modular.
- [ ] Configurar TypeScript, lint, formatação e testes.
- [ ] Implementar tokens e temas.
- [ ] Criar AppShell e navegação mobile.
- [ ] Implementar IndexedDB e camada de repositório.
- [ ] Implementar estados vazios, erros e carregamento.

**Saída:** aplicação navegável, sem leitores ainda.

## Fase 2 — Biblioteca e importação
- [ ] Importar PDF e imagens.
- [ ] Implementar CBZ/ZIP após teste de segurança e desempenho.
- [ ] Criar metadados editáveis.
- [ ] Criar busca, filtros e ordenação.
- [ ] Implementar armazenamento e monitoramento de quota.

**Saída:** biblioteca funcional com conteúdo local.

## Fase 3 — Leitores
- [ ] Leitor de imagens por página.
- [ ] Rolagem vertical para quadrinhos.
- [ ] Direção de leitura configurável.
- [ ] Leitor PDF progressivo.
- [ ] Retomada automática de posição.

**Saída:** leitura offline para formatos do MVP.

## Fase 4 — Recursos de organização
- [ ] Favoritos.
- [ ] Coleções.
- [ ] Histórico.
- [ ] Marcadores.
- [ ] Estatísticas básicas.

## Fase 5 — Novels adicionais
- [ ] Leitor EPUB.
- [ ] Leitor TXT.
- [ ] Personalização tipográfica.
- [ ] Sumário e navegação por capítulo.

## Fase 6 — Robustez
- [ ] Testes em diferentes larguras e aparelhos Android.
- [ ] Testes com arquivos grandes.
- [ ] Testes de recuperação após falha.
- [ ] Exportação e restauração de biblioteca.
- [ ] Auditoria de acessibilidade.
- [ ] Otimização de memória e bateria.

## Regra de execução
Trabalhar em tarefas pequenas. Cada tarefa deve ter objetivo, arquivos afetados, critérios de aceitação, testes e resumo das alterações. Não iniciar a fase seguinte enquanto os critérios essenciais da fase atual não forem validados.
