# Relato dos Resultados — Avaliação de Acessibilidade

> **Site avaliado:** [sabin.com.br](https://www.sabin.com.br)
> **Normas de referência:** WCAG 2.2, NBR 17225:2025, e-MAG 3.1 — conforme Checklist PocketV2 (Grupo 07)
> **Data:** Junho/2026
> **Metodologia:** Inspeção manual do HTML bruto + análise semântica de múltiplas rotas do site
> **Avaliadores:** Equipe IHC 2026.1 Grupo 07

---

## Índice de Conformidade por Seção

| Seção | Itens Avaliáveis | Conformes | Parciais | Não Conformes | Não Verificáveis | % Conformidade¹ |
|---|---|---|---|---|---|---|
| A — Percepção Visual e Auditiva | 5 | 1 | 2 | 2 | 0 | **40%** |
| B — Operabilidade e Navegação | 5 | 1 | 1 | 2 | 1 | **37,5%** (excl. N/V) |
| C — Compreensibilidade e Ajuda | 6 | 1 | 1 | 3 | 1 | **30%** (excl. N/V) |
| D — Robustez e Código Semântico | 2 | 0 | 2 | 0 | 0 | **50%** |
| **Total** | **18** | **3** | **6** | **7** | **2** | **37,5%** |

> ¹ Conformidade parcial conta como 0,5. Itens Não Verificáveis excluídos do denominador.
> ⚠️ **Para conformidade plena com WCAG 2.2 AA (exigida pela NBR 17225:2025), é necessário 100% nos critérios de Nível A e AA.** O site está significativamente abaixo desse limiar.

---

## Legenda de Status

| Badge | Significado |
|---|---|
| ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) | Critério atendido integralmente |
| ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) | Atendido em parte — necessita correção |
| ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) | Critério não atendido |
| ![Não Verificável](https://img.shields.io/badge/status-N%C3%A3o%20Verific%C3%A1vel-lightgrey) | Não foi possível verificar sem execução real do fluxo |

---

## Seção A — Percepção Visual e Auditiva

---

### Item 1 — Texto Alternativo para Imagens

**Referência:** NBR 17225 (5.2.1, 5.2.3, 5.2.4) | WCAG 2.2 — C.S. 1.1.1 (Nível A)

**Status:** ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red)

**Evidência:**

```bash
grep -oiE 'alt=""' sabin_home.html | wc -l
# resultado: 92

grep -oiE '<img[^>]*>' sabin_home.html | wc -l
# resultado: 112
```

Das 112 imagens da homepage, **92 possuem `alt=""`** (vazio). O atributo vazio é correto para imagens puramente decorativas, mas foi identificado que imagens informativas também estão com `alt` vazio:

| Contexto da imagem | `alt` encontrado | Classificação correta |
|---|---|---|
| `Sabin` (logo principal) | `alt="Sabin"` | Informativa — ok |
| Selos de certificação (ISO 9001, ISO 14001, CAP, PADI) | `alt=""` | Informativa — **incorreto** |
| Fotos de unidades | `alt=""` | Informativa — **incorreto** |
| Ícones de redes sociais | `alt=""` | Decorativos — ok |
| Imagens de produtos (vacinas, check-ups) | `alt=""` | Informativas — **incorreto** |

**Impacto:** Usuários de leitores de tela (NVDA, JAWS, VoiceOver) não recebem informação sobre certificações ISO, PADI e CAP — elementos que constroem a credibilidade institucional — nem sobre os produtos vendidos na loja virtual.

**Recomendação:** Auditar as 92 imagens com `alt=""`, mantendo o vazio apenas para decorativas e adicionando descrição nas informativas. Exemplo: `alt="Certificação ISO 9001 — Sistema de Gestão da Qualidade"`.

---

### Item 2 — Contraste Mínimo de Cores

**Referência:** NBR 17225 (5.11.3, 5.11.4) | WCAG 2.2 — C.S. 1.4.3 e 1.4.11 (Nível AA)

**Status:** ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red)

**Evidência:**

```css
/* Extraído do CSS inline do HTML */
color: #999;          /* textos de apoio, labels, subtítulos */
background-color: #fff;
```

| Combinação | Razão de contraste | Mínimo WCAG AA | Resultado |
|---|---|---|---|
| `#999` sobre `#fff` | ~2,85:1 | 4,5:1 (texto normal) | **Reprovado** |
| `#6f6e67` sobre `#fff` | ~4,02:1 | 4,5:1 | **Reprovado** |
| `#312e2a` sobre `#fff` | ~12,1:1 | 4,5:1 | Aprovado |
| `#222` sobre `#fff` | ~16,1:1 | 4,5:1 | Aprovado |

A cor `#999` é utilizada em subtítulos secundários, textos de placeholder e rótulos de formulário — elementos que usuários com baixa acuidade visual dependem para orientação.

**Recomendação:** Substituir `color: #999` por `color: #767676` (mínimo para 4,5:1 sobre branco) e `#6f6e67` por `#595855` ou mais escuro em todos os textos de apoio.

---

### Item 3 — Uso Restrito da Cor

**Referência:** NBR 17225 (5.11.1) | WCAG 2.2 — C.S. 1.4.1 (Nível A)

**Status:** ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen)

**Evidência:** Campos obrigatórios do formulário de newsletter marcados com `*` em texto, não apenas com cor. Botões de estado (ativo/inativo) diferenciados por texto e posição além da cor. Não foi encontrado nenhum caso em que a cor seja o único meio de transmitir informação crítica.

---

### Item 4 — Controle de Áudio e Mídia

**Referência:** NBR 17225 (5.14.7, 5.14.8) | WCAG 2.2 — C.S. 1.4.2 (Nível A) e 2.2.2 (Nível A)

**Status:** ![Parcial](https://img.shields.io/badge/status-Parcial-yellow)

**Evidência:**

```html
<!-- Extraído do HTML bruto -->
data-autoplay-enabled="true"
autoplay-delay="6"
```

Nenhum elemento `<audio>` ou `<video>` com `autoplay` foi encontrado — critério 1.4.2 **atendido**.

Porém, o carrossel principal da homepage roda automaticamente com intervalo de 6 segundos (`autoplay-delay="6"`) e **não foram encontrados controles de pausa** (`pause`, `stop`, `play`) com `aria-label` acessível:

```bash
grep -oiE '(pause|play|stop)[^"<]*aria' sabin_home.html
# sem resultados
```

Conteúdo que avança automaticamente por mais de 3 segundos viola o C.S. 2.2.2 (Pausar, Parar, Ocultar — Nível A) quando não há mecanismo de controle acessível.

**Recomendação:** Adicionar botão de pausa ao carrossel com `aria-label="Pausar apresentação de slides"` e garantir que o carrossel pare quando o foco do teclado entrar nele.

---

### Item 5 — Design Responsivo e Refluxo (Reflow)

**Referência:** NBR 17225 (5.10.4) | WCAG 2.2 — C.S. 1.4.10 (Nível AA)

**Status:** ![Parcial](https://img.shields.io/badge/status-Parcial-yellow)

**Evidência:**
- Viewport configurado corretamente: `<meta name="viewport" content="width=device-width, initial-scale=1.0">` — sem `user-scalable=no` (positivo).
- Fontes definidas em `px` em elementos críticos, em vez de `rem`/`em`, o que pode causar quebra de layout ao aumentar o zoom do navegador para 200%.
- Carrosséis com scroll horizontal fixo podem apresentar perda de conteúdo em viewport de 320px CSS (critério de refluxo do WCAG 2.2).
- A restrição de conteúdo à orientação portrait em carrosséis móveis afeta usuários que fixam o dispositivo em landscape por limitação motora.

**Recomendação:** Substituir unidades `px` de fonte por `rem`; testar refluxo a 320px e garantir que nenhum conteúdo exija scroll horizontal nessa largura.

---

## Seção B — Operabilidade e Navegação

---

### Item 6 — Foco Visível e Não Obscurecido

**Referência:** NBR 17225 (5.1.1, 5.1.3) | WCAG 2.2 — C.S. 2.4.7 e 2.4.11 (Nível AA)

**Status:** ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red)

**Evidência:**

```bash
grep -oiE 'focus-visible' sabin_home.html | wc -l
# resultado: 0

grep -oiE ':focus' sabin_home.html | wc -l
# resultado: 45
```

O CSS contém 45 referências a `:focus`, mas **nenhuma a `:focus-visible`**. O pseudo-seletor `:focus-visible` é o padrão moderno para indicadores de foco que aparecem apenas na navegação por teclado (sem interferir no uso de mouse). A ausência de `:focus-visible` combinada com estilos que podem suprimir o outline padrão do navegador torna o foco invisível em:
- Botões dos carrosséis de produtos
- Cards de check-ups e vacinas
- Links do rodapé extenso

**Recomendação:** Implementar regra global:
```css
:focus-visible {
  outline: 3px solid #c8102e;
  outline-offset: 2px;
}
```

---

### Item 7 — Atalhos de Teclado (Skip Links)

**Referência:** NBR 17225 (5.7.12) | WCAG 2.2 — C.S. 2.4.1 (Nível A)

**Status:** ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red)

**Evidência:**

```bash
grep -iE 'skip|pular para|ir para conteúdo|ir ao conteúdo' sabin_home.html
# sem resultados
```

Nenhum skip link encontrado em nenhuma página do site. O menu de navegação principal possui múltiplos submenus — usuários de teclado e leitores de tela precisam tabular por todos eles antes de atingir o conteúdo principal em cada carregamento de página.

**Recomendação:** Inserir como primeiro elemento do `<body>`:
```html
<a href="#main-content" class="skip-link">Pular para o conteúdo principal</a>
```
Com CSS que o oculta visualmente mas torna visível ao receber foco (técnica `sr-only` com `focus:not-sr-only`).

---

### Item 8 — Tamanho do Alvo de Clique

**Referência:** NBR 17225 (5.8.7) | WCAG 2.2 — C.S. 2.5.8 (Nível AA)

**Status:** ![Parcial](https://img.shields.io/badge/status-Parcial-yellow)

**Evidência:**

```bash
grep -oiE 'btn--[a-z0-9_-]+' sabin_home.html | sort | uniq -c
# 6 btn--lg  (large — provavelmente ≥ 44px)
# 4 btn--secondary
# 2 btn--primary
# 1 btn--prev / btn--next  (navegação de carrossel)
```

Botões principais (`btn--lg`) provavelmente atendem ao mínimo de 24px × 24px exigido pelo WCAG 2.2. Porém, os botões de navegação anterior/próximo do carrossel (`btn--prev`, `btn--next`) são tipicamente ícones pequenos que podem não atingir o mínimo sem renderização confirmada. Verificação completa requer inspeção no DevTools com renderização ativa.

**Recomendação:** Garantir que todos os elementos interativos — especialmente ícones de carrossel, botões de redes sociais e ícones de compartilhamento de unidade — possuam área de toque mínima de 24×24px com espaçamento adjacente adequado. Recomendado: 44×44px (Nível AAA).

---

### Item 9 — Movimentos de Arrastar (Drag-and-Drop)

**Referência:** NBR 17225 (5.8.13) | WCAG 2.2 — C.S. 2.5.7 (Nível AA)

**Status:** ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen)

**Evidência:** O atributo `draggable` foi encontrado no HTML, mas apenas associado ao componente interno do carrossel (swipe em mobile), não a nenhuma funcionalidade de arrastar e soltar exposta ao usuário. O site não possui funcionalidades de drag-and-drop — critério não aplicável. Nenhuma violação identificada.

---

### Item 10 — Temporização Ajustável

**Referência:** NBR 17225 (5.16.2) | WCAG 2.2 — C.S. 2.2.1 (Nível A)

**Status:** ![Não Verificável](https://img.shields.io/badge/status-N%C3%A3o%20Verific%C3%A1vel-lightgrey)

**Evidência:** Referências a `Timeout` foram encontradas no JavaScript da homepage, mas estão associadas a requisições de rede (XHR/fetch), não a limites de sessão do usuário. O portal de resultados de exames (`laudos.sabin.com.br`) provavelmente possui limite de sessão (logout automático), mas não foi possível verificar a existência de mecanismo de aviso e extensão sem autenticação real.

**Recomendação:** Verificar, com acesso autenticado ao portal de laudos, se a sessão expira com aviso antecipado e opção de extensão (ex.: modal "Sua sessão expira em 5 minutos — deseja continuar?").

---

## Seção C — Compreensibilidade e Ajuda

---

### Item 11 — Títulos de Página e Semântica de Cabeçalhos

**Referência:** NBR 17225 (5.13.1, 5.3.1, 5.3.5) | WCAG 2.2 — C.S. 2.4.2 (A), 1.3.1 (A), 2.4.6 (AA)

**Status:** ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red)

**Evidência:**

```bash
grep -oiE '<h1[^>]*>' sabin_home.html
# sem resultados — nenhum <h1> encontrado

grep -oiE '<h2[^>]*>[^<]+<' sabin_home.html | head -3
# <h2 ...>Sabin Diagnóstico e Saúde</h2>   ← primeiro heading do documento
# <h2 ...>Facilidades mais buscadas:</h2>
```

A homepage **não possui `<h1>`**. A hierarquia de títulos inicia diretamente em `<h2>`, violando:
- WCAG 1.3.1: a estrutura semântica do documento não está determinada programaticamente.
- WCAG 2.4.6: títulos não descrevem adequadamente as seções.

Para leitores de tela que navegam por headings (tecla `H` no NVDA/JAWS), não há ponto de entrada principal no documento.

**Recomendação:** Adicionar `<h1>` visível ou `visually-hidden` na homepage. Auditar todas as páginas internas para garantir hierarquia correta (H1 → H2 → H3, sem saltos).

---

### Item 12 — Consistência na Interface e Ajuda Consistente

**Referência:** NBR 17225 (5.7.15, 5.7.16, 5.8.5) | WCAG 2.2 — C.S. 3.2.3, 3.2.4 (AA) e 3.2.6 (A)

**Status:** ![Parcial](https://img.shields.io/badge/status-Parcial-yellow)

**Evidência:**

**Positivo:** Menu de navegação principal mantém ordem e posição consistentes em todas as páginas visitadas. Botões de contato (WhatsApp, telefone) aparecem no mesmo local em todas as rotas analisadas.

**Problema:** A ação de agendamento é referenciada com terminologia inconsistente em diferentes pontos do site:

| Local | Rótulo usado |
|---|---|
| Banner hero da homepage | `Agendamentos #VemSabin` |
| Card de unidade | `Solicitar atendimento` |
| Menu de navegação | `Serviços Digitais` |
| Rodapé | `Atendimento Domiciliar` |

Isso viola WCAG 3.2.4 (Identificação Consistente): componentes com a mesma função devem ter a mesma identificação.

**Recomendação:** Padronizar para `Agendar exame` em todos os pontos de chamada para o fluxo de agendamento.

---

### Item 13 — Identificação Programática do Idioma

**Referência:** NBR 17225 (5.13.2, 5.13.3) | WCAG 2.2 — C.S. 3.1.1 (A) e 3.1.2 (AA)

**Status:** ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen)

**Evidência:**
```html
<html lang="pt-BR">
```
Idioma principal declarado corretamente. Nenhum trecho em idioma estrangeiro sem marcação `lang` alternado foi identificado no conteúdo analisado.

---

### Item 14 — Identificação, Sugestão e Prevenção de Erros

**Referência:** NBR 17225 (5.9.9, 5.9.10, 5.9.12) | WCAG 2.2 — C.S. 3.3.1 (A), 3.3.3 e 3.3.4 (AA)

**Status:** ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red)

**Evidência:**

O portal de resultados de exames (`laudos.sabin.com.br`) — ponto crítico de interação — apresenta:
- Campos sem `<label>` associado: apenas texto placeholder `"Informe seu usuário"` / `"Informe sua senha"`, sem identificação programática.
- Nenhuma indicação do formato esperado (CPF? e-mail? número de cadastro?).
- Nenhuma mensagem de erro visível descrita na análise — não é possível confirmar se os erros de login são identificados em texto ou apenas por cor.
- Ausência de link "Primeiro acesso" ou orientação para novos usuários.

Adicionalmente, a string de desenvolvedor `Feedback titlte` (typo) vaza no DOM da homepage:
```html
<h2 ...>Feedback titlte</h2>
```
Este `<h2>` aparece como ponto de navegação por heading para leitores de tela, com conteúdo sem sentido.

**Recomendação:** No portal de laudos: adicionar `<label for="...">CPF</label>` explícito, placeholder com formato (`000.000.000-00`), mensagem de erro em texto próxima ao campo problemático e link "Primeiro acesso". Corrigir typo no DOM da homepage.

---

### Item 15 — Prevenção de Entradas Redundantes

**Referência:** NBR 17225 (5.9.15) | WCAG 2.2 — C.S. 3.3.7 (Nível A)

**Status:** ![Não Verificável](https://img.shields.io/badge/status-N%C3%A3o%20Verific%C3%A1vel-lightgrey)

**Evidência:** O fluxo de agendamento — contexto principal onde entradas redundantes seriam verificadas (ex.: CPF solicitado na etapa 1 e novamente na etapa 3) — retorna erro 404, impossibilitando a avaliação. O formulário de newsletter é de etapa única, não aplicável a este critério.

**Recomendação:** Assim que o fluxo de agendamento for restaurado, verificar se dados já informados (CPF, data de nascimento) são reutilizados automaticamente nas etapas subsequentes.

---

### Item 16 — Autenticação Acessível (Sem Testes Cognitivos)

**Referência:** NBR 17225 (5.9.18) | WCAG 2.2 — C.S. 3.3.8 (Nível AA)

**Status:** ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red)

**Evidência:**

O critério 3.3.8 exige que processos de autenticação não dependam de memorização — e que, quando há campo de senha, **cópia/colagem e preenchimento automático (`autocomplete`) sejam suportados**.

```html
<!-- formulário de busca da homepage -->
autocomplete="off"
```

O padrão de `autocomplete="off"` observado no site indica tendência de desabilitar preenchimento automático. No portal de laudos, o campo de senha deveria ter `autocomplete="current-password"` para permitir que gerenciadores de senha preencham automaticamente. Sem isso, o usuário é forçado a memorizar e digitar manualmente — teste cognitivo implícito.

**Recomendação:** No portal de laudos, configurar:
```html
<input type="text"     autocomplete="username"         ...>
<input type="password" autocomplete="current-password" ...>
```

---

## Seção D — Robustez e Código Semântico

---

### Item 17 — Nome, Função e Valor em Componentes Web

**Referência:** NBR 17225 (5.13.12, 5.13.13) | WCAG 2.2 — C.S. 4.1.2 (Nível A)

**Status:** ![Parcial](https://img.shields.io/badge/status-Parcial-yellow)

**Evidência:**

**Positivo — homepage:**
```html
<!-- botões de menu com estado correto -->
<button aria-controls="cmp-header-submenu-exames"
        aria-expanded="false"
        class="cmp-header-institucional__menu-toggle">

<!-- botões de ação com nome acessível -->
<button aria-label="Selecionar localidade atual" ...>
<button aria-label="Abrir busca" ...>
<button aria-label="Fechar" ...>
```

103 ocorrências de `aria-label` na homepage indicam esforço de acessibilidade semântica.

**Problema — portal de laudos:**
Os campos de formulário do portal de resultados (`laudos.sabin.com.br`) utilizam apenas texto de placeholder como instrução, sem `<label>`, `aria-label` ou `aria-labelledby`. Placeholders desaparecem ao digitar, removendo a instrução do usuário no momento de maior atenção cognitiva.

**Recomendação:** Associar `<label>` explícito a cada campo do portal de laudos; garantir que placeholders sejam complementares ao label, nunca substitutos.

---

### Item 18 — Linguagem Simples (Plain Language)

**Referência:** NBR 17225 (5.12.11, 5.12.12) | WCAG 2.2 — C.S. 3.1.4 e 3.1.5 (Nível AAA)

**Status:** ![Parcial](https://img.shields.io/badge/status-Parcial-yellow)

**Evidência:**

```bash
grep -oiE '\b(TSH|HbA1c|PCR|PSA|HCG|HPV|VDRL|Anti-HIV)\b' sabin_home.html | sort | uniq -c
# 2 HPV
# 2 HCG
# 3 hpv / 1 hcg (variações de caso)
```

Siglas médicas aparecem sem expansão no conteúdo principal:
- `HPV` listado como produto na loja virtual sem expandir "Vírus do Papiloma Humano".
- `HCG` (Beta HCG) referenciado sem definição.
- `Sabin Genômica` utilizado como categoria sem explicação do que é genômica ou o que inclui.

**Positivo:** Linguagem geral do site é acessível, com termos como "Preparo de exames", "Exames de Sangue" e "Resultado de exames" bem escolhidos para o público leigo.

**Recomendação:** Expandir siglas médicas na primeira ocorrência de cada página: `HPV (Vírus do Papiloma Humano)`, `HCG (Gonadotrofina Coriônica Humana)`. Adicionar descrição resumida às categorias especializadas como "Sabin Genômica".

---

## Tabela Resumo — Todos os 18 Itens

| ID | Item | Seção | WCAG 2.2 | Status |
|---|---|---|---|---|
| 1 | Texto Alternativo para Imagens | A | 1.1.1 (A) | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) |
| 2 | Contraste Mínimo de Cores | A | 1.4.3 / 1.4.11 (AA) | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) |
| 3 | Uso Restrito da Cor | A | 1.4.1 (A) | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) |
| 4 | Controle de Áudio e Mídia | A | 1.4.2 (A) / 2.2.2 (A) | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) |
| 5 | Design Responsivo e Refluxo | A | 1.4.10 (AA) | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) |
| 6 | Foco Visível e Não Obscurecido | B | 2.4.7 / 2.4.11 (AA) | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) |
| 7 | Atalhos de Teclado (Skip Links) | B | 2.4.1 (A) | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) |
| 8 | Tamanho do Alvo de Clique | B | 2.5.8 (AA) | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) |
| 9 | Movimentos de Arrastar | B | 2.5.7 (AA) | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) |
| 10 | Temporização Ajustável | B | 2.2.1 (A) | ![Não Verificável](https://img.shields.io/badge/status-N%C3%A3o%20Verific%C3%A1vel-lightgrey) |
| 11 | Títulos e Semântica de Cabeçalhos | C | 2.4.2 (A) / 1.3.1 (A) | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) |
| 12 | Consistência e Ajuda Consistente | C | 3.2.3 / 3.2.4 / 3.2.6 | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) |
| 13 | Identificação do Idioma | C | 3.1.1 (A) / 3.1.2 (AA) | ![Conforme](https://img.shields.io/badge/status-Conforme-brightgreen) |
| 14 | Identificação e Prevenção de Erros | C | 3.3.1 (A) / 3.3.3 / 3.3.4 (AA) | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) |
| 15 | Prevenção de Entradas Redundantes | C | 3.3.7 (A) | ![Não Verificável](https://img.shields.io/badge/status-N%C3%A3o%20Verific%C3%A1vel-lightgrey) |
| 16 | Autenticação Acessível | C | 3.3.8 (AA) | ![Não Conforme](https://img.shields.io/badge/status-N%C3%A3o%20Conforme-red) |
| 17 | Nome, Função e Valor (Componentes) | D | 4.1.2 (A) | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) |
| 18 | Linguagem Simples | D | 3.1.4 / 3.1.5 (AAA) | ![Parcial](https://img.shields.io/badge/status-Parcial-yellow) |

---

## Recomendações Prioritárias

| Prioridade | ID | Critério | Ação |
|---|---|---|---|
| ![Prioridade Imediata](https://img.shields.io/badge/prioridade-Imediata-red) | 7 | WCAG 2.4.1 | Implementar skip link `<a href="#main-content">Pular para o conteúdo</a>` como primeiro elemento do `<body>` |
| ![Prioridade Imediata](https://img.shields.io/badge/prioridade-Imediata-red) | 11 | WCAG 1.3.1 | Adicionar `<h1>` na homepage; auditar hierarquia de headings em todas as páginas internas |
| ![Prioridade Imediata](https://img.shields.io/badge/prioridade-Imediata-red) | 1 | WCAG 1.1.1 | Auditar as 92 imagens com `alt=""`: manter vazio em decorativas, adicionar descrição nas informativas |
| ![Prioridade Alta](https://img.shields.io/badge/prioridade-Alta-orange) | 2 | WCAG 1.4.3 | Substituir `color: #999` → `#767676` e `#6f6e67` → `#595855` em textos de apoio |
| ![Prioridade Alta](https://img.shields.io/badge/prioridade-Alta-orange) | 6 | WCAG 2.4.7 | Implementar `:focus-visible` com outline de 3px e cor de alto contraste |
| ![Prioridade Alta](https://img.shields.io/badge/prioridade-Alta-orange) | 14 | WCAG 3.3.1 | Adicionar `<label>` explícito e mensagens de erro descritivas no portal de laudos |
| ![Prioridade Alta](https://img.shields.io/badge/prioridade-Alta-orange) | 16 | WCAG 3.3.8 | Configurar `autocomplete="username"` e `autocomplete="current-password"` no portal de laudos |
| ![Prioridade Média](https://img.shields.io/badge/prioridade-M%C3%A9dia-yellowgreen) | 4 | WCAG 2.2.2 | Adicionar botão de pausa ao carrossel da homepage |
| ![Prioridade Média](https://img.shields.io/badge/prioridade-M%C3%A9dia-yellowgreen) | 12 | WCAG 3.2.4 | Padronizar terminologia de agendamento para `Agendar exame` em todos os pontos do site |
| ![Prioridade Média](https://img.shields.io/badge/prioridade-M%C3%A9dia-yellowgreen) | 18 | WCAG 3.1.4 | Expandir siglas médicas (HPV, HCG) na primeira ocorrência de cada página |

---

## Referências

> GRUPO 07 IHC 2026.1. *Checklist de Acessibilidade Digital — PocketV2*. Disponível em: `docs/pocket-v2/checklistAcessibilidade/checklist_acessibilidade_digital.md`.

> W3C. *Web Content Accessibility Guidelines (WCAG) 2.2*. 2023. Disponível em: [https://www.w3.org/TR/WCAG22/](https://www.w3.org/TR/WCAG22/).

> ABNT. *NBR 17225:2025 — Acessibilidade Digital*. Associação Brasileira de Normas Técnicas, 2025.

> BRASIL. *e-MAG — Modelo de Acessibilidade em Governo Eletrônico*, versão 3.1. 2014.

> DINIZ, V. et al. *Guia de Boas Práticas para Acessibilidade Digital*. Programa de Cooperação Reino Unido–Brasil, 2023.
