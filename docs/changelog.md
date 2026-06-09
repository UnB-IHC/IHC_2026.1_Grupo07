# Registro de Mudanças – Pocket V2 (Grupo 07, 2026)

**Data:** Junho de 2026  
**Versão anterior:** V1 – VerificaAAA (grupo anterior, 2024)  
**Versão atual:** V2 – VerificaAAA (Grupo 07 – IHC 2026.1)  
**Tarefa:** TG-01 – Melhoria do Guia de Acessibilidade (POCKET)  

---

## Motivação das Mudanças

A versão V1 (VerificaAAA, 2024) foi produzida antes da publicação de duas referências normativas essenciais:

1. **WCAG 2.2** (W3C, outubro de 2023) – adicionou 9 critérios novos e removeu 1 critério obsoleto (4.1.1 Parsing)
2. **ABNT NBR 17225:2025** – norma técnica brasileira que adota o WCAG 2.2 como base legal obrigatória para serviços digitais no Brasil

Esta versão incorpora ambas as referências, marca os itens novos explicitamente com `[NOVO WCAG 2.2]` ou `[NOVO NBR/WCAG 2.2]` e melhora a seção de ferramentas conforme orientação da TG-01.

---

## Arquivos Modificados

### `docs/tools/ferramentas.md` — Reestruturação completa

**Antes (V1):** Lista simples de 8 ferramentas com links, sem descrição, sem avaliação, sem passo a passo.

**Depois (V2):**

| Mudança | Detalhamento |
|---|---|
| Tabela comparativa de ferramentas | "Qual usar para quê?" com tipo, melhor uso e limitação principal |
| Passo a passo: axe DevTools | Instalação, uso, classificação de severidade, integração CI/CD |
| Passo a passo: Lighthouse | Configuração de auditoria, interpretação da pontuação, limitações |
| Passo a passo: WAVE | Uso da sobreposição visual, diferencial vs axe |
| Passo a passo: Colour Contrast Analyser | Como usar conta-gotas para WCAG 1.4.3, 1.4.11 e **2.4.13** |
| Passo a passo: NVDA | Instalação, teclas essenciais, roteiro mínimo de teste |
| Passo a passo: VoiceOver | Ativação, teclas essenciais, uso do Rotor |
| Passo a passo: Teste por teclado | Roteiro completo sem mouse |
| Ferramentas novas adicionadas | NVDA, VoiceOver, Colour Contrast Analyser (CCA/TPGi), Teste manual por teclado |
| Nota metodológica | Ferramentas automatizadas cobrem apenas ~30-40% dos critérios WCAG |
| Matriz de cobertura | Tabela cruzando ferramentas × critérios WCAG 2.2, com destaque para os 5 critérios novos sem cobertura automatizada |
| Referências | W3C WCAG 2.2, ABNT NBR 17225:2025, TG10 Grupo 7 |

**Fonte:** TG10 – Estudo Aprofundado WCAG 2.2 (Grupo 7, 2026), seção 8.3; ABNT NBR 17225:2025, seção 6.

---

### `docs/devWeb/non_text_content.md` — Adição de 6 critérios WCAG 2.2 novos

**Nota de obsolescência:** O critério **4.1.1 Parsing** foi **removido** do WCAG 2.2 por ser obsoleto no contexto moderno de parsing de HTML. Referências a ele na V1 (RP15) foram mantidas com nota de contexto.

| Item Adicionado | Seção | Critério WCAG 2.2 | Nível | NBR 17225:2025 |
|---|---|---|---|---|
| Foco não obscurecido por sticky headers | Teclado | 2.4.11 | AA | 5.1.1, 5.1.3 |
| Técnica `scroll-margin-top` para foco | Teclado | 2.4.11 | AA | 5.1.1 |
| Tamanho mínimo de alvo **24×24px** (corrigido de 44px que é AAA) | Ferramentas e extras | 2.5.8 | AA | 5.8.7 |
| Alternativa a drag-and-drop | Ferramentas e extras | 2.5.7 | AA | 5.8.13 |
| Autenticação sem teste cognitivo (CAPTCHA) | Ferramentas e extras | 3.3.8 | AA | 5.9.18 |
| Não re-solicitar dados já fornecidos | Ferramentas e extras | 3.3.7 | A | 5.9.15 |
| Ajuda consistente na mesma posição | Ferramentas e extras | 3.2.6 | A | 5.7.15 |
| Nota introdutória sobre WCAG 2.2 e NBR | Cabeçalho | — | — | — |

**Correção de V1:** O item "44px de altura e largura" na seção "Ferramentas e extras" estava correto para AAA (WCAG 2.5.5), mas o mínimo obrigatório AA do WCAG 2.2 é **24×24px** (critério 2.5.8, novo em 2.2). O texto foi corrigido para refletir ambos os valores com seus níveis corretos.

---

### `docs/design/design.md` — Adição de critério de aparência do foco

| Item Adicionado | Seção | Critério WCAG 2.2 | Nível | NBR 17225:2025 |
|---|---|---|---|---|
| Indicador de foco com contraste ≥ 3:1 e espessura ≥ 2px | Contraste de Cores | 2.4.13 | AAA | 5.1.3 |
| Proibição de remover outline sem substituto | Contraste de Cores | 2.4.13 | AAA | 5.1.3 |
| Nota introdutória sobre WCAG 2.2 e NBR | Cabeçalho | — | — | — |

---

### `docs/gestaoProjeto/gestaoProjeto.md` — Contexto legal e NBR

| Item Adicionado | Detalhamento |
|---|---|
| Bloco de contexto legal | LBI (13.146/2015), Decreto 5.296/2004, ABNT NBR 17225:2025 |
| Critério: referência à NBR nos critérios de aceitação | Novo item de checklist de planejamento |
| Critério: combinação de testes automatizados e manuais | Referência ao limite de 30-40% de cobertura automatizada |
| Critério: abordagem Shift-left | Acessibilidade desde o início, não como correção retroativa |
| Referências bibliográficas | WCAG 2.2 e ABNT NBR 17225:2025 adicionadas |

---

## Critérios WCAG 2.2 Cobertos pela V2 (Novos em Relação à V1)

| Critério | Descrição | Nível | Arquivo |
|---|---|---|---|
| 2.4.11 | Foco Não Obscurecido (Mínimo) | AA | devWeb |
| 2.4.12 | Foco Não Obscurecido (Aprimorado) | AAA | devWeb (nota) |
| 2.4.13 | Aparência do Foco | AAA | design |
| 2.5.7 | Movimentos de Arrastar | AA | devWeb |
| 2.5.8 | Tamanho do Alvo, Mínimo | AA | devWeb |
| 3.2.6 | Ajuda Consistente | A | devWeb |
| 3.3.7 | Entrada Redundante | A | devWeb |
| 3.3.8 | Autenticação Acessível (Mínimo) | AA | devWeb |
| 3.3.9 | Autenticação Acessível (Aprimorado) | AAA | devWeb (nota) |

---

## Critério Removido do WCAG 2.2 (Nota de Atenção)

| Critério | Descrição | Status |
|---|---|---|
| 4.1.1 Parsing | Validação de HTML | **Removido** do WCAG 2.2 (outubro 2023). Era referenciado na V1 como RP15. O critério foi considerado obsoleto pois navegadores modernos lidam com HTML malformado de forma consistente. A NBR 17225:2025 não o inclui. |

---

## Referências das Mudanças

- W3C. **Web Content Accessibility Guidelines (WCAG) 2.2**. World Wide Web Consortium, outubro 2023. Disponível em: https://www.w3.org/TR/WCAG22/
- ABNT. **NBR 17225:2025** – Acessibilidade em ambientes virtuais. 2025.
- GRUPO 7 – IHC 2026.1. **TG10 – Estudo Aprofundado da WCAG 2.2**. Universidade de Brasília, junho de 2026.
- W3C WAI. **Understanding WCAG 2.2**. Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/
- DEQUE SYSTEMS. **Axe Core Accessibility Rules**. Disponível em: https://dequeuniversity.com/rules/axe/
