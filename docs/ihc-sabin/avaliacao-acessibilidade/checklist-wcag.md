# Checklist WCAG

> Versão resumida do [Relato dos Resultados](resultados.md), aplicando os 18 itens do [Checklist de Acessibilidade Digital — Guia PocketV2](../../pocket-v2/checklistAcessibilidade/checklist_acessibilidade_digital.md). Para evidências completas (grep, HTML, screenshots) de cada item, ver o relato detalhado.

## Critérios Avaliados

| ID | Critério                                      | Status         | Justificativa                                                                                                                                                         | Evidência                               |
| -- | --------------------------------------------- | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| 1  | Texto Alternativo para Imagens                | ❌ Não Conforme | Das 112 imagens da homepage, 92 têm `alt=""`; selos de certificação, fotos de unidade e imagens de produtos informativos estão incorretamente marcados como decorativos. | resultados.md                    |
| 2  | Contraste Mínimo de Cores                     | ❌ Não Conforme | `#999` (~2,85:1) e `#6f6e67` (~4,02:1) sobre fundo branco ficam abaixo do mínimo AA de 4,5:1 em textos de apoio e rótulos.                                            | resultados.md                    |
| 3  | Uso Restrito da Cor                           | ✅ Conforme     | Campos obrigatórios e estados de botão diferenciados por texto/posição, além da cor; nenhum caso de cor como único meio de informação.                                | resultados.md                    |
| 4  | Controle de Áudio e Mídia                     | ⚠️ Parcial     | Sem autoplay de áudio/vídeo, mas o carrossel da homepage avança automaticamente a cada 6s sem botão de pausa acessível (viola C.S. 2.2.2).                            | resultados.md                    |
| 5  | Design Responsivo e Refluxo                   | ⚠️ Parcial     | Viewport configurado corretamente, porém fontes em `px` (não `rem`) e carrosséis com scroll fixo podem perder conteúdo a 320px CSS.                                   | resultados.md                    |
| 6  | Foco Visível e Não Obscurecido                | ❌ Não Conforme | 45 ocorrências de `:focus` no CSS, porém nenhuma de `:focus-visible` — foco pode ficar invisível em botões de carrossel e cards.                                       | resultados.md                    |
| 7  | Atalhos de Teclado (Skip Links)                | ❌ Não Conforme | Nenhum skip link encontrado em nenhuma página avaliada do site.                                                                                                       | resultados.md                    |
| 8  | Tamanho do Alvo de Clique                     | ⚠️ Parcial     | Botões principais (`btn--lg`) atendem ao mínimo, mas ícones de navegação do carrossel (`btn--prev`/`btn--next`) podem não atingir 24×24px.                            | best-LightHouse.png, resultados.md |
| 9  | Movimentos de Arrastar (Drag-and-Drop)        | ✅ Conforme     | `draggable` presente apenas no swipe interno do carrossel; nenhuma funcionalidade de arrastar-e-soltar exposta ao usuário.                                            | resultados.md                    |
| 10 | Temporização Ajustável                        | ⚪ Não Verificável | Não foi possível confirmar, sem acesso autenticado, se o portal de laudos avisa e permite estender a sessão antes do logout automático.                            | resultados.md                   |
| 11 | Títulos de Página e Semântica de Cabeçalhos   | ❌ Não Conforme | A homepage não possui `<h1>`; a hierarquia de títulos inicia em `<h2>`.                                                                                               | alertas-Wave.png, resultados.md |
| 12 | Consistência na Interface e Ajuda Consistente | ⚠️ Parcial     | Navegação principal consistente entre páginas, mas o agendamento é nomeado de 4 formas diferentes ("Agendamentos", "Solicitar atendimento", "Serviços Digitais"...). | resultados.md                   |
| 13 | Identificação Programática do Idioma          | ✅ Conforme     | `<html lang="pt-BR">` declarado corretamente; nenhum trecho em idioma estrangeiro sem marcação alternada.                                                             | resultados.md                   |
| 14 | Identificação, Sugestão e Prevenção de Erros  | ❌ Não Conforme | Campos do portal de laudos sem `<label>` associado, sem indicação de formato esperado e sem link "Primeiro acesso".                                                   | resultados.md                   |
| 15 | Prevenção de Entradas Redundantes             | ⚪ Não Verificável | O fluxo de agendamento — onde o critério se aplicaria — retorna erro 404, impossibilitando a avaliação.                                                            | resultados.md                   |
| 16 | Autenticação Acessível                        | ❌ Não Conforme | Padrão de `autocomplete="off"` no site; campo de senha do portal de laudos deveria usar `autocomplete="current-password"`.                                            | resultados.md                   |
| 17 | Nome, Função e Valor em Componentes Web       | ⚠️ Parcial     | Homepage usa `aria-label`/`aria-expanded` corretamente (103 ocorrências), mas o portal de laudos depende só de placeholder, sem `<label>`.                            | erros-Wave.png, links-Lighthouse.png    |
| 18 | Linguagem Simples                             | ⚠️ Parcial     | Linguagem geral clara, mas siglas médicas (HPV, HCG) e categorias como "Sabin Genômica" aparecem sem expansão/explicação.                                            | resultados.md                   |

## Resumo dos Resultados

| Situação           | Quantidade |
| ------------------ | ---------- |
| ✅ Conforme         | 3          |
| ⚠️ Parcial         | 6          |
| ❌ Não Conforme     | 7          |
| ⚪ Não Verificável  | 2          |

## Principais Não Conformidades

* Imagens com links sem texto alternativo (item 1).
* Problemas de contraste entre texto e fundo (item 2).
* Ausência de indicador de foco visível (`:focus-visible`) (item 6).
* Ausência de skip links para o conteúdo principal (item 7).
* Estrutura inadequada de cabeçalhos — homepage sem `<h1>` (item 11).
* Formulários do portal de laudos sem `<label>` nem mensagens de erro descritivas (item 14).
* Autenticação sem suporte a `autocomplete` de senha (item 16).

## Conclusão

A avaliação realizada indica que o site do Sabin tem boa pontuação em ferramentas automatizadas (93/100 no Lighthouse), mas isso **não se traduz em conformidade real com a WCAG 2.2/NBR 17225:2025**: dos 18 itens do checklist PocketV2, apenas 3 estão plenamente conformes, 7 são não conformes e 6 são parciais. Ferramentas automatizadas cobrem só uma fração dos critérios — boa parte das não conformidades (foco visível, skip links, labels de formulário) só aparece na inspeção manual do código, reforçando a nota metodológica do [Guia PocketV2](../../pocket-v2/tools/ferramentas.md) de que automação cobre apenas 30–40% do WCAG 2.2.

Esses problemas podem impactar diretamente usuários que dependem de leitores de tela, navegação por teclado ou possuem limitações visuais e motoras. Recomenda-se a correção das não conformidades identificadas para aumentar a inclusão digital e a aderência às diretrizes WCAG 2.2, NBR 17225:2025 e e-MAG.

## Referências

* W3C. Web Content Accessibility Guidelines (WCAG) 2.2.
* ABNT. NBR 17225:2025 – Acessibilidade em Conteúdo e Aplicações Web.
* Brasil. e-MAG – Modelo de Acessibilidade em Governo Eletrônico.
* Google Lighthouse.
* WAVE – Web Accessibility Evaluation Tool.
