---
target: "index.html#pdf-export"
total_score: 28
p0_count: 0
p1_count: 2
timestamp: 2026-06-02T19-02-17Z
slug: index-html-pdf-export
---
## Design Health Score

| # | Heuristic | Score | Key Issue |
|---|-----------|-------|-----------|
| 1 | Visibility of System Status | 3 | Overlay informa progresso, agora com texto mais específico. |
| 2 | Match System / Real World | 3 | O PDF passou a ser composto como documento oficial, não como captura de tela. |
| 3 | User Control and Freedom | 3 | A exportação respeita filtros e matérias desmarcadas. |
| 4 | Consistency and Standards | 3 | Cores e estrutura seguem o design institucional; fonte nativa do PDF ainda não replica Montserrat. |
| 5 | Error Prevention | 3 | Bloqueia exportação vazia e não falha se a logo externa não converter. |
| 6 | Recognition Rather Than Recall | 3 | Capa resume filtro e quantidade exportada. |
| 7 | Flexibility and Efficiency | 3 | Exporta direto o recorte visível sem exigir pré-visualização manual. |
| 8 | Aesthetic and Minimalist Design | 3 | Removeu a camada antiga de modo PDF e reduziu ornamentação de borda no cabeçalho. |
| 9 | Error Recovery | 2 | Erro ainda aparece como alerta simples, sem detalhes acionáveis para a usuária. |
| 10 | Help and Documentation | 2 | Não há explicação curta sobre dependência de biblioteca externa ou ausência de imagem. |
| **Total** | | **28/40** | **Good, with residual hardening opportunities** |

## Anti-Patterns Verdict

A causa raiz era estrutural: o fluxo antigo tentava transformar a interface inteira em PDF por captura de DOM com html2canvas/html2pdf. Esse padrão é frágil para documento institucional, porque depende de estilos computados, fontes carregadas, canvas, largura fixa e quebras de página CSS. A nova implementação gera o PDF por composição direta em jsPDF, com capa, cabeçalho, rodapé, texto medido, imagem em proporção 2:1, lead destacado e continuação automática quando o texto ultrapassa a página.

Detector: após a correção, os avisos restantes são Montserrat como fonte única e fonte comum. Neste projeto isso é falso positivo, porque PRODUCT.md/DESIGN.md definem Montserrat como decisão de continuidade entre interface e relatório. O detector também deixou de acusar a borda grossa no cabeçalho após a troca por borda completa discreta.

## Overall Impression

A exportação ficou muito mais confiável: saiu de uma fotografia da tela para um documento composto. O maior ganho é previsibilidade de paginação. O maior risco remanescente é a fidelidade tipográfica exata, porque jsPDF usa fontes nativas salvo se Montserrat for embutida no PDF.

## What's Working

- O relatório agora respeita o recorte editorial visível: filtros e matérias ocultadas pelo checkbox entram corretamente no conjunto exportado.
- A capa e os rodapés dão contexto institucional: quantidade de pautas, filtros, data de geração e paginação total.
- A rotina tolera falha de conversão da logo externa e imagem de matéria inválida sem derrubar toda a exportação.

## Priority Issues

**[P1] Exportação antiga por captura visual do DOM**
Why it matters: qualquer atraso de fonte, largura fixa ou regra CSS não suportada pelo canvas quebrava completamente a formatação.
Fix: substituído por geração direta em jsPDF, com layout controlado por medidas de página.
Suggested command: $impeccable harden

**[P1] Exportação sem validação de pauta selecionada**
Why it matters: a usuária podia gerar um PDF vazio quando filtros ou checkboxes removiam tudo.
Fix: adicionada validação antes da composição e mensagem clara.
Suggested command: $impeccable clarify

**[P2] Camada antiga de pdf-mode criava manutenção enganosa**
Why it matters: futuras correções poderiam mexer em CSS que já não participa do PDF, perpetuando a causa do problema.
Fix: removida a capa invisível e o bloco CSS de modo PDF.
Suggested command: $impeccable distill

**[P2] Montserrat ainda não está embutida no PDF**
Why it matters: o layout agora se mantém, mas a tipografia do arquivo pode não ser idêntica à interface.
Fix: em uma próxima passada, embutir a fonte Montserrat no jsPDF ou aceitar formalmente uma fonte PDF nativa para exportação.
Suggested command: $impeccable typeset

## Persona Red Flags

**Redatora operacional**: antes, ela não tinha confiança de que o PDF final corresponderia ao relatório revisado na tela. O novo fluxo melhora isso com composição determinística, mas ainda não oferece pré-visualização de páginas antes do download.

**Revisora institucional**: precisa de documento estável para circulação. A hierarquia agora é consistente, mas a diferença de fonte pode ser percebida em revisão visual rigorosa.

**Usuária em prazo curto**: precisa saber rápido se gerou o arquivo certo. O bloqueio de exportação vazia e o resumo de filtros na capa reduzem erro de envio.

## Minor Observations

- O projeto ainda usa alguns z-index arbitrários em modais e overlay, fora do escopo do PDF.
- Algumas mensagens de erro ainda são alertas nativos, suficientes para falha simples, mas pobres para diagnóstico.
- A dependência externa de CDN continua sendo ponto de fragilidade operacional.

## Questions to Consider

- O PDF oficial precisa ser visualmente idêntico à interface ou pode usar fonte nativa estável de PDF?
- A redatora precisa revisar uma prévia paginada antes de baixar o arquivo?
- As imagens sem exportação deveriam aparecer como aviso na capa, em vez de apenas placeholder na página da pauta?
