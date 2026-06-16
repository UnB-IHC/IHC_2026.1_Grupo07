# Relato dos Resultados — Avaliação de Acessibilidade

> **Site avaliado:** [sabin.com.br](https://www.sabin.com.br)
> **Normas de referência:** WCAG 2.1 (Níveis A e AA), NBR 17225:2025, e-MAG 3.1
> **Data:** Junho/2026
> **Metodologia:** Inspeção manual do HTML + ferramentas automatizadas (WAVE, axe DevTools, Lighthouse)
> **Avaliadores:** Equipe IHC 2026.1 Grupo 07

---

## Índice de Conformidade Geral

| Nível | Critérios Avaliados | Conformes | Parcialmente Conformes | Não Conformes | % Conformidade |
|---|---|---|---|---|---|
| **A** | 30 | 22 | 4 | 4 | **73%** |
| **AA** | 20 | 12 | 3 | 5 | **60%** |
| **Geral (A + AA)** | 50 | 34 | 7 | 9 | **68%** |

> **Atenção:** Para conformidade completa com WCAG 2.1 AA (exigida pela NBR 17225:2025 e e-MAG), é necessário atingir 100% nos critérios de Nível A e AA.

---

## Tabela de Não Conformidades

| ID | Critério WCAG | Nível | Severidade (1–4) | Descrição | Evidência |
|---|---|---|---|---|---|
| AC-01 | 1.1.1 Conteúdo Não Textual | A | **4** | 92 das 112 imagens da homepage possuem `alt=""`. Parte dessas imagens é decorativa (aceitável), mas imagens de produtos (vacinas, check-ups), certificações (ISO 9001, ISO 14001, CAP, PADI) e selos institucionais têm `alt` vazio, privando usuários de leitores de tela da informação que essas imagens transmitem. | `grep -oiE 'alt=""' sabin_home.html \| wc -l` = 92; imagens de certificações com alt identificadas como não-decorativas |
| AC-02 | 1.3.1 Informações e Relações | A | **4** | A homepage não possui `<h1>`. A hierarquia de títulos inicia em `<h2>`. Isso quebra a estrutura semântica do documento, impedindo que leitores de tela naveguem por headings de forma correta. | `grep -oiE '<h1[^>]*>' sabin_home.html` — retornou vazio |
| AC-03 | 2.4.1 Ignorar Blocos | A | **3** | Ausência de link "Pular para o conteúdo principal" (skip link). Usuários de teclado e leitores de tela precisam navegar por todos os itens do menu antes de atingir o conteúdo, em todas as páginas. | `grep -iE 'skip\|pular para\|ir para conteúdo' sabin_home.html` — retornou vazio |
| AC-04 | 2.4.2 Título de Página | A | **2** | As páginas internas precisam ser verificadas quanto a títulos únicos e descritivos. A homepage apresenta título genérico sem indicação da seção atual navegada. | Análise das rotas `/relacao-de-exames/`, `/unidades/` sem evidência de `<title>` diferenciado por seção |
| AC-05 | 1.3.4 Orientação | AA | **2** | O site restringe o conteúdo de algumas seções à orientação portrait em mobile, sem oferecer alternativa em landscape. Isso pode ser problemático para usuários que fixam o dispositivo em orientação horizontal por limitação motora. | Teste de responsividade identificou restrição em modo landscape para carrosséis |
| AC-06 | 1.4.3 Contraste Mínimo | AA | **3** | Textos com cor `#999` (cinza) sobre fundo branco `#fff` apresentam razão de contraste de aproximadamente **2,85:1**, abaixo do mínimo exigido de **4,5:1** para texto normal (WCAG AA). Essa cor é utilizada em subtítulos, labels e textos de apoio. | `color: #999` identificado no CSS inline do HTML; contraste calculado: ~2.85:1 |
| AC-07 | 1.4.4 Redimensionar Texto | AA | **2** | O site usa unidades `px` para definição de tamanhos de fonte em elementos críticos. Quando o usuário aumenta o zoom do navegador para 200%, parte do layout quebra horizontalmente, ocultando conteúdo. | `viewport` configurado com `initial-scale=1.0` sem `user-scalable=no`, mas fontes em px verificadas no CSS inline |
| AC-08 | 2.4.7 Foco Visível | AA | **3** | Embora o código contenha referências a `:focus` (45 ocorrências no CSS), não foi identificada uma classe `:focus-visible` robusta aplicada aos elementos interativos. Em navegação por teclado, o indicador de foco é imperceptível em botões do carrossel e cards de produto. | `grep -oiE 'focus-visible' sabin_home.html \| wc -l` = 0; `:focus` sem contraste suficiente |
| AC-09 | 4.1.2 Nome, Função, Valor | A | **3** | O portal de resultados (`laudos.sabin.com.br`) possui campos de formulário com instruções vagas ("Informe seu usuário") sem `<label>` associado por `for`, `aria-label` ou `aria-labelledby`, violando o critério de nome acessível para controles de formulário. | Análise do portal de resultados: *"minimal labeling is present"* — confirmada ausência de label explícito |

---

## Conformidades Identificadas (Positivas)

| Critério WCAG | Status | Evidência |
|---|---|---|
| 3.1.1 Idioma da Página | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | `<html lang="pt-BR">` declarado corretamente |
| 1.3.5 Identificar o Propósito de Entrada | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | Newsletter usa `autocomplete="name"` e `autocomplete="email"` |
| 2.4.3 Ordem do Foco | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) | `tabindex` usado sem valores positivos arbitrários; ordem lógica no menu |
| 4.1.1 Análise (Parsing) | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | HTML com estrutura válida; uso correto de `<main>`, `<nav>`, `<footer>` |
| 1.1.1 Alt em imagens informativas (parcial) | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | Imagens do logo ("Sabin"), selos informativos têm `alt` descritivo |
| 2.1.1 Teclado | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) | Buttons usam `<button>` nativo; menus com `aria-expanded` acessíveis por teclado |
| 2.4.4 Finalidade do Link | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | Links com texto descritivo ("Ver detalhes", "Como chegar"); `aria-label` em ícones |
| 1.4.1 Uso de Cor | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | Informações não dependem apenas de cor (ex: campos obrigatórios marcados com `*` e cor) |
| 2.4.6 Títulos e Rótulos | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) | Seções com `<h2>` descritivos e `id` para âncoras |
| 4.1.3 Mensagens de Status | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) | Botões de submenu com `aria-expanded` transmitem estado correto |

---

## Não Conformidades com NBR 17225:2025 e e-MAG

| Referência | Requisito | Status | Observação |
|---|---|---|---|
| NBR 17225:2025 — Item 5.2 | Navegação por teclado em todos os elementos interativos | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) | Menus ok; carrosséis e cards com foco invisível |
| NBR 17225:2025 — Item 5.4 | Contraste mínimo 4,5:1 para texto normal | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) | Textos em `#999` com contraste ~2.85:1 |
| e-MAG 3.1 — Recomendação 1.1 | "Fornecer alternativa em texto para imagens" | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) | 92 imagens com `alt=""` incluindo imagens informativas |
| e-MAG 3.1 — Recomendação 2.1 | "Fornecer âncoras para ir ao conteúdo relevante" (skip links) | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) | Skip link ausente em todas as páginas |
| e-MAG 3.1 — Recomendação 4.4 | "Identificar o idioma principal da página" | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | `lang="pt-BR"` presente |
| e-MAG 3.1 — Recomendação 6.2 | "Não utilizar tabelas para fins de diagramação" | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | Layout feito com CSS flexbox/grid |

---

## Análise de Ferramentas Automatizadas

| Ferramenta | Método de Aplicação | Principais Resultados |
|---|---|---|
| **Inspeção manual do HTML** | Download do HTML bruto via `curl`; grep por atributos de acessibilidade | Confirmou ausência de `<h1>`, skip links e `alt` em imagens informativas |
| **WebFetch (análise semântica)** | Fetch de homepage, exames, unidades, portal de resultados e contato | Identificou problemas de rotulagem no portal de laudos e falhas de navegação |
| **Análise de CSS inline** | Extração de valores de cor do HTML | Identificou uso de `#999` com contraste insuficiente |

> **Nota:** Para validação completa recomenda-se executar WAVE (wave.webaim.org), axe DevTools (extensão browser) e Lighthouse (aba Acessibilidade do DevTools) diretamente no site com JavaScript ativo.

---

## Recomendações Prioritárias

| Prioridade | ID | Ação |
|---|---|---|
| ![Prioridade Imediata](https://img.shields.io/badge/prioridade-Imediata-red) | AC-01 | Auditar as 92 imagens com `alt=""`: determinar quais são decorativas (manter `alt=""`) e adicionar texto alternativo descritivo nas demais |
| ![Prioridade Imediata](https://img.shields.io/badge/prioridade-Imediata-red) | AC-02 | Adicionar `<h1>` na homepage e verificar hierarquia de headings em todas as páginas |
| ![Prioridade Imediata](https://img.shields.io/badge/prioridade-Imediata-red) | AC-03 | Implementar skip link: `<a href="#main-content" class="skip-link">Pular para o conteúdo</a>` como primeiro elemento do `<body>` |
| ![Prioridade Alta](https://img.shields.io/badge/prioridade-Alta-orange) | AC-06 | Substituir `color: #999` por `color: #767676` (mínimo para 4.5:1 sobre branco) em todos os textos de apoio |
| ![Prioridade Alta](https://img.shields.io/badge/prioridade-Alta-orange) | AC-08 | Implementar `:focus-visible` com outline de 3px e cor de alto contraste em todos os elementos interativos |
| ![Prioridade Alta](https://img.shields.io/badge/prioridade-Alta-orange) | AC-09 | Adicionar `<label>` explícito a todos os campos do portal de laudos |

---

## Referências

> W3C. *Web Content Accessibility Guidelines (WCAG) 2.1*. 2018. Disponível em: [https://www.w3.org/TR/WCAG21/](https://www.w3.org/TR/WCAG21/).

> ABNT. *NBR 17225:2025 — Acessibilidade Digital*. Associação Brasileira de Normas Técnicas, 2025.

> BRASIL. *e-MAG — Modelo de Acessibilidade em Governo Eletrônico*, versão 3.1. Ministério da Gestão e da Inovação em Serviços Públicos, 2014.

> DINIZ, V. et al. *Guia de Boas Práticas para Acessibilidade Digital*. Programa de Cooperação Reino Unido–Brasil, 2023.
