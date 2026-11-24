# FORMATOS E IMPORTAÇÃO — KIRIA

## 1. Objetivo
Definir suporte transparente a formatos de quadrinhos, novels e documentos, sem prometer compatibilidade que ainda não foi testada.

## 2. Matriz de formatos
| Formato | Uso | Prioridade | Observações |
|---|---|---:|---|
| PDF | Novels e documentos | MVP | Preservar layout; renderização progressiva |
| JPG/JPEG | Páginas e imagens | MVP | Ordenação e agrupamento |
| PNG | Páginas e imagens | MVP | Atenção ao consumo de memória |
| WebP | Páginas e imagens | MVP | Validar decodificação no Android alvo |
| ZIP | Arquivos de imagens | MVP condicionado | Identificar estrutura e ordenar entradas |
| CBZ | Quadrinhos compactados | MVP condicionado | Geralmente baseado em ZIP; validar arquivos reais |
| EPUB | Novels | Pós-MVP | Texto refluível; testar navegação e fontes |
| TXT | Novels simples | Pós-MVP | Codificação e quebras de linha |
| CBR/RAR | Quadrinhos | Futuro | Dependência e compatibilidade devem ser avaliadas |
| CB7/7z | Quadrinhos | Futuro | Avaliar suporte e custo de processamento |

## 3. Regras de importação
- O arquivo original não deve ser alterado.
- O app deve informar o nome, tamanho e tipo detectado.
- Extensão não é prova suficiente do formato.
- Arquivos inválidos devem gerar mensagem compreensível.
- Importação em lote deve mostrar progresso e permitir cancelamento seguro.
- Duplicatas podem ser sinalizadas por nome/tamanho e, futuramente, checksum; não apagar automaticamente.

## 4. Organização de quadrinhos
- Permitir que uma pasta de imagens seja importada como capítulo.
- Ordenar nomes com ordenação natural (`2` antes de `10`).
- Permitir corrigir manualmente a ordem.
- Ignorar arquivos ocultos e metadados do sistema quando apropriado.
- Não interpretar automaticamente imagens não reconhecidas como páginas sem confirmação.

## 5. PDF
- Usar renderização por página, não converter o documento inteiro em imagens de uma só vez.
- Preservar proporção e orientação.
- Salvar página atual e, se viável, deslocamento dentro da página.
- Oferecer zoom e ajuste à largura.
- Não prometer alteração de fonte, margens ou reflow para PDFs comuns.
- Testar PDFs grandes, digitalizados, com texto selecionável e com rotação.

## 6. EPUB e TXT
- EPUB deve preservar capítulos, sumário e marcadores quando possível.
- Oferecer ajustes de fonte, tamanho, altura de linha, margem e tema.
- TXT deve permitir detecção/seleção de codificação quando necessário.
- Validar arquivos malformados e conteúdo muito grande.

## 7. Limites e mensagens
Mensagens devem distinguir:
- formato não suportado;
- arquivo corrompido;
- arquivo protegido ou não legível;
- espaço insuficiente;
- importação cancelada;
- erro de leitura;
- arquivo já importado.

## 8. Testes de aceitação
- Importar, fechar e reabrir cada formato suportado.
- Ler offline.
- Retomar posição.
- Verificar ordenação.
- Testar arquivos grandes e lotes.
- Confirmar que o arquivo de origem permanece intacto.
