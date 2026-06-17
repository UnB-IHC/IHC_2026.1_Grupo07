# Checklist WCAG

## Critérios Avaliados

| ID | Critério                                      | Status         | Justificativa                                                                                                                                                         | Evidência                               |
| -- | --------------------------------------------- | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| 1  | Texto Alternativo para Imagens                | ❌ Não Conforme | Foram identificadas 4 imagens utilizadas como links sem texto alternativo adequado, comprometendo a compreensão do conteúdo por usuários de leitores de tela.         | erros-Wave.png                          |
| 2  | Contraste Mínimo de Cores                     | ❌ Não Conforme | Foram encontrados 5 elementos com contraste muito baixo entre texto e fundo, dificultando a leitura para usuários com baixa visão.                                    | contraste-Wave.png, contraste2-Wave.png |
| 3  | Uso Restrito da Cor                           | ⚠️ Parcial     | Não foram identificadas falhas automáticas, porém a verificação completa exige testes manuais para garantir que a cor não seja o único meio de transmitir informação. | Inspeção manual                         |
| 4  | Controle de Áudio e Mídia                     | ✅ Conforme     | Durante a avaliação não foram identificados conteúdos com reprodução automática de áudio que exigissem mecanismos de controle adicionais.                             | Inspeção manual                         |
| 5  | Design Responsivo e Refluxo                   | ✅ Conforme     | O site apresentou comportamento responsivo adequado em dispositivos móveis, sem perda perceptível de conteúdo ou funcionalidade.                                      | Avaliação Lighthouse                    |
| 6  | Foco Visível e Não Obscurecido                | ⚠️ Parcial     | Não foram observadas falhas críticas, porém a validação completa exige navegação integral utilizando apenas teclado.                                                  | Inspeção manual                         |
| 7  | Atalhos de Teclado (Skip Links)               | ⚠️ Parcial     | Não foi possível confirmar a presença de mecanismos para salto direto ao conteúdo principal durante a avaliação realizada.                                            | Inspeção manual                         |
| 8  | Tamanho do Alvo de Clique                     | ❌ Não Conforme | O Lighthouse identificou elementos interativos com área de toque insuficiente para interação confortável em dispositivos móveis.                                      | best-LightHouse.png                     |
| 9  | Movimentos de Arrastar (Drag-and-Drop)        | ✅ Conforme     | Não foram identificadas funcionalidades dependentes exclusivamente de movimentos de arrastar e soltar.                                                                | Inspeção manual                         |
| 10 | Temporização Ajustável                        | ✅ Conforme     | Não foram observadas restrições de tempo ou sessões com expiração durante os testes realizados.                                                                       | Inspeção manual                         |
| 11 | Títulos de Página e Semântica de Cabeçalhos   | ❌ Não Conforme | Foi identificada ausência de cabeçalho principal (H1) e salto na hierarquia dos títulos, comprometendo a estrutura semântica da página.                               | alertas-Wave.png                        |
| 12 | Consistência na Interface e Ajuda Consistente | ✅ Conforme     | A estrutura de navegação e os elementos da interface mantêm padrão consistente entre as páginas avaliadas.                                                            | Inspeção manual                         |
| 13 | Identificação Programática do Idioma          | ⚠️ Parcial     | Não foi realizada inspeção detalhada do código-fonte para confirmação completa da marcação do idioma da página.                                                       | Inspeção manual                         |
| 14 | Identificação, Sugestão e Prevenção de Erros  | ⚠️ Parcial     | A avaliação não contemplou testes aprofundados em formulários e fluxos completos de interação.                                                                        | Inspeção manual                         |
| 15 | Prevenção de Entradas Redundantes             | ⚠️ Parcial     | Não foi possível validar completamente sem executar processos completos de cadastro e agendamento.                                                                    | Inspeção manual                         |
| 16 | Autenticação Acessível                        | ⚠️ Parcial     | Os mecanismos de autenticação não foram avaliados em profundidade durante esta etapa.                                                                                 | Inspeção manual                         |
| 17 | Nome, Função e Valor em Componentes Web       | ❌ Não Conforme | Foram encontradas 5 referências ARIA inválidas e links sem nome acessível discernível para tecnologias assistivas.                                                    | erros-Wave.png, links-Lighthouse.png    |
| 18 | Linguagem Simples                             | ✅ Conforme     | O conteúdo utiliza linguagem clara, objetiva e compatível com o público-alvo do serviço.                                                                              | Inspeção manual                         |

## Resumo dos Resultados

| Situação       | Quantidade |
| -------------- | ---------- |
| ✅ Conforme     | 6          |
| ⚠️ Parcial     | 7          |
| ❌ Não Conforme | 5          |

## Principais Não Conformidades

* Imagens com links sem texto alternativo.
* Problemas de contraste entre texto e fundo.
* Tamanho insuficiente de alguns elementos clicáveis.
* Estrutura inadequada de cabeçalhos.
* Problemas em atributos ARIA e identificação de componentes.

## Conclusão

A avaliação realizada indica que o site do Sabin apresenta um nível geral satisfatório de acessibilidade, refletido pela pontuação de 93/100 obtida na ferramenta Lighthouse. Entretanto, foram identificadas não conformidades relevantes relacionadas aos critérios WCAG 1.1.1 (Conteúdo Não Textual), 1.4.3 (Contraste Mínimo), 2.5.8 (Tamanho do Alvo) e 4.1.2 (Nome, Função e Valor).

Esses problemas podem impactar diretamente usuários que dependem de leitores de tela, navegação por teclado ou possuem limitações visuais e motoras. Recomenda-se a correção das não conformidades identificadas para aumentar a inclusão digital e a aderência às diretrizes WCAG 2.2, NBR 17225:2025 e e-MAG.

## Referências

* W3C. Web Content Accessibility Guidelines (WCAG) 2.2.
* ABNT. NBR 17225:2025 – Acessibilidade em Conteúdo e Aplicações Web.
* Brasil. e-MAG – Modelo de Acessibilidade em Governo Eletrônico.
* Google Lighthouse.
* WAVE – Web Accessibility Evaluation Tool.
