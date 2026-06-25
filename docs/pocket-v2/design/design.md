# :material-palette-outline: Design

!!! info "[NOVO - TG10/Grupo07]"
    Esta seção foi atualizada para incluir critérios introduzidos pelo WCAG 2.2 e referências à ABNT NBR 17225:2025. Além disso, foram adicionadas recomendações relacionadas à tipografia, espaçamento, foco visível e componentes interativos. Itens marcados com `[NOVO WCAG 2.2]` ou `[NOVO - TG10/Grupo07]` não estavam presentes na versão V1 (VerificaAAA, 2024). Referência: TG10 – Estudo Aprofundado WCAG 2.2 (Grupo 7, 2026).

> "Existe uma lenda de que a acessibilidade torna um sítio web muito simples ou feio. Não é verdade: um sítio web bem estruturado pode ser bonito e criativo. É possível, inclusive, criar apresentações visuais diferentes para a mesma estrutura HTML de um sítio web com o uso de CSS e atender a diferentes necessidades."

Dessa forma, nesta seção encontra-se um checklist de boas práticas que auxiliam na construção de interfaces visualmente acessíveis.

## Aparência

- [ ] **Adicionar instrução** que não **dependa exclusivamente da cor**. <a id="TEC1" href="#RP1">[1]</a>
- [ ] **Adicionar informação** (como gráficos e diagramas) que não **dependa exclusivamente da cor**. <a id="TEC1" href="#RP1">[1]</a>
- [ ] **Tamanho do texto ajustável** para permitir ampliação. <a id="TEC2" href="#RP2">[2]</a>
- [ ] **Descrever os controles** pelo nome, não apenas pela aparência ou localização. <a id="TEC3" href="#RP3">[3]</a>
- [ ] **Garantir que dicas visuais** significativas atinjam 3:1 em relação ao fundo. <a id="TEC4" href="#RP4">[4]</a>
- [ ] **Fazer com que as linhas** de texto se ajustem ao viewport. <a id="TEC5" href="#RP5">[5]</a>
- [ ] Oferecer uma **opção de alto contraste** (dark mode) e aumento de fontes.
- [ ] Parágrafos com no **máximo 80 caracteres por linha**.
- [ ] **Evitar** o uso de **textos longos em caixa alta ou condensados**.
- [ ] Evitar o alinhamento justificado.
- [ ] **Fontes são fluidas** e de fácil entendimento.
- [ ] Tomar o devido cuidado com **`display:none` e `visibility:hidden` para recursos de tecnologia assistiva**.
- [ ] Preferir **botões com texto e ícone**. Botões apenas com ícones devem possuir nome acessível.

## Tipografia

!!! note "[NOVO - TG10/Grupo07]"

- [ ] Utilizar fontes com boa legibilidade em ambientes digitais.
- [ ] Evitar fontes excessivamente decorativas em conteúdos informativos.
- [ ] Utilizar tamanho base mínimo recomendado de 16px para textos principais.
- [ ] Garantir contraste adequado entre texto e plano de fundo (mínimo 4.5:1 para textos normais e 3:1 para textos grandes).
- [ ] Utilizar hierarquia visual clara entre títulos, subtítulos e corpo de texto.
- [ ] Garantir que o texto possa ser ampliado em até 200% sem perda de conteúdo ou funcionalidade.
- [ ] Evitar o uso excessivo de itálico em blocos longos de texto.
- [ ] Garantir diferenciação visual adequada entre links e texto comum (preferencialmente sublinhado ou com contraste adicional além da cor).

## Espaçamento e Organização Visual

!!! note "[NOVO - TG10/Grupo07]"

- [ ] Garantir espaçamento entre linhas de pelo menos 1,5 vezes o tamanho da fonte.
- [ ] Garantir espaçamento entre parágrafos de pelo menos 2 vezes o tamanho da fonte.
- [ ] Permitir aumento do espaçamento entre letras sem perda de conteúdo ou funcionalidade.
- [ ] Permitir aumento do espaçamento entre palavras sem quebra da interface.
- [ ] Evitar agrupamento excessivo de informações e componentes.
- [ ] Utilizar espaçamento adequado entre elementos interativos (mínimo 8px).
- [ ] Garantir que o conteúdo continue legível quando o usuário personalizar espaçamentos via navegador ou tecnologia assistiva.
- [ ] **[NOVO WCAG 2.2]** Garantir que as configurações de espaçamento não causem perda de conteúdo ou sobreposição (SC 1.4.12). <a id="TEC_D2" href="#RP_D2">[D2]</a>

## Animação

- [ ] **Evitar conteúdo que pisque**, ou mantê-lo abaixo dos limites (máximo 3 flashes por segundo). <a id="TEC6" href="#RP6">[6]</a>
- [ ] **Permitir que os usuários controlem alterações de conteúdo** que ocorram em paralelo com outro conteúdo. <a id="TEC7" href="#RP7">[7]</a>
- [ ] **Toda animação** deve obedecer à consulta de mídia `prefers-reduced-motion`. <a id="TEC8" href="#RP8">[8]</a>
- [ ] Evitar animações automáticas em conteúdos essenciais; preferir animações iniciadas por interação do usuário.

## Contraste de Cores

- [ ] **Verificar o contraste** de todo texto em tamanho normal: 4.5:1 (mínimo AA) ou 7:1 (AAA). <a id="TEC9" href="#RP9">[9]</a>
- [ ] **Verificar o contraste** de todo texto em tamanho grande (≥18pt ou ≥14pt negrito): 3:1 (mínimo AA) ou 4.5:1 (AAA). <a id="TEC9" href="#RP9">[9]</a>
- [ ] **Verificar o contraste** de todos os ícones: 3:1 em relação ao fundo. <a id="TEC4" href="#RP4">[4]</a>
- [ ] **Verificar o contraste** das bordas dos elementos de entrada: 3:1 em relação ao fundo adjacente. <a href="#RP4">[4]</a>
- [ ] **Verificar o contraste** do texto que se sobrepõe a imagens ou vídeos. <a id="TEC9" href="#RP9">[9]</a>
- [ ] **Verificar cores personalizadas de `::selection`** para garantir legibilidade. <a id="TEC9" href="#RP9">[9]</a>
- [ ] **[NOVO WCAG 2.2]** O indicador de foco deve possuir contraste mínimo de 3:1 em relação ao fundo adjacente e espessura mínima de 2px CSS. Recomenda-se `outline: 2px solid #005fcc` ou cores similares com bom contraste. Utilize `:focus-visible` para exibir o foco apenas quando necessário. <a id="TEC_D1" href="#RP_D1">[D1]</a>
- [ ] **[NOVO WCAG 2.2]** Nunca remover o `outline` padrão sem fornecer um substituto equivalente ou superior.
- [ ] **[NOVO WCAG 2.2]** Garantir que o contraste entre o indicador de foco e o fundo não seja inferior a 3:1, inclusive em diferentes estados de interface.

## Componentes Interativos

!!! note "[NOVO - TG10/Grupo07]"

- [ ] Todos os componentes interativos devem ser acessíveis por teclado.
- [ ] A ordem de navegação por teclado deve seguir a ordem lógica e visual da interface.
- [ ] Componentes devem apresentar estado de foco claramente visível.
- [ ] Elementos clicáveis devem possuir rótulos claros e compreensíveis.
- [ ] Não utilizar apenas cor para indicar estados de erro, sucesso ou seleção.
- [ ] **[NOVO WCAG 2.2]** Garantir tamanho mínimo de 24×24px para áreas clicáveis (AA) ou 44×44px para melhor usabilidade (AAA). <a id="TEC_D4" href="#RP_D4">[D4]</a>
- [ ] Mensagens de erro devem explicar claramente o problema e como corrigi-lo.
- [ ] Elementos desabilitados devem ser visualmente distinguíveis sem comprometer a legibilidade.
- [ ] Links devem possuir texto descritivo e compreensível fora de contexto.
- [ ] Menus, modais e componentes dinâmicos devem indicar corretamente seu estado para tecnologias assistivas.
- [ ] **[NOVO WCAG 2.2]** Em componentes com arrastar e soltar, oferecer alternativas por teclado ou interfaces alternativas de seleção.
- [ ] **[NOVO WCAG 2.2]** Garantir que o estado de foco seja perceptível em todos os componentes interativos, incluindo os customizados com JavaScript.

## Novidades em Relação à Versão V1

!!! tip "[NOVO - TG10/Grupo07]"

| Item | Descrição | Referência |
|---|---|---|
| Indicador de foco | Novo critério de contraste 3:1 e espessura mínima de 2px | SC 2.4.13 (AAA) |
| Espaçamento de texto | Configurações específicas para espaçamento entre linhas, parágrafos, letras e palavras | SC 1.4.12 (AA) |
| Tamanho de alvo | Área clicável mínima de 24×24px (AA) ou 44×44px (AAA) | SC 2.5.8 (AA) |
| Apresentação do foco | Recomendação explícita de uso de `:focus-visible` | SC 2.4.7 (AA) |
| Componentes interativos | Seção completa com diretrizes para componentes dinâmicos | Múltiplas SCs |
| Tipografia | Seção dedicada com recomendações específicas | SC 1.4.4, 1.4.8 |
| Espaçamento visual | Seção dedicada com valores mínimos recomendados | SC 1.4.12 |

## Referências Bibliográficas

??? note "Ver lista completa de referências (WCAG 2.2 / NBR 17225:2025)"
    <a id="RP_D1" href="#TEC_D1">D1.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 2.4.13 Focus Appearance (Level AAA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/focus-appearance.html. Acesso em: jun. 2026. | NBR 17225:2025 (5.1.3)

    <a id="RP_D2" href="#TEC_D2">D2.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 1.4.12 Text Spacing (Level AA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html. Acesso em: jun. 2026. | NBR 17225:2025 (5.1.4)

    <a id="RP_D3" href="#TEC_D3">D3.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 1.4.4 Resize Text (Level AA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html. Acesso em: jun. 2026. | NBR 17225:2025 (5.1.2)

    <a id="RP_D4" href="#TEC_D4">D4.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 2.5.8 Target Size (Minimum) (Level AA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html. Acesso em: jun. 2026.

    <a id="RP_D5" href="#TEC_D5">D5.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 2.4.7 Focus Visible (Level AA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html. Acesso em: jun. 2026. | NBR 17225:2025 (5.2)

    <a id="RP1" href="#TEC1">1.</a> WCAG 2.2 Understanding Docs. SC 1.4.1 Use of Color (Level A). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html. Acesso em: 9 Mai. 2024.

    <a id="RP2" href="#TEC2">2.</a> WCAG 2.2 Understanding Docs. SC 1.4.4 Resize Text (Level AA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html. Acesso em: 9 Mai. 2024.

    <a id="RP3" href="#TEC3">3.</a> WCAG 2.2 Understanding Docs. SC 1.3.3 Sensory Characteristics (Level A). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/sensory-characteristics.html. Acesso em: 9 Mai. 2024.

    <a id="RP4" href="#TEC4">4.</a> WCAG 2.2 Understanding Docs. SC 1.4.11 Non-text Contrast (Level AA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html. Acesso em: 9 Mai. 2024.

    <a id="RP5" href="#TEC5">5.</a> WCAG 2.2 Understanding Docs. SC 1.4.10 Reflow (Level AA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/reflow.html. Acesso em: 9 Mai. 2024.

    <a id="RP6" href="#TEC6">6.</a> WCAG 2.2 Understanding Docs. SC 2.3.1 Three Flashes or Below Threshold (Level A). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html. Acesso em: 9 Mai. 2024.

    <a id="RP7" href="#TEC7">7.</a> WCAG 2.2 Understanding Docs. SC 2.2.2 Pause, Stop, Hide (Level A). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/pause-stop-hide.html. Acesso em: 9 Mai. 2024.

    <a id="RP8" href="#TEC8">8.</a> WCAG 2.2 Understanding Docs. SC 2.3.3 Animation from Interactions (Level AAA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html. Acesso em: 9 Mai. 2024.

    <a id="RP9" href="#TEC9">9.</a> WCAG 2.2 Understanding Docs. SC 1.4.3 Contrast (Minimum) (Level AA). Disponível em: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html. Acesso em: 9 Mai. 2024.

## Bibliografia

??? note "Ver bibliografia completa"
    DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R. Guia de Boas Práticas para Acessibilidade Digital. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023. Disponível em: https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf. Acesso em: 9 Mai. 2024.

    W3C. Web Content Accessibility Guidelines (WCAG) 2.2. Disponível em: https://www.w3.org/TR/WCAG22/. Acesso em: jun. 2026.

    ABNT NBR 17225:2025 - Tecnologia da Informação — Acessibilidade para pessoas com deficiência em sistemas de computação. Disponível em: https://www.abnt.org.br. Acesso em: jun. 2026.
