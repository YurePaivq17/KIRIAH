# DESIGN SYSTEM — KIRIA

## 1. Direção criativa
**Fusão:** Obsidian Editorial + Modern Library + Literary Atelier + Immersive Reading.

A interface combina a profundidade de uma biblioteca escura, a clareza de um catálogo contemporâneo, a delicadeza editorial de materiais impressos e uma experiência de leitura imersiva. A estética deve servir ao conteúdo: capas e páginas são protagonistas.

## 2. Personalidade
- Cultivada, serena, contemporânea e acolhedora.
- Sofisticada sem parecer luxuosa em excesso.
- Visualmente rica na biblioteca; discreta durante a leitura.
- Evitar excesso de gradientes, glassmorphism, bordas luminosas e animações decorativas.

## 3. Cores — tokens iniciais
Os valores são uma base de prototipagem e devem ser validados em telas reais.

### Tema escuro (padrão da interface)
- `color.bg`: `#111210`
- `color.surface`: `#1A1B18`
- `color.surface-elevated`: `#242520`
- `color.border`: `#34352F`
- `color.text-primary`: `#F2F0E8`
- `color.text-secondary`: `#AAA99F`
- `color.text-muted`: `#77776F`
- `color.accent`: `#C5A477` (ouro envelhecido discreto)
- `color.accent-strong`: `#E0BD8C`
- `color.success`: `#8DA88A`
- `color.warning`: `#D5A56F`
- `color.error`: `#CF8279`

### Tema claro
- `color.bg`: `#F3F0E8`
- `color.surface`: `#FBF9F3`
- `color.surface-elevated`: `#FFFFFF`
- `color.border`: `#DED9CE`
- `color.text-primary`: `#25251F`
- `color.text-secondary`: `#69685F`
- `color.text-muted`: `#89877D`
- `color.accent`: `#8C6D45`

### Temas do leitor
- Escuro: fundo `#101010`, controles discretos.
- Papel: fundo `#F3EBDD`, texto `#332F28`.
- Sépia: fundo `#E7D8B9`, texto `#453A2D`.
- Claro: fundo `#FFFFFF`, texto `#242424`.

Não aplicar filtros de cor às páginas de quadrinhos por padrão. Temas de novel não devem alterar a aparência de PDFs digitalizados.

## 4. Tipografia
Usar uma família de interface legível e uma família editorial opcional para títulos. Fontes candidatas devem ser verificadas quanto a licença, cobertura de caracteres e desempenho antes de inclusão.

- Interface: sans-serif de alta legibilidade.
- Títulos editoriais: serif contemporânea, usada com moderação.
- Texto de novel: controle de tamanho, altura de linha e largura da coluna quando o formato permitir.
- Não usar fontes pequenas para metadados essenciais.

Escala inicial:
- `text-xs`: 12 px
- `text-sm`: 14 px
- `text-md`: 16 px
- `text-lg`: 18 px
- `heading-sm`: 20 px
- `heading-md`: 24 px
- `heading-lg`: 30 px

## 5. Espaçamento e forma
Base de espaçamento: 4 px.
- `space-1`: 4 px
- `space-2`: 8 px
- `space-3`: 12 px
- `space-4`: 16 px
- `space-5`: 20 px
- `space-6`: 24 px
- `space-8`: 32 px
- `space-10`: 40 px

Raios:
- `radius-sm`: 8 px
- `radius-md`: 12 px
- `radius-lg`: 18 px
- `radius-xl`: 24 px
- `radius-pill`: 999 px

## 6. Layout mobile
- Projetar primeiro para largura de 360–430 px.
- Respeitar áreas seguras do sistema operacional.
- Navegação inferior com 3–5 destinos no máximo.
- Áreas de toque preferencialmente com pelo menos 44 × 44 px.
- Evitar ações importantes escondidas apenas em gestos.
- Usar listas compactas para metadados e cards visuais para capas.
- Durante a leitura, esconder a navegação principal e oferecer controles sob demanda.

## 7. Navegação proposta
- Início
- Biblioteca
- Coleções
- Atividade
- Ajustes

A navegação pode ser simplificada no MVP; não implementar telas vazias apenas para preencher o menu.

## 8. Componentes essenciais
- `AppShell`
- `BottomNavigation`
- `TopBar`
- `SearchField`
- `MediaCard`
- `BookRow`
- `LibraryGrid`
- `FilterChips`
- `ProgressIndicator`
- `EmptyState`
- `ImportDropzone`/`ImportAction`
- `ImportQueue`
- `ReaderToolbar`
- `ChapterNavigator`
- `ReadingSettingsSheet`
- `ConfirmationDialog`
- `StorageUsagePanel`

Cada componente deve ter estados normal, pressionado, foco, desabilitado, carregando e erro quando aplicável.

## 9. Diretrizes para capas
- Preservar proporção original.
- Usar `object-fit: cover` apenas para miniaturas de catálogo quando o corte for aceitável.
- Oferecer visualização da capa inteira.
- Não inventar capas nem substituir arquivos originais silenciosamente.
- Placeholders devem ser discretos e distintos de capas reais.

## 10. Movimento
- Animações curtas e funcionais, normalmente entre 120–220 ms.
- Respeitar `prefers-reduced-motion`.
- Evitar animação durante a leitura contínua.
- Não usar parallax ou efeitos que prejudiquem desempenho.

## 11. Acessibilidade
- Contraste adequado.
- Foco visível para navegação por teclado quando aplicável.
- Rótulos acessíveis em ícones e controles.
- Não comunicar status apenas por cor.
- Alvos de toque confortáveis.
- Suporte a tamanho de texto ampliado sempre que possível.

## 12. Regras de consistência
1. A biblioteca pode ser visualmente expressiva; o leitor deve ser calmo.
2. Uma cor de destaque por contexto; não transformar todo elemento em destaque.
3. Capas têm prioridade visual sobre decoração.
4. Não usar sombras fortes em todos os cards.
5. Não adicionar componente novo sem verificar se um existente pode ser reutilizado.
6. Tokens devem ser centralizados e não espalhados como valores arbitrários.
