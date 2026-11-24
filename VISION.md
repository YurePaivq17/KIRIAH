# VISION — KIRIA

## 1. Visão do produto
KIRIA é uma biblioteca digital pessoal para reunir, organizar e ler mangás, manhwas, manhuas e novels em um único aplicativo mobile. O produto prioriza leitura confortável, biblioteca organizada, privacidade e disponibilidade offline.

## 2. Problema
Arquivos de leitura ficam dispersos em pastas e aplicativos diferentes. É difícil manter uma visão consistente da biblioteca, retomar exatamente de onde a leitura parou e alternar entre formatos de imagem, quadrinhos compactados e documentos de texto.

## 3. Objetivos
1. Importar arquivos locais com fluxo simples.
2. Organizar obras, volumes e capítulos.
3. Oferecer modos de leitura apropriados para quadrinhos e novels.
4. Salvar progresso automaticamente.
5. Funcionar sem conexão após a importação.
6. Preservar os arquivos originais e permitir exportação/backup dos dados da biblioteca.

## 4. Usuário e contexto
- Uso individual e pessoal.
- Principal dispositivo: celular Android.
- Armazenamento: local no dispositivo.
- Conectividade: não deve ser necessária para ler conteúdo já importado.
- Interface: português como idioma inicial, preparada para internacionalização futura.

## 5. Pilares da experiência
### Biblioteca
Visão geral com busca, filtros, coleções, favoritos, status e ordenação.

### Leitura de quadrinhos
Visualização por página, direção de leitura configurável, modo vertical contínuo, zoom e navegação por capítulo.

### Leitura de novels
Leitura de PDF, EPUB e TXT, com controles de tipografia quando o formato permitir. PDF deve manter seu layout original; não prometer reflow de PDF.

### Continuidade
Retomar leitura, salvar posição e registrar histórico sem exigir ação manual.

### Privacidade e controle
Dados e arquivos permanecem no dispositivo. O usuário deve poder exportar metadados e remover conteúdo importado com confirmação.

## 6. Escopo por prioridade
### MVP
- Importação de PDF e imagens.
- Importação de CBZ/ZIP, após validação técnica.
- Biblioteca com metadados editáveis.
- Leitor de imagens com página única e rolagem vertical.
- Leitor PDF.
- Progresso, favoritos, busca simples e histórico.
- Persistência local e tratamento de falta de espaço.

### Pós-MVP
- EPUB e TXT.
- Coleções personalizadas.
- Marcadores e anotações.
- Estatísticas e metas.
- Importação em lote e reconhecimento assistido de metadados.
- Suporte adicional a formatos compactados após avaliação.

## 7. Não objetivos
- Hospedar ou distribuir obras.
- Buscar capítulos em sites de terceiros.
- Sincronizar entre dispositivos na primeira versão.
- Criar contas ou backend na primeira versão.
- Prometer suporte universal a qualquer arquivo compactado sem testes.

## 8. Métricas de qualidade
- Importação apresenta resultado claro: sucesso, falha ou formato não suportado.
- A leitura reabre na última posição salva.
- A biblioteca permanece disponível offline.
- Arquivos originais não são alterados durante a leitura.
- Erros de armazenamento não causam perda silenciosa de metadados.
- Interface utilizável em telas pequenas e com acessibilidade básica.

## 9. Critérios de sucesso do MVP
Uma pessoa consegue importar um arquivo PDF e um conjunto de imagens/CBZ, encontrá-los na biblioteca, ler offline, fechar o aplicativo e continuar do ponto salvo após reabri-lo.
