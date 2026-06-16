# Gestão de Projetos de Acessibilidade

> **[NOVO - TG10/Grupo07]** Esta seção foi atualizada para incluir a **ABNT NBR 17225:2025** como referência normativa obrigatória e reforçar o contexto legal brasileiro. Itens marcados com `[NOVO NBR/WCAG 2.2]` não estavam na versão V1 (VerificaAAA, 2024). Referência: TG10 – Estudo Aprofundado WCAG 2.2 (Grupo 7, 2026).

> **[NOVO NBR/WCAG 2.2]** Contexto legal obrigatório: No Brasil, a **ABNT NBR 17225:2025** adotou integralmente o WCAG 2.2 como base técnica. A conformidade com níveis **A e AA** é exigida por:
> - Lei nº 13.146/2015 – Lei Brasileira de Inclusão (LBI)
> - Decreto nº 5.296/2004 – obrigatoriedade de acessibilidade em serviços digitais públicos
> - ABNT NBR 17225:2025 – norma técnica vigente

# Primeiro Passo

"Para que a acessibilidade digital possa impactar positivamente a vida de milhões de pessoas, ela deve ser pensada logo no início, na concepção do projeto, fase de iniciação na Gestão de Projetos de Acessibilidade" <a id="TEC1" href="#RP1">[1]</a>.

Nessa lógica, durante a etapa inicial do desenvolvimento de um software, elabore personas com os seguintes perfis abaixo, dessa forma, seu projeto vai garantir que o software contenha requisitos de acessibilidade.

Em seu projeto, foram elaboradas personas para... 

- [ ] <b> Pessoas com Deficiência Visual </b> (cegueira, baixa visão, daltonismo ou deficiência cromática)
- [ ] <b> Pessoas com Deficiência Física </b> (fraqueza, tremores, movimentos involuntá rios, paralisia, limitações da sensação, dor que impede movimento, ausênciade membros) 
- [ ] <b> Pessoas com Deficiência Auditiva </b> (surdez, baixa audição, surdocegueira)
- [ ] <b> Pessoas com Deficiência na Fala </b> (dificuldade para falar, volume insuficiente, gagueira, mudez) 
- [ ] <b> Pessoas Neurodiversas </b> (dificuldades de diferentes graus para ver, escutar, falar, compreender e interagir socialmente)
- [ ] <b> Pessoas com Múltiplas Deficiências </b> (combinação de duas ou mais deficiências anteriores)
- [ ] <b> Possíveis limitações decorrentes do envelhecimento </b> (que podem ser de um ou mais grupos de deficiências)
- [ ] <b> Pessoas com analfabetismo </b> (analfabetismo digital e funcional níveis 1, 2 e 3)

# Conscientização

"Na iniciação do projeto, é necessário garantir que a equipe de projeto esteja consciente sobre a questão da acessibilidade digital, dos direitos das pessoas com deficiência e do potencial de mercado desse público" <a id="TEC1" href="#RP1">[1]</a>.

Sendo assim, existem argumentos que podem facilitar o processo de conscientização da equipe sobre a questão da acessibilidade digital. Esse argumentos estão representados no checklist abaixo. 

Em seu projeto, a equipe está consciente de...

- [ ] Quantidade de pessoas no mundo com algum tipo de deficiência.
- [ ] Quantidade de pessoas no Brasil com algum tipo de deficiência, segundo IBGE.
- [ ] Natureza da deficiência: congênita, hereditária, adquirida, temporária.
- [ ] Grupos mais comuns de tipos de deficiência.
- [ ] Quanto custa a acessibilidade?
- [ ] Quanto tempo a mais o projeto precisará para implementar acessibilidade?
- [ ] Quantas pessoas com deficiência vão usar meu aplicativo ou acessar meu sítio de Internet?
- [ ] Pessoas cegas compram online?
- [ ] Pessoas tetraplégicas usam smartphone?
- [ ] Legislação: A Convenção sobre os Direitos das Pessoas com Deficiência Comentada.
- [ ] Legislação: PORTARIA Nº 3, DE 7 DE MAIO DE 2007.
- [ ] Análise de mercado de software de acessibilidade digital.

# Planejamento

"É importante prever e elaborar a arquitetura para todos os públicos com deficiência, visando uma vida autônoma, com segurança e bem-estar" <a id="TEC1" href="#RP1">[1]</a>.

Assim, é de suma importância que se tenha, incluso no plano de projeto, e, definição de recursos alocados, para estratégia de acessibilidade de um projeto de software. 

Em seu planejamento, há...

- [ ] Atividades bem delineadas, cronogramas e atribuições de responsabilidade relacionadas à acessibilidade?
- [ ] Recursos alocados (pessoas, softwares, cursos, tarefas)?
- [ ] Tarefas com critérios de sucesso que atendam pelo menos os níveis A e AA, segundo a documentação de acessibilidade (WCAG 2.2)?
- [ ] **[NOVO NBR/WCAG 2.2]** Referência à **ABNT NBR 17225:2025** como norma técnica brasileira vigente nos critérios de aceitação?
- [ ] **[NOVO NBR/WCAG 2.2]** Combinação de testes automatizados (axe, Lighthouse) **e** testes manuais (teclado, leitor de tela), sabendo que ferramentas automatizadas cobrem apenas ~30-40% dos critérios?
- [ ] **[NOVO NBR/WCAG 2.2]** Abordagem **Shift-left**: acessibilidade incluída desde o planejamento e design, não como correção retroativa?

# Documentação Inclusiva

A acessibilidade começa pelos artefatos que a equipe produz. Garanta que a documentação do projeto também siga os critérios do WCAG 2.2 e da ABNT NBR 17225:2025.

Em sua documentação, há...

- [ ] **Texto alternativo** em diagramas, *wireframes*, fluxos e capturas de tela usados em documentos e apresentações? (WCAG 1.1.1, NBR 5.1)
- [ ] **Hierarquia de títulos** correta (H1 → H2 → H3) em documentos, *wikis* e páginas do guia, sem pular níveis? (WCAG 1.3.1)
- [ ] **Contraste mínimo** de 4.5:1 em textos de *slides*, planilhas e relatórios? (WCAG 1.4.3)
- [ ] Informação **não transmitida apenas por cor** (ex.: status de tarefas no quadro Kanban indicado também por rótulo ou ícone)? (WCAG 1.4.1)
- [ ] **Linguagem simples e objetiva**, evitando jargão desnecessário e explicando siglas na primeira ocorrência?
- [ ] **Tabelas com cabeçalhos** identificados e estrutura semântica, em vez de tabelas usadas apenas para layout? (WCAG 1.3.1)
- [ ] **Links descritivos** (evitar "clique aqui"), indicando o destino pelo próprio texto do link? (WCAG 2.4.4)
- [ ] Documentos exportados (PDF, DOCX) verificados com checagem de acessibilidade antes da distribuição?

# Critérios de Aceite Acessíveis

Acessibilidade só é entregue de forma consistente quando vira **critério de aceite** mensurável nas histórias de usuário, e não uma intenção genérica. Ao escrever histórias, garanta que...

- [ ] Cada história com interface tem **critérios de aceite de acessibilidade explícitos**, vinculados a critérios WCAG 2.2 específicos (ex.: "todos os campos do formulário possuem `label` associado — WCAG 1.3.1, 3.3.2")?
- [ ] Os critérios são **verificáveis** (testáveis por ferramenta automatizada, teclado ou leitor de tela), não subjetivos?
- [ ] O **nível-alvo de conformidade** (A e AA, conforme NBR 17225:2025) está declarado no critério?
- [ ] Histórias de componentes interativos incluem critérios para **navegação por teclado**, **foco visível** (2.4.7, 2.4.11) e **tamanho de alvo ≥ 24×24px** (2.5.8)?
- [ ] Histórias de conteúdo dinâmico incluem critérios para **regiões `aria-live`** e anúncio de mudanças a leitores de tela?
- [ ] Há critérios para **mensagens de erro acessíveis** (associadas ao campo, descritivas, não apenas por cor — 3.3.1, 3.3.3)?

# Definition of Done (DoD) com Acessibilidade

Uma tarefa ou história só está **"pronta" (Done)** quando a acessibilidade foi verificada. Inclua os itens abaixo na *Definition of Done* da equipe.

Antes de marcar como concluído, a equipe verificou que...

- [ ] **Teste automatizado** executado (axe DevTools, Lighthouse ou equivalente) sem violações de nível A/AA pendentes?
- [ ] **Teste manual por teclado** realizado: toda a funcionalidade é operável sem mouse, com ordem de foco lógica e foco sempre visível? (2.1.1, 2.4.3, 2.4.7)
- [ ] **Teste com leitor de tela** (NVDA ou VoiceOver) em pelo menos um fluxo crítico da entrega?
- [ ] **Contraste de cores** validado nos componentes novos/alterados? (1.4.3, 1.4.11)
- [ ] **Critérios de aceite de acessibilidade** da história todos satisfeitos e marcados?
- [ ] Lembrando que ferramentas automatizadas cobrem apenas **~30-40%** dos critérios — o teste manual **não** pode ser pulado?
- [ ] **Documentação inclusiva** atualizada (texto alternativo em novas imagens, *changelog* registrado)?
- [ ] Conformidade declarada conforme **ABNT NBR 17225:2025** (níveis A e AA)?

## Referências Bibliográficas

> <a id="RP1" href="#TEC1">1.</a> DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R. Guia de Boas Práticas para Acessibilidade Digital. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf). Acesso em: 9 Mai. 2024.

## Bibliografia

> **[NOVO]** ABNT. NBR 17225:2025 – Acessibilidade em ambientes virtuais – Requisitos e Recomendações. Associação Brasileira de Normas Técnicas, 2025.

> **[NOVO]** W3C. Web Content Accessibility Guidelines (WCAG) 2.2. World Wide Web Consortium, outubro 2023. Disponível em: [https://www.w3.org/TR/WCAG22/](https://www.w3.org/TR/WCAG22/). Acesso em: jun. 2026.

> </a> A Convenção sobre Direitos das Pessoas com Deficiência comentada / Coordenação de Ana Paula Crosara de Resende e Flavia Maria de Paiva Vital . _ Brasília : Secretaria Especial dos Direitos Humanos, 2008. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/convencao-direitos-pessoas-deficiencia-comentada.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/convencao-direitos-pessoas-deficiencia-comentada.pdf). Acesso em: 9 Mai. 2024

> </a> BRASIL. Secretaria de Logística e Tecnologia da Informação. Portaria nº 3, de 7 de maio de 2007. Institucionaliza o Modelo de Acessibilidade em Governo Eletrônico – e-MAG no âmbito do Sistema de Administração dos Recursos de Informação e Informática – SISP. Diário Oficial da União, Brasília, DF, 7 maio 2007. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/legislacao/portaria3_eMAG.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/legislacao/portaria3_eMAG.pdf). Acesso em: 9 Mai. 2024

> </a> MORDOR INTELLIGENCE. Digital Accessibility Software Market Size & Share Analysis- Growth Trends & Forecasts (2024-2029). Disponível em: [https://www.mordorintelligence.com/industry-reports/digital-accessibility-software-market](https://www.mordorintelligence.com/industry-reports/digital-accessibility-software-market). Acesso em: 9 Mai. 2024

> </a> WORLD WIDE WEB CONSORTIUM. Web Content Accessibility Guidelines (WCAG) 2.1. Recomendação W3C, 21 setembro 2023. Disponível em: [https://www.w3.org/TR/WCAG21/#sotd](https://www.w3.org/TR/WCAG21/#sotd). Acesso em: 9 Mai. 2024