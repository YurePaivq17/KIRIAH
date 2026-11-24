# ARQUITETURA — KIRIA

## 1. Princípios
- Local-first e offline-first.
- Separação entre interface, domínio, persistência e adaptadores de formato.
- Arquivos originais tratados como imutáveis.
- Progresso salvo de forma incremental.
- Falhas de importação e armazenamento sempre explícitas.
- Dependências escolhidas após validação de manutenção, licença e compatibilidade mobile.

## 2. Estratégia de plataforma
Hipótese inicial: PWA com React + TypeScript. Antes de consolidar, criar uma prova de conceito Android para validar:
- Seleção de arquivos pelo seletor do sistema.
- Importação de arquivos grandes.
- Persistência após fechar/reabrir o navegador.
- Funcionamento offline.
- Limites de armazenamento e comportamento de quota.
- Instalação e experiência em tela cheia.

Se PWA não oferecer experiência ou persistência adequadas, avaliar Capacitor mantendo a maior parte da aplicação web.

## 3. Camadas
### Presentation
Telas, componentes, navegação, estados e acessibilidade.

### Application
Casos de uso: importar obra, atualizar metadados, abrir leitura, salvar progresso, exportar biblioteca e remover arquivo.

### Domain
Entidades e regras independentes de frameworks:
- `Work`
- `Volume`
- `Chapter`
- `ReadingProgress`
- `Bookmark`
- `Collection`
- `ImportedAsset`

### Infrastructure
IndexedDB, OPFS quando suportado, File Picker, parser de arquivos, PDF renderer, cache e Service Worker.

## 4. Persistência local
- IndexedDB: metadados, índices, configurações, progresso e referências aos arquivos.
- OPFS: opção preferencial para arquivos grandes quando suportado e validado.
- Fallback: Blob no IndexedDB, sujeito a testes de desempenho e quota.
- `localStorage`: somente preferências pequenas e não críticas; nunca armazenar arquivos ou progresso principal.

Não assumir que o armazenamento do navegador é permanente. Solicitar persistência quando disponível, monitorar quota e oferecer exportação/backup. Explicar ao usuário que limpar dados do navegador pode apagar a biblioteca local.

## 5. Modelo de domínio inicial
### Work
`id`, `title`, `alternativeTitles`, `type`, `coverAssetId`, `authors`, `description`, `tags`, `status`, `createdAt`, `updatedAt`.

### Volume
`id`, `workId`, `title`, `number`, `sortOrder`.

### Chapter
`id`, `workId`, `volumeId`, `title`, `number`, `sortOrder`, `assetId`.

### ImportedAsset
`id`, `fileName`, `mimeType`, `sizeBytes`, `storageKey`, `checksum` opcional, `importedAt`.

### ReadingProgress
`id`, `workId`, `chapterId`, `locationType`, `locationValue`, `updatedAt`.

`locationType` pode representar página, índice de imagem, posição vertical ou página/posição do PDF. A implementação deve evitar depender de um único formato de localização.

### Bookmark
`id`, `workId`, `chapterId`, `locationType`, `locationValue`, `label`, `createdAt`.

## 6. Importação
Fluxo:
1. Usuário seleciona arquivo(s).
2. Validar extensão, MIME e tamanho; não confiar apenas na extensão.
3. Verificar espaço disponível quando possível.
4. Ler metadados mínimos.
5. Copiar para armazenamento gerenciado pelo app, sem modificar a origem.
6. Criar registro transacional.
7. Gerar miniatura quando suportado.
8. Mostrar resultado e permitir editar título/categoria.

Se uma etapa falhar, limpar temporários e não deixar registros órfãos. Para importações grandes, usar fila e progresso.

## 7. Leitores como adaptadores
Interface comum `ReaderAdapter` com capacidades declaradas:
- abrir documento;
- renderizar conteúdo;
- obter posição atual;
- restaurar posição;
- navegar para frente/trás;
- liberar recursos.

Adaptadores iniciais:
- `ImageChapterAdapter`
- `PdfReaderAdapter`
- futuramente `EpubReaderAdapter`
- futuramente `TextReaderAdapter`

Não forçar todos os formatos a compartilhar os mesmos controles. Cada leitor expõe capacidades próprias.

## 8. Desempenho
- Renderizar páginas sob demanda.
- Descartar imagens fora da janela de leitura quando seguro.
- Usar miniaturas para a biblioteca.
- Evitar carregar capítulos inteiros em memória.
- Testar arquivos grandes e aparelhos Android de desempenho intermediário.
- Salvar progresso com debounce e em eventos de navegação relevantes.

## 9. Segurança e privacidade
- Não enviar arquivos, nomes de obras ou hábitos de leitura para serviços externos.
- Não adicionar analytics remoto no MVP.
- Não executar conteúdo ativo embutido em arquivos.
- Validar arquivos compactados contra caminhos maliciosos, entradas excessivas e tamanhos descomprimidos abusivos.
- Pedir confirmação antes de excluir arquivos e explicar se a exclusão é definitiva.
- Não registrar conteúdo pessoal em logs.

## 10. Estrutura de pastas sugerida
```text
src/
  app/
  components/
  features/
    library/
    import/
    comic-reader/
    novel-reader/
    progress/
    settings/
  domain/
  infrastructure/
    database/
    storage/
    file-parsers/
    readers/
  hooks/
  styles/
  types/
  utils/
tests/
docs/
```

## 11. Decisões pendentes de prova de conceito
- PWA pura ou Capacitor.
- OPFS versus Blob no IndexedDB para arquivos grandes.
- Biblioteca de EPUB.
- Estratégia de extração CBZ/ZIP.
- Estratégia de miniaturas e cache.
- Exportação e restauração de backup.
