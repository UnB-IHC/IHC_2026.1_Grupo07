# :material-format-list-checks: Checklist de Acessibilidade Digital

> NBR 17225 / WCAG 2.2 / Guia UK-Brasil

!!! info "Como usar"
    Os 18 itens estão organizados em 4 categorias (A–D). Cada item indica a **Classificação** (Requisito = obrigatório para conformidade AA; Recomendação = boas práticas além do mínimo) e o **Pilar de Aplicação** (quem na equipe é responsável). Use a [Tabela Resumo](#tabela-resumo-do-checklist) no final como visão rápida.

## :material-eye-outline: A. Percepção Visual e Auditiva

*   **[ ] 1. Texto Alternativo para Imagens**
    *   **Descrição Técnica:** Todas as imagens que transmitem conteúdo devem possuir atributo `alt` descritivo. Imagens complexas (gráficos/infográficos) exigem descrição detalhada no próprio texto adjacente ou em página indicada. Imagens puramente decorativas devem ter `alt=""` para serem ignoradas por tecnologia assistiva.
    *   **Referência Normativa:** NBR 17225 (5.2.1, 5.2.3, 5.2.4) | WCAG 2.2 (C.S. 1.1.1 - Nível A)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Conteúdo / Desenvolvimento

*   **[ ] 2. Contraste Mínimo de Cores**
    *   **Descrição Técnica:** A interface deve garantir que textos normais tenham uma razão de contraste de 4.5:1 com o fundo, e textos grandes (18pt ou 14pt negrito) tenham 3:1. Além disso, elementos de interface de usuário e gráficos de dados também devem respeitar o limite mínimo de 3:1 contra cores adjacentes.
    *   **Referência Normativa:** NBR 17225 (5.11.3, 5.11.4) | WCAG 2.2 (C.S. 1.4.3 e 1.4.11 - Nível AA)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Design

*   **[ ] 3. Uso Restrito da Cor**
    *   **Descrição Técnica:** A cor não deve ser o único meio de transmitir uma informação, indicar uma ação, pedir uma resposta ou distinguir um elemento visual.
    *   **Referência Normativa:** NBR 17225 (5.11.1) | WCAG 2.2 (C.S. 1.4.1 - Nível A)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Design / Conteúdo

*   **[ ] 4. Controle de Áudio e Mídia**
    *   **Descrição Técnica:** Áudios que tocam automaticamente por mais de 3 segundos devem possuir controles para pausar, parar, silenciar ou ajustar o seu volume independentemente do sistema. Para conformidade plena, o áudio focado na fala não deve possuir sons de fundo ou estes devem estar em um volume que não interfira no som principal.
    *   **Referência Normativa:** NBR 17225 (5.14.7, 5.14.8) | WCAG 2.2 (C.S. 1.4.2 - Nível A e C.S. 1.4.7 - Nível AAA)
    *   **Classificação:** Requisito (Nível A) e Recomendação (Nível AAA)
    *   **Pilar de Aplicação:** Desenvolvimento / Design

*   **[ ] 5. Design Responsivo e Refluxo (Reflow) `[Lacuna Preenchida]`**
    *   **Descrição Técnica:** O conteúdo da página não deve perder informação ou funcionalidade quando houver rolagem vertical com largura equivalente a 320px CSS ou rolagem horizontal com altura equivalente a 256px CSS.
    *   **Referência Normativa:** NBR 17225 (5.10.4) | WCAG 2.2 (C.S. 1.4.10 - Nível AA)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Design / Desenvolvimento

---

## :material-gesture-tap-button: B. Operabilidade e Navegação

*   **[ ] 6. Foco Visível e Não Obscurecido `[Lacuna Preenchida WCAG 2.2]`**
    *   **Descrição Técnica:** Todos os elementos focáveis devem ter um indicador de foco visível. Além disso, o elemento que recebe foco deve estar pelo menos parcialmente visível, considerando a sobreposição por elementos de autoria do desenvolvedor.
    *   **Referência Normativa:** NBR 17225 (5.1.1, 5.1.3) | WCAG 2.2 (C.S. 2.4.7 e 2.4.11 - Nível AA)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Design / Desenvolvimento

*   **[ ] 7. Atalhos de Teclado (Skip Links)**
    *   **Descrição Técnica:** Devem ser fornecidos mecanismos (links ou atalhos) que permitam contornar blocos de conteúdo que se repetem em um conjunto de páginas.
    *   **Referência Normativa:** NBR 17225 (5.7.12) | WCAG 2.2 (C.S. 2.4.1 - Nível A)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Desenvolvimento

*   **[ ] 8. Tamanho do Alvo de Clique `[Lacuna Preenchida WCAG 2.2]`**
    *   **Descrição Técnica:** Todos os elementos interativos devem ter uma área de acionamento de pelo menos 24 pixels CSS de altura e largura, ou possuir espaçamento em relação aos adjacentes que some essa dimensão.
    *   **Referência Normativa:** NBR 17225 (5.8.7) | WCAG 2.2 (C.S. 2.5.8 - Nível AA)
    *   **Classificação:** Requisito *(Nota: Áreas de 44 pixels configuram Recomendação/Nível AAA)*
    *   **Pilar de Aplicação:** Design / Desenvolvimento

*   **[ ] 9. Movimentos de Arrastar (Drag-and-Drop) `[Lacuna Preenchida WCAG 2.2]`**
    *   **Descrição Técnica:** Toda funcionalidade operada por movimento de arrastar deve poder ser operada também por um ponteiro único sem esse movimento.
    *   **Referência Normativa:** NBR 17225 (5.8.13) | WCAG 2.2 (C.S. 2.5.7 - Nível AA)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Desenvolvimento / Design

*   **[ ] 10. Temporização Ajustável**
    *   **Descrição Técnica:** Deve haver um mecanismo simples para desligar, ajustar ou estender o limite de tempo imposto pelo conteúdo antes que ele seja atingido.
    *   **Referência Normativa:** NBR 17225 (5.16.2) | WCAG 2.2 (C.S. 2.2.1 - Nível A)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Desenvolvimento / Gestão

---

## :material-help-circle-outline: C. Compreensibilidade e Ajuda

*   **[ ] 11. Títulos de Página e Semântica de Cabeçalhos**
    *   **Descrição Técnica:** A página deve possuir um título único que a identifique. Os cabeçalhos internos devem seguir uma estrutura hierárquica, lógica e semântica determinada programaticamente.
    *   **Referência Normativa:** NBR 17225 (5.13.1, 5.3.1, 5.3.5) | WCAG 2.2 (C.S. 2.4.2 - Nível A, 1.3.1 - Nível A e 2.4.6 - Nível AA)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Desenvolvimento / Conteúdo

*   **[ ] 12. Consistência na Interface e Ajuda Consistente `[Lacuna Preenchida WCAG 2.2]`**
    *   **Descrição Técnica:** Componentes que repetem a mesma funcionalidade em um conjunto de páginas devem ter identificação, navegação e mecanismos de ajuda dispostos de maneira consistente e na mesma ordem relativa.
    *   **Referência Normativa:** NBR 17225 (5.7.15, 5.7.16, 5.8.5) | WCAG 2.2 (C.S. 3.2.3, 3.2.4 - Nível AA e 3.2.6 - Nível A)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Design / Gestão

*   **[ ] 13. Identificação Programática do Idioma**
    *   **Descrição Técnica:** O idioma padrão da página deve ser declarado programaticamente. Da mesma forma, alterações de idioma em partes específicas do texto também devem ser marcadas.
    *   **Referência Normativa:** NBR 17225 (5.13.2, 5.13.3) | WCAG 2.2 (C.S. 3.1.1 - Nível A, 3.1.2 - Nível AA)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Desenvolvimento / Conteúdo

*   **[ ] 14. Identificação, Sugestão e Prevenção de Erros `[Refinado]`**
    *   **Descrição Técnica:** Mensagens de erro devem ser descritivas em texto e indicar o campo exato. O sistema deve fornecer sugestões de correção e, para formulários críticos (financeiros/jurídicos), permitir reverter, verificar ou confirmar os dados.
    *   **Referência Normativa:** NBR 17225 (5.9.9, 5.9.10, 5.9.12) | WCAG 2.2 (C.S. 3.3.1 - Nível A, 3.3.3 e 3.3.4 - Nível AA)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Desenvolvimento / Design

*   **[ ] 15. Prevenção de Entradas Redundantes `[Lacuna Preenchida WCAG 2.2]`**
    *   **Descrição Técnica:** Campos que exijam informações fornecidas anteriormente no mesmo fluxo devem preenchê-las automaticamente ou disponibilizá-las para seleção, exceto se a reentrada for essencial.
    *   **Referência Normativa:** NBR 17225 (5.9.15) | WCAG 2.2 (C.S. 3.3.7 - Nível A)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Design / Desenvolvimento

*   **[ ] 16. Autenticação Acessível (Sem Testes Cognitivos) `[Lacuna Preenchida WCAG 2.2]`**
    *   **Descrição Técnica:** Processos de autenticação não devem exigir testes de função cognitiva (como memorizar senhas complexas ou fazer cálculos), a menos que haja um método alternativo ou suporte a mecanismos como cópia/colagem e preenchimento automático.
    *   **Referência Normativa:** NBR 17225 (5.9.18) | WCAG 2.2 (C.S. 3.3.8 - Nível AA)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Desenvolvimento / Gestão

---

## :material-shield-check-outline: D. Robustez e Código Semântico

*   **[ ] 17. Nome, Função e Valor em Componentes Web `[Lacuna Preenchida Crítica]`**
    *   **Descrição Técnica:** Todos os componentes customizados devem possuir semântica determinada programaticamente, incluindo sua função (role), estados, propriedades e valores, garantindo que tecnologias assistivas identifiquem suas alterações.
    *   **Referência Normativa:** NBR 17225 (5.13.12, 5.13.13) | WCAG 2.2 (C.S. 4.1.2 - Nível A)
    *   **Classificação:** Requisito
    *   **Pilar de Aplicação:** Desenvolvimento

*   **[ ] 18. Linguagem Simples (Plain Language)**
    *   **Descrição Técnica:** O conteúdo textual deve adotar uma linguagem simples, clara e compreensível, provendo mecanismos para identificar a expansão de siglas, abreviaturas ou termos incomuns.
    *   **Referência Normativa:** NBR 17225 (5.12.11, 5.12.12) | WCAG 2.2 (C.S. 3.1.4 e 3.1.5 - Nível AAA)
    *   **Classificação:** Recomendação
    *   **Pilar de Aplicação:** Conteúdo

---

## Tabela Resumo do Checklist

| ID | Item de Verificação | NBR 17225:2025 | WCAG 2.2 (C.S.) | Tipo | Pilar Principal |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | Texto Alternativo para Imagens | 5.2.1, 5.2.3, 5.2.4 | 1.1.1 (Nível A) | Requisito | Conteúdo / Dev |
| **2** | Contraste Mínimo de Cores | 5.11.3, 5.11.4 | 1.4.3 / 1.4.11 (Nível AA) | Requisito | Design |
| **3** | Uso Restrito da Cor | 5.11.1 | 1.4.1 (Nível A) | Requisito | Design / Conteúdo |
| **4** | Controle de Áudio e Mídia | 5.14.7, 5.14.8 | 1.4.2 (A) / 1.4.7 (AAA) | Req. / Rec. | Dev / Design |
| **5** | Design Responsivo e Refluxo | 5.10.4 | 1.4.10 (Nível AA) | Requisito | Design / Dev |
| **6** | Foco Visível e Não Obscurecido | 5.1.1, 5.1.3 | 2.4.7 / 2.4.11 (Nível AA) | Requisito | Design / Dev |
| **7** | Atalhos de Teclado (Skip Links) | 5.7.12 | 2.4.1 (Nível A) | Requisito | Desenvolvimento |
| **8** | Tamanho do Alvo de Clique | 5.8.7 | 2.5.8 (Nível AA) | Requisito | Design / Dev |
| **9** | Movimentos de Arrastar (Drag) | 5.8.13 | 2.5.7 (Nível AA) | Requisito | Dev / Design |
| **10** | Temporização Ajustável | 5.16.2 | 2.2.1 (Nível A) | Requisito | Dev / Gestão |
| **11** | Títulos e Semântica de Cabeçalhos | 5.13.1, 5.3.1, 5.3.5 | 2.4.2 (A) / 1.3.1 (A) / 2.4.6 (AA) | Requisito | Dev / Conteúdo |
| **12** | Consistência e Ajuda Consistente | 5.7.15, 5.7.16, 5.8.5 | 3.2.3 / 3.2.4 / 3.2.6 | Requisito | Design / Gestão |
| **13** | Identificação do Idioma | 5.13.2, 5.13.3 | 3.1.1 (A) / 3.1.2 (AA) | Requisito | Dev / Conteúdo |
| **14** | Identificação e Prevenção de Erros | 5.9.9, 5.9.10, 5.9.12 | 3.3.1 (A) / 3.3.3 / 3.3.4 (AA) | Requisito | Dev / Design |
| **15** | Prevenção de Entradas Redundantes | 5.9.15 | 3.3.7 (Nível A) | Requisito | Design / Dev |
| **16** | Autenticação Acessível | 5.9.18 | 3.3.8 (Nível AA) | Requisito | Dev / Gestão |
| **17** | Nome, Função e Valor (Componentes) | 5.13.12, 5.13.13 | 4.1.2 (Nível A) | Requisito | Desenvolvimento |
| **18** | Linguagem Simples | 5.12.11, 5.12.12 | 3.1.4 / 3.1.5 (Nível AAA) | Recomendação | Conteúdo |