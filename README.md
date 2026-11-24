# KIRIA — Biblioteca de Leitura

**Nome de trabalho:** KIRIA  
**Descrição:** biblioteca digital pessoal, mobile-first e offline-first para mangás, manhwas, manhuas e novels.

> KIRIA é um nome provisório de produto. A disponibilidade de marca, domínio e nome nas lojas não foi verificada.

## Objetivo
Organizar arquivos pessoais de leitura em uma experiência única, confortável e confiável, com armazenamento local e progresso persistente.

## Princípios
- Mobile-first, com prioridade para Android.
- Uso pessoal e funcionamento offline.
- Arquivos importados permanecem sob controle do usuário.
- Não exigir conta, backend ou conexão permanente.
- Interface editorial sofisticada, sem prejudicar a leitura.
- Arquitetura modular e evolução incremental.

## Documentos
- `VISION.md`: propósito, público e escopo.
- `DESIGN_SYSTEM.md`: direção visual, tokens e componentes.
- `ARCHITECTURE.md`: arquitetura técnica proposta.
- `FILE_FORMATS.md`: importação e formatos.
- `ROADMAP.md`: fases e critérios de conclusão.
- `CLAUDE.md`: instruções de trabalho para o Claude.
- `DECISIONS.md`: decisões e premissas registradas.

## Primeira hipótese técnica
Aplicação web instalável (PWA), React + TypeScript. A decisão entre PWA pura e empacotamento com Capacitor deve ser validada em um protótipo Android, especialmente para importação, persistência e gerenciamento de arquivos.

## Fora do escopo inicial
- Catálogo online ou agregador de conteúdo.
- Download de obras de terceiros.
- Sincronização em nuvem.
- Login, perfis públicos ou recursos sociais.
- Distribuição pública de conteúdo protegido por direitos autorais.

## Como começar
1. Coloque estes documentos na raiz do repositório.
2. Peça ao Claude para ler `CLAUDE.md` e todos os documentos de referência.
3. Faça a auditoria do repositório antes de alterar arquivos.
4. Implemente somente a primeira tarefa aprovada do `ROADMAP.md`.
