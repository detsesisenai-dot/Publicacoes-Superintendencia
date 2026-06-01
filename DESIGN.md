---
name: "Informe Executivo Sistema FIEG"
description: "Ferramenta editorial interna para montar, revisar e exportar informes executivos institucionais."
colors:
  primary-blue: "#003A70"
  primary-red: "#E31937"
  surface-page: "#F4F6F9"
  surface-white: "#FFFFFF"
  surface-muted: "#F9FAFB"
  surface-panel: "#F3F4F6"
  ink: "#2B2D42"
  muted-text: "#5B667A"
  body-text: "#1F2937"
  neutral-border: "#E5E7EB"
  neutral-control-border: "#D1D5DB"
  neutral-hover: "#E5E7EB"
  info-soft: "#EFF6FF"
  danger: "#B91C1C"
  danger-soft: "#FEF2F2"
  success: "#166534"
  success-soft: "#F0FDF4"
  warning: "#92400E"
  warning-soft: "#FFFBEB"
typography:
  display:
    fontFamily: "Montserrat, sans-serif"
    fontSize: "2.25rem"
    fontWeight: 900
    lineHeight: 1.1
    letterSpacing: "-0.025em"
  headline:
    fontFamily: "Montserrat, sans-serif"
    fontSize: "1.5rem"
    fontWeight: 900
    lineHeight: 1.3
    letterSpacing: "0.025em"
  title:
    fontFamily: "Montserrat, sans-serif"
    fontSize: "1.25rem"
    fontWeight: 700
    lineHeight: 1.35
  body:
    fontFamily: "Montserrat, sans-serif"
    fontSize: "0.875rem"
    fontWeight: 500
    lineHeight: 1.6
  label:
    fontFamily: "Montserrat, sans-serif"
    fontSize: "0.75rem"
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "0.025em"
rounded:
  none: "0px"
  sm: "4px"
  md: "8px"
  lg: "12px"
  xl: "16px"
  full: "9999px"
spacing:
  xs: "4px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  xl: "20px"
  xxl: "24px"
  section: "40px"
components:
  button-primary:
    backgroundColor: "{colors.primary-blue}"
    textColor: "{colors.surface-white}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: "8px 16px"
  button-secondary:
    backgroundColor: "{colors.surface-white}"
    textColor: "{colors.primary-blue}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: "8px 16px"
  button-danger:
    backgroundColor: "{colors.danger}"
    textColor: "{colors.surface-white}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: "8px 20px"
  input-field:
    backgroundColor: "{colors.surface-muted}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: "8px"
  card-surface:
    backgroundColor: "{colors.surface-white}"
    textColor: "{colors.ink}"
    rounded: "{rounded.lg}"
    padding: "20px"
  modal-surface:
    backgroundColor: "{colors.surface-white}"
    textColor: "{colors.ink}"
    rounded: "{rounded.xl}"
    padding: "24px"
---

# Design System: Informe Executivo Sistema FIEG

## 1. Overview

**Creative North Star: "Mesa Editorial Executiva"**

O sistema atual combina uma mesa de trabalho editorial com acabamento executivo institucional. A interface precisa sustentar tarefas de importacao, revisao, organizacao, recorte de imagem e geracao de PDF sem competir com o conteudo jornalistico.

A estetica usa azul institucional, vermelho de alerta/marca, superficies brancas e uma camada de fundo cinza muito clara. A personalidade e formal, direta e operacional: moderna na organizacao, mas contida o suficiente para reforcar confianca em uma ferramenta de trabalho interno.

O sistema rejeita aparencia de peca publicitaria chamativa, editor amador de redes sociais, painel corporativo pesado ou pagina experimental. O visual deve facilitar leitura, revisao textual e tomada de decisao antes da exportacao.

**Key Characteristics:**
- Interface de produto, nao landing page.
- Paleta institucional restrita com azul como cor de acao, vermelho como enfase editorial e token proprio para perigo.
- Componentes densos, escaneaveis e voltados a revisao editorial.
- PDF final mais plano e normatizado que a interface web.
- Linguagem visual moderna, limpa e sem efeitos decorativos desnecessarios.

## 2. Colors

A paleta atual e institucional e restrita: azul profundo para identidade e acoes, vermelho para enfase editorial, perigo semantico para exclusao, fundos claros para leitura prolongada e neutros para estrutura.

### Primary
- **Azul Institucional**: cor de identidade, botoes primarios, icones principais, foco e linhas de estrutura.
- **Vermelho Editorial**: cor de enfase editorial, destaque de filtros ativos e indicacao visual controlada.

### Semantic
- **Perigo**: usado em exclusao, confirmacao destrutiva e estados que removem dados. Usa texto/fundo fortes o suficiente para WCAG AA.
- **Informacao**: usado em superficies azuis muito claras, seletores e estados de apoio vinculados ao eixo institucional.
- **Sucesso**: reservado para confirmacoes de salvamento, importacao concluida e processos finalizados.
- **Aviso**: reservado para pendencias, limites e estados que exigem atencao antes de gerar o PDF.

### Neutral
- **Fundo Operacional**: fundo principal da pagina, usado para separar a area de trabalho dos paineis brancos.
- **Superficie Branca**: base de cabecalho, filtros, modais, cards de revisao e conteudo do informe.
- **Superficie Muted**: fundos internos de campos, barras de acao, areas de upload e containers secundarios.
- **Tinta Executiva**: texto principal, titulos internos e conteudo institucional.
- **Texto Secundario**: metadados, descricoes e labels. O token deve permanecer escuro o suficiente para atingir WCAG AA em superficies brancas e cinza claro.
- **Borda Neutra**: divisoes, contornos de campos, separadores e bordas de cards.

### Named Rules

**The Institutional Accent Rule.** Azul e vermelho devem aparecer como acao, identidade ou enfase editorial. Eles nao devem virar decoracao de fundo.

**The Contrast Rule.** Texto secundario precisa manter contraste WCAG AA. Nunca use cinza claro para labels, placeholders ou metadados importantes.

**The Semantic State Rule.** Vermelho institucional pode comunicar enfase editorial, mas acoes destrutivas devem usar o token Perigo. Estados de informacao, sucesso e aviso devem usar pares de texto/fundo ja verificados.

## 3. Typography

**Display Font:** Montserrat (with sans-serif fallback)
**Body Font:** Montserrat (with sans-serif fallback)
**Label/Mono Font:** Montserrat (no mono role currently defined)

**Character:** A tipografia atual usa uma unica familia para manter unidade entre interface e PDF. Pesos altos criam tom executivo; tamanhos pequenos e labels em caixa alta criam densidade operacional.

### Hierarchy
- **Display** (900, 2.25rem, 1.1): usado no titulo "INFORME EXECUTIVO" e na capa do PDF.
- **Headline** (900, 1.5rem, 1.3): usado em titulos de secao como "Panorama das Unidades".
- **Title** (700, 1.25rem, 1.35): usado em modais, etapa de revisao e titulos de materia.
- **Body** (500, 0.875rem, 1.6): usado em campos, botoes, texto de apoio e corpo editorial na interface.
- **Label** (700, 0.75rem, 0.025em, uppercase): usado em filtros, formularios e metadados. Deve ser curto, nunca frases completas.

### Named Rules

**The Editorial Reading Rule.** Campos de titulo, lead e corpo precisam favorecer leitura precisa. Texto de apoio pode ser compacto, mas conteudo editorial nao deve parecer comprimido.

**The One Family Rule.** Enquanto o PDF depender de Montserrat, a interface tambem deve usar Montserrat para manter continuidade entre tela e documento final.

## 4. Elevation

O sistema atual usa um hibrido de elevacao leve e camadas tonais. A interface web usa sombras pequenas para separar cabecalho, botoes, cards e modais. O modo PDF remove sombras, bordas e raios para gerar uma pagina mais plana e previsivel.

### Shadow Vocabulary
- **Shadow Low** (`box-shadow: Tailwind shadow-sm`): usado em cards, cabecalho, filtros e botoes secundarios para separar superficies brancas do fundo claro.
- **Shadow Medium** (`box-shadow: Tailwind shadow-md`): usado em botoes primarios, acoes de confirmacao e controles sobre imagens.
- **Shadow Modal** (`box-shadow: Tailwind shadow-2xl`): usado nos modais principais para separar a camada de dialogo do overlay.
- **PDF Flat Mode** (`box-shadow: none; border: none; border-radius: 0`): aplicado em modo PDF para renderizacao limpa.

### Named Rules

**The Flat PDF Rule.** Qualquer elevacao visual da interface deve desaparecer no PDF final. O documento exportado precisa parecer normativo, nao uma captura de tela.

## 5. Components

### Buttons

- **Shape:** cantos moderadamente arredondados (8px), com botoes de icone podendo usar formato circular.
- **Primary:** fundo Azul Institucional, texto branco, peso 600-700, icone Phosphor a esquerda e padding compacto.
- **Hover / Focus:** hover escurece ou clareia a superficie; foco usa anel azul. Estados de foco devem ficar visiveis em todos os botoes.
- **Secondary / Ghost / Tertiary:** secundarios usam fundo branco ou cinza claro com texto azul ou cinza. Acoes destrutivas usam vermelho apenas quando a destruicao e confirmada.

### Chips

- **Style:** nao ha chip dedicado. Filtros ativos aparecem como texto vermelho no cabecalho.
- **State:** filtros selecionados sao refletidos em subtitulo textual e no PDF, nao em chips removiveis.

### Cards / Containers

- **Corner Style:** cards e paineis principais usam cantos de 12px; modais usam 16px.
- **Background:** superficies brancas sobre fundo operacional claro.
- **Shadow Strategy:** sombra leve em repouso; modais usam sombra forte. No PDF, sombras sao removidas.
- **Border:** bordas cinza claras reforcam campos, cards de revisao e separadores.
- **Internal Padding:** paineis usam 20px a 24px; areas de upload usam 40px.

### Inputs / Fields

- **Style:** campos com borda cinza, fundo cinza muito claro e raio de 8px na area de filtros; campos de edicao usam raio de 4px.
- **Focus:** anel azul em campos principais. Alguns campos dinamicos ainda usam `focus:outline-none` sem alternativa robusta e devem ser corrigidos.
- **Error / Disabled:** nao ha vocabulario visual completo para erro, sucesso, desabilitado e carregando. Esses estados devem ser definidos antes de ampliar a ferramenta.

### Navigation

- **Style:** nao ha navegacao de paginas. A estrutura atual e orientada por fluxo: cabecalho, filtros, lista de materias, modal de importacao, modal de edicao, modal de recorte e modal de confirmacao.
- **Mobile treatment:** a interface usa colunas responsivas via Tailwind, mas os grupos de botoes e filtros ainda precisam de teste visual em telas pequenas.

### Editorial Report Card

O card de materia e o componente central. Ele combina barra de inclusao no PDF, acoes de editar/apagar, unidade, data, eixo, imagem widescreen, lead em destaque e corpo do texto. Na tela, ele funciona como preview editavel do material; no PDF, perde controles e assume formato documental.

### Import Review Card

O card de revisao aparece apos importar Word. Ele concentra miniatura, unidade, data, manchete, lead, corpo e eixo. A densidade e alta por necessidade operacional, mas os labels, contadores e contraste precisam ser tratados com rigor para nao cansar a leitura.

## 6. Do's and Don'ts

### Do:

- **Do** preservar a linguagem de produto interno: comandos claros, estados explicitos e telas voltadas a revisao editorial.
- **Do** usar Azul Institucional para acao primaria, foco, icones importantes e estrutura de documento.
- **Do** usar Vermelho Editorial para filtros ativos ou enfase editorial controlada, reservando o token Perigo para exclusao.
- **Do** manter o PDF visualmente mais plano que a tela, com tipografia consistente e paginas previsiveis.
- **Do** escrever rotulos em portugues formal do Brasil, sem abreviacoes desnecessarias.
- **Do** garantir contraste WCAG AA antes de reutilizar cinzas em labels, placeholders e metadados.

### Don't:

- **Don't** fazer a interface parecer uma peca publicitaria chamativa.
- **Don't** fazer a ferramenta parecer um editor amador de redes sociais.
- **Don't** criar um painel corporativo pesado ou uma pagina experimental.
- **Don't** usar excesso de efeitos visuais, caixas competindo por atencao ou decoracao sem funcao.
- **Don't** usar bordas laterais coloridas grossas como padrao visual; prefira borda completa fina, fundo suave ou icone de estado.
- **Don't** misturar portugues europeu com portugues do Brasil em comandos de interface.
- **Don't** depender de texto cinza claro para informacoes importantes.
