# UX Design e Acessibilidade

## O que é UX Design?

A Experiência do Usuário (UX, do inglês *User Experience*) é o conjunto de percepções, emoções e respostas que uma pessoa experimenta ao interagir com um produto, sistema ou serviço. O UX Design é a disciplina responsável por projetar essas interações de forma intencional, buscando garantir que elas sejam eficientes, satisfatórias e — fundamentalmente — **acessíveis a todas as pessoas**.

> Segundo a norma **ISO 9241-210:2019**, UX abrange "as percepções e respostas de uma pessoa resultantes do uso e/ou uso antecipado de um produto, sistema ou serviço", incluindo emoções, crenças, preferências, comportamentos e realizações.

No contexto da acessibilidade digital, o UX Design vai além da usabilidade convencional. Seu objetivo é garantir que pessoas com deficiência visual, auditiva, motora, cognitiva ou múltipla possam interagir com produtos digitais com a mesma autonomia e satisfação que qualquer outro usuário.

---

## Métodos de Avaliação UX

Os métodos de avaliação em UX se dividem em diferentes dimensões complementares:

### Por natureza da coleta

| Tipo | O que avalia | Exemplos |
|---|---|---|
| **Atitudinal** | Crenças, opiniões e percepções dos usuários | Entrevistas, questionários, escala SUS |
| **Comportamental** | Ações e interações diretas com a interface | Testes de usabilidade, eye-tracking |

### Por forma de análise

| Tipo | Característica | Aplicação |
|---|---|---|
| **Qualitativo** | Profundidade de compreensão | Descobrir *por que* algo acontece |
| **Quantitativo** | Métricas e dados numéricos | Medir *o quanto* algo ocorre |

### Por momento do desenvolvimento

- **Avaliação Formativa**: ocorre *durante* o desenvolvimento; tem caráter diagnóstico e permite corrigir problemas antes do lançamento.
- **Avaliação Somativa**: realizada *ao final* do desenvolvimento; mede a qualidade final da experiência entregue.

### Por participação de usuários

- **Empírica**: envolve diretamente usuários finais em testes de uso real.
- **Analítica**: baseada em conhecimentos prévios e heurísticas, sem participação direta de usuários (ex.: Avaliação Heurística de Nielsen).

---

## UX Design Acessível: Princípios Fundamentais

Um design verdadeiramente centrado no usuário deve incorporar acessibilidade desde o início do processo — não como uma camada adicionada ao final, mas como parte integrante de todas as decisões de projeto. A abordagem **Shift-Left** em acessibilidade significa que quanto mais cedo os princípios acessíveis forem aplicados, menor o custo e esforço de correção.

### 1. Design Universal e Inclusivo

O Design Universal propõe criar soluções que funcionem para o maior número possível de pessoas, sem a necessidade de adaptações especiais. Seus 7 princípios são:

1. **Uso equitativo** — o design é útil e vendável para pessoas com diversas habilidades.
2. **Flexibilidade de uso** — acomoda uma ampla gama de preferências e habilidades individuais.
3. **Uso simples e intuitivo** — fácil de entender, independentemente de experiência ou nível cognitivo.
4. **Informação perceptível** — transmite informação essencial efetivamente para o usuário, independente das condições ambientais ou das capacidades sensoriais da pessoa.
5. **Tolerância ao erro** — minimiza os riscos e consequências adversas de ações acidentais ou não intencionais.
6. **Baixo esforço físico** — pode ser usado de forma eficiente, confortável e com mínimo de fadiga.
7. **Tamanho e espaço para aproximação e uso** — garante espaço apropriado para aproximação e uso, independentemente do tamanho do corpo, postura ou mobilidade do usuário.

### 2. Os 4 Princípios do WCAG (POUR)

As Diretrizes de Acessibilidade para Conteúdo Web (WCAG 2.2), adotadas pela **ABNT NBR 17225:2025** como norma técnica brasileira, estruturam a acessibilidade em quatro princípios fundamentais:

| Princípio | Significado |
|---|---|
| **Perceptível** | Informações e componentes de interface devem ser apresentados de formas que os usuários possam perceber. |
| **Operável** | Componentes de interface e navegação devem ser operáveis por diferentes meios (teclado, voz, etc.). |
| **Compreensível** | Informações e operações de interface devem ser compreensíveis. |
| **Robusto** | Conteúdo deve ser interpretável por tecnologias assistivas, incluindo as futuras. |

### 3. Empatia com Diversidade Funcional

Projetar com empatia envolve compreender as diferentes formas de interação com um produto:

- **Deficiência visual**: uso de leitores de tela (NVDA, VoiceOver), telas braille, ampliação de tela.
- **Deficiência motora**: navegação por teclado, switches, eye-tracking.
- **Deficiência auditiva**: legendas, transcrições, alternativas visuais a alertas sonoros.
- **Deficiência cognitiva**: linguagem simples, navegação previsível, prevenção de erros.

---

## Checklist de Boas Práticas de UX para Acessibilidade

### Visual e Perceptibilidade

- [ ] Contraste de cor entre texto e fundo é de no mínimo **4,5:1** (nível AA, WCAG 1.4.3)?
- [ ] Informações críticas não dependem **apenas de cor** para serem transmitidas (WCAG 1.4.1)?
- [ ] Elementos não-textuais (ícones, gráficos) possuem texto alternativo descritivo (WCAG 1.1.1)?
- [ ] O indicador de foco é visível e com contraste mínimo de **3:1** (WCAG 2.4.11)?
- [ ] Animações e movimentos podem ser pausados ou desativados pelo usuário (WCAG 2.3.3)?
- [ ] O layout é responsivo e funciona em diferentes tamanhos de tela e orientações (WCAG 1.4.10)?

### Operabilidade e Interação

- [ ] Toda funcionalidade é acessível via **teclado** (sem necessidade de mouse) (WCAG 2.1.1)?
- [ ] O **foco do teclado** percorre os elementos em ordem lógica (WCAG 2.4.3)?
- [ ] Elementos interativos possuem área de clique/toque mínima de **24×24px** (WCAG 2.5.8)?
- [ ] Funcionalidades que exigem gesto de arrastar possuem **alternativa de teclado** (WCAG 2.5.7)?
- [ ] Não há armadilhas de foco: o usuário consegue entrar e sair de qualquer componente (WCAG 2.1.2)?
- [ ] Modais e overlays prendem o foco corretamente e retornam ao elemento de origem ao fechar?

### Compreensibilidade e Linguagem

- [ ] A linguagem utilizada é clara, direta e adequada ao público-alvo (WCAG 3.1)?
- [ ] Mensagens de erro são **descritivas e orientam a correção** (WCAG 3.3.1 e 3.3.3)?
- [ ] Dados já fornecidos pelo usuário **não são solicitados novamente** sem motivo (WCAG 3.3.7)?
- [ ] Processos de autenticação não exigem testes cognitivos como CAPTCHAs visuais (WCAG 3.3.8)?
- [ ] Ajuda contextual está disponível e em **posição consistente** em todas as páginas (WCAG 3.2.6)?
- [ ] O idioma principal da página está declarado no código HTML (`lang="pt-BR"`) (WCAG 3.1.1)?

### Processo e Design Inclusivo

- [ ] Personas com diferentes necessidades de acessibilidade foram criadas e usadas no projeto?
- [ ] Testes de usabilidade foram conduzidos com usuários com deficiência?
- [ ] A acessibilidade foi considerada desde o início do projeto (**Shift-Left**), não como correção retroativa?
- [ ] Foram utilizadas ferramentas de avaliação automatizada (axe, Lighthouse) **E** testes manuais (teclado, leitor de tela)?
- [ ] O projeto referencia a **ABNT NBR 17225:2025** e o **WCAG 2.2** como padrões de conformidade?

---

## Referências Bibliográficas

> <a id="RP1" href="#TEC1">1.</a> ISO. **ISO 9241-210:2019** — Ergonomics of human-system interaction. Part 210: Human-centred design for interactive systems. International Organization for Standardization, 2019.

> <a id="RP2" href="#TEC2">2.</a> W3C. **Web Content Accessibility Guidelines (WCAG) 2.2**. World Wide Web Consortium, outubro 2023. Disponível em: [https://www.w3.org/TR/WCAG22/](https://www.w3.org/TR/WCAG22/).

> <a id="RP3" href="#TEC3">3.</a> ABNT. **NBR 17225:2025** — Acessibilidade em ambientes virtuais. Associação Brasileira de Normas Técnicas, 2025.

> <a id="RP4" href="#TEC4">4.</a> BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Rio de Janeiro: Elsevier, 2010.

> <a id="RP5" href="#TEC5">5.</a> NIELSEN, J. **10 Usability Heuristics for User Interface Design**. Nielsen Norman Group, 1994. Disponível em: [https://www.nngroup.com/articles/ten-usability-heuristics/](https://www.nngroup.com/articles/ten-usability-heuristics/).

> <a id="RP6" href="#TEC6">6.</a> The Center for Universal Design. **The Principles of Universal Design** (Version 2.0). North Carolina State University, 1997. Disponível em: [https://design.ncsu.edu/research/center-for-universal-design/](https://design.ncsu.edu/research/center-for-universal-design/).
