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
| 8  | Tamanho do Alvo de Clique                     | ❌ Não Conforme | O Lighthouse identificou elementos interativos com área de toque insuficiente para interação confortável em dispositivos móveis (botões de carrossel e ícones do rodapé abaixo de 24×24px). | best-LightHouse.png, resultados.md |
| 9  | Movimentos de Arrastar (Drag-and-Drop)        | ✅ Conforme     | `draggable` presente apenas no swipe interno do carrossel; nenhuma funcionalidade de arrastar-e-soltar exposta ao usuário.                                            | resultados.md                    |
| 10 | Temporização Ajustável                        | ⚪ Não Verificável | Não foi possível confirmar, sem acesso autenticado, se o portal de laudos avisa e permite estender a sessão antes do logout automático.                            | resultados.md                   |
| 11 | Títulos de Página e Semântica de Cabeçalhos   | ❌ Não Conforme | A homepage não possui `<h1>`; a hierarquia de títulos inicia em `<h2>`.                                                                                               | alertas-Wave.png, resultados.md |
| 12 | Consistência na Interface e Ajuda Consistente | ⚠️ Parcial     | Navegação principal consistente entre páginas, mas o agendamento é nomeado de 4 formas diferentes ("Agendamentos", "Solicitar atendimento", "Serviços Digitais"...). | resultados.md                   |
| 13 | Identificação Programática do Idioma          | ✅ Conforme     | `<html lang="pt-BR">` declarado corretamente; nenhum trecho em idioma estrangeiro sem marcação alternada.                                                             | resultados.md                   |
| 14 | Identificação, Sugestão e Prevenção de Erros  | ❌ Não Conforme | Campos do portal de laudos sem `<label>` associado, sem indicação de formato esperado e sem link "Primeiro acesso".                                                   | resultados.md                   |
| 15 | Prevenção de Entradas Redundantes             | ⚪ Não Verificável | O fluxo de agendamento — onde o critério se aplicaria — retorna erro 404, impossibilitando a avaliação.                                                            | resultados.md                   |
| 16 | Autenticação Acessível                        | ❌ Não Conforme | Padrão de `autocomplete="off"` no site; campo de senha do portal de laudos deveria usar `autocomplete="current-password"`.                                            | resultados.md                   |
| 17 | Nome, Função e Valor em Componentes Web       | ❌ Não Conforme | Foram encontradas 5 referências ARIA inválidas (WAVE) e links sem nome acessível discernível (Lighthouse). Portal de laudos sem `<label>` em campos de formulário.    | erros-Wave.png, links-Lighthouse.png    |
| 18 | Linguagem Simples                             | ⚠️ Parcial     | Linguagem geral clara, mas siglas médicas (HPV, HCG) e categorias como "Sabin Genômica" aparecem sem expansão/explicação.                                            | resultados.md                   |

## Resumo dos Resultados

| Situação           | Quantidade |
| ------------------ | ---------- |
| ✅ Conforme         | 3          |
| ⚠️ Parcial         | 4          |
| ❌ Não Conforme     | 9          |
| ⚪ Não Verificável  | 2          |

## Principais Não Conformidades

* Imagens com texto alternativo incorreto ou ausente (item 1) — 92 de 112 imagens com `alt=""` indevido.
* Problemas de contraste entre texto e fundo (item 2) — `#999` sobre branco abaixo do mínimo AA.
* Ausência de indicador de foco visível (`:focus-visible`) (item 6) — invisível na navegação por teclado.
* Ausência de skip links para o conteúdo principal (item 7) — todos os usuários de teclado afetados.
* Tamanho de alvo de clique insuficiente confirmado pelo Lighthouse (item 8) — botões de carrossel e ícones abaixo de 24×24px.
* Estrutura inadequada de cabeçalhos — homepage sem `<h1>` (item 11).
* Formulários do portal de laudos sem `<label>` nem mensagens de erro descritivas (item 14).
* Autenticação sem suporte a `autocomplete` de senha (item 16).
* Referências ARIA inválidas e links sem nome acessível confirmados pelo WAVE e Lighthouse (item 17).

## Conclusão

A avaliação realizada indica que o site do Sabin tem boa pontuação em ferramentas automatizadas (93/100 no Lighthouse), mas isso **não se traduz em conformidade real com a WCAG 2.2/NBR 17225:2025**: dos 18 itens do checklist PocketV2, apenas 3 estão plenamente conformes, **9 são não conformes** e 4 são parciais — resultando em apenas **31,25% de conformidade** (muito abaixo dos 100% exigidos pela NBR 17225:2025 para os níveis A e AA). Notavelmente, as ferramentas automatizadas (Lighthouse e WAVE) confirmaram diretamente violações nos itens 8 (tamanho de alvo de clique) e 17 (ARIA inválido e links sem nome), reforçando que mesmo ferramentas automatizadas, quando usadas corretamente, revelam falhas críticas. A inspeção manual identificou ainda violações adicionais (foco visível, skip links, labels de formulário) que ferramentas automáticas não capturam — evidência do que o [Guia PocketV2](../../pocket-v2/tools/ferramentas.md) aponta: automação cobre apenas 30–40% do WCAG 2.2.

Esses problemas podem impactar diretamente usuários que dependem de leitores de tela, navegação por teclado ou possuem limitações visuais e motoras. Recomenda-se a correção das não conformidades identificadas para aumentar a inclusão digital e a aderência às diretrizes WCAG 2.2, NBR 17225:2025 e e-MAG.

## Referências

* W3C. Web Content Accessibility Guidelines (WCAG) 2.2.
* ABNT. NBR 17225:2025 – Acessibilidade em Conteúdo e Aplicações Web.
* Brasil. e-MAG – Modelo de Acessibilidade em Governo Eletrônico.
* Google Lighthouse.
* WAVE – Web Accessibility Evaluation Tool.
