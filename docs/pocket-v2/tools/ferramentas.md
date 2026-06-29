# :material-toolbox-outline: Ferramentas de Acessibilidade

!!! info "[NOVO - TG10/Grupo07]"
    Esta seção foi reestruturada com avaliação comparativa, indicação de adequação por perfil de uso e passo a passo para as ferramentas principais. Referência: TG10 – Estudo Aprofundado WCAG 2.2 (Grupo 7, 2026); ABNT NBR 17225:2025, seção 6.

!!! warning "Nota metodológica importante"
    Ferramentas automatizadas cobrem apenas **30–40% dos critérios WCAG 2.2**. Os demais exigem avaliação humana – teste manual por teclado, leitor de tela e inspeção visual. Nenhuma ferramenta substitui o outro método. Use ambos. (Fonte: ABNT NBR 17225:2025; W3C WAI Understanding WCAG 2.2)

---

## Visão Geral: Qual ferramenta usar para quê?

| Ferramenta | Tipo | Perfil de Usuário | Melhor Para | Limitação Principal |
|---|---|---|---|---|
| axe DevTools | Automatizado | Desenvolvedor, QA | Encontrar erros ARIA, contraste, semântica durante desenvolvimento | ~30-40% dos critérios |
| Lighthouse | Automatizado | Desenvolvedor, Gestor | Auditoria rápida integrada ao DevTools, inclui performance | Menos detalhado que axe |
| WAVE | Automatizado | Designer, Analista | Visualizar estrutura semântica e problemas de forma sobreposta | Apenas via navegador |
| Colour Contrast Analyser | Manual assistido | Designer, Desenvolvedor | Medir contraste exato de qualquer cor da tela com conta-gotas | Não testa conteúdo web em si |
| NVDA | Leitor de tela | QA, Desenvolvedor | Teste funcional real com usuário de leitura de tela (Windows) | Curva de aprendizado |
| VoiceOver | Leitor de tela | QA, Desenvolvedor | Teste funcional real com usuário de leitura de tela (macOS/iOS) | Apenas em plataformas Apple |
| JAWS | Leitor de tela | QA | Leitor mais utilizado por usuários reais (Windows, pago) | Licença comercial |
| Teste por teclado | Manual puro | Todos | Validar navegabilidade, foco visível, armadilhas de teclado | Demanda tempo |
| ACHECKS | Automatizado | QA | Verificação online rápida sem instalação | Menos atualizado que axe |
| WebAIM Contrast Checker | Automatizado | Designer, Desenvolvedor | Calcular razão de contraste por hex/RGB online | Não usa conta-gotas |
| Accessibility Insights | Híbrido | QA, Desenvolvedor | Testes automatizados (FastPass) e manuais guiados | Extensão focada no Chromium |
| Stark | Plugin/Extensão | Designer, QA | Validar acessibilidade direto no design (Figma) e código | Versão pro é paga |

---

## Ferramentas Detalhadas

### 1. axe DevTools (Deque Systems)
**Nível de Dificuldade:** Fácil  
**Prós:** Integração excelente com DevTools; indica a severidade e como resolver os erros; foca em zero falsos positivos.  
**Contras:** Cobre apenas cerca de 30-40% dos critérios WCAG; alguns problemas requerem revisão manual assistida.  
**Teste na prática (Exemplo Sabin):** Ao testar a página inicial do site do Sabin, o axe identificou rapidamente falhas de contraste em botões secundários e imagens sem atributo `alt` na estrutura do carrossel.  

**Tipo:** Extensão de navegador (Chrome, Firefox, Edge) – automatizado  
**Critérios cobertos:** ARIA, contraste, semântica HTML, rótulos, idioma, role/state  
**Ideal para:** Desenvolvedores front-end durante codificação  

> **[NOVO - TG10/Grupo07]** Recomendada como ferramenta primária de auditoria automatizada pela ABNT NBR 17225:2025 e pelo Guia DAP Gov.BR.

**Passo a passo:**

1. Instale a extensão "axe DevTools" na Chrome Web Store ou Mozilla Add-ons
2. Abra a página que deseja auditar
3. Pressione `F12` para abrir o DevTools
4. Vá até a aba **"axe DevTools"** (aparece ao final das abas do DevTools)
5. Clique em **"Scan ALL of my page"**
6. Os resultados são classificados em:
   - **Critical** (<span class="badge" style="background:#c62828;color:#fff;">Crítico</span>): viola critérios de nível A – corrigir imediatamente
   - **Serious** (<span class="badge" style="background:#e65100;color:#fff;">Sério</span>): viola nível AA – corrigir antes de publicar
   - **Moderate / Minor** (<span class="badge" style="background:#f9a825;color:#000;">Moderado/Menor</span>): melhoria recomendada
7. Clique em cada item para ver o elemento no DOM e a técnica de correção sugerida
8. Use o botão **"Highlight"** para localizar o elemento na página visualmente

**Integração CI/CD:** O `axe-core` (biblioteca base) pode ser integrado a testes automatizados com Jest, Cypress ou Playwright via `@axe-core/playwright` para bloquear regressões de acessibilidade no pipeline.

**Referência:** [github.com/dequelabs/axe-core](https://github.com/dequelabs/axe-core)

---

### 2. Lighthouse (Google)
**Nível de Dificuldade:** Fácil  
**Prós:** Nativo do Chrome (não exige instalação extra); gera relatórios fáceis de compartilhar com gestores; pontuação gamificada de 0 a 100.  
**Contras:** Menos detalhado e preciso que o axe para acessibilidade pura; pode dar pontuação 100 mesmo com graves falhas de teclado.  
**Teste na prática (Exemplo Sabin):** Analisou o site do Sabin fornecendo uma nota de 85/100, indicando elementos sem rótulos (ARIALabels) mas falhou em perceber botões que não recebiam foco pelo teclado.  

**Tipo:** Integrado ao Chrome DevTools – automatizado  
**Critérios cobertos:** Subconjunto de critérios WCAG A e AA, boas práticas gerais  
**Ideal para:** Auditoria rápida sem instalar nada; relatório de pontuação para stakeholders  

**Passo a passo:**

1. Abra a página no Chrome
2. Pressione `F12` → aba **"Lighthouse"**
3. Em "Categories", marque **"Accessibility"** (pode desmarcar as demais para foco)
4. Selecione "Device": Desktop ou Mobile conforme o contexto
5. Clique em **"Analyze page load"**
6. O relatório mostra uma pontuação de 0–100 e lista:
   - Itens que **passaram** (expandir para confirmar)
   - Itens que **falharam** com descrição do critério WCAG
   - Itens **não aplicáveis**
7. Clique em "Learn more" em cada item para acessar a documentação do critério

> **Atenção:** A pontuação 100 não significa conformidade total com WCAG 2.2. O Lighthouse cobre ~30% dos critérios e não substitui testes manuais.

**Referência:** [developer.chrome.com/docs/lighthouse](https://developer.chrome.com/docs/lighthouse)

---

### 3. WAVE – Web Accessibility Evaluation Tool (WebAIM)
**Nível de Dificuldade:** Fácil  
**Prós:** Visualização sobreposta no contexto da página facilita o entendimento por designers e não-técnicos; boa visualização da hierarquia de headings.  
**Contras:** Pode poluir visualmente páginas muito complexas; a interface lateral parece datada em telas menores.  
**Teste na prática (Exemplo Sabin):** No site do Sabin, o WAVE poluiu bastante a Home devido ao excesso de ícones de alerta próximos ao menu de navegação, mas foi excelente para confirmar a quebra da ordem de Headings (h2 seguido de h4).  

**Tipo:** Extensão de navegador ou site online – automatizado com visualização sobreposta  
**Critérios cobertos:** Estrutura de headings, imagens sem alt, formulários sem label, contraste  
**Ideal para:** Designers e analistas de conteúdo que preferem visualização visual inline  

**Passo a passo:**

1. Instale a extensão WAVE no navegador ou acesse [wave.webaim.org](https://wave.webaim.org/)
2. Para usar como extensão: abra a página alvo e clique no ícone WAVE na barra de ferramentas
3. A página é sobreposta com ícones coloridos:
   - <span class="badge" style="background:#c62828;color:#fff;">Erros</span> (ex: imagem sem alt, input sem label)
   - <span class="badge" style="background:#f9a825;color:#000;">Alertas</span> (possíveis problemas, revisar manualmente)
   - <span class="badge" style="background:#2e7d32;color:#fff;">Estrutura</span> (headings, landmarks – validar hierarquia)
   - <span class="badge" style="background:#1565c0;color:#fff;">Recursos de acessibilidade</span> presentes (aria-label, skip links)
4. No painel lateral, clique em qualquer ícone para saltar ao elemento no DOM
5. Use a aba **"Contrast"** para verificar todas as combinações de cor identificadas automaticamente

**Diferencial em relação ao axe:** O WAVE é mais visual e intuitivo para não-desenvolvedores. O axe é mais preciso tecnicamente e integra melhor com CI/CD.

**Referência:** [wave.webaim.org](https://wave.webaim.org/)

---

### 4. Colour Contrast Analyser – CCA (TPGi)
**Nível de Dificuldade:** Médio (exige entendimento das regras de contraste AA/AAA)  
**Prós:** Ferramenta desktop que funciona em qualquer software (Figma, PDFs, softwares legados); avalia contraste exato de elementos visuais não textuais.  
**Contras:** Exige instalação; processo manual e lento de clicar elemento por elemento.  
**Teste na prática (Exemplo Sabin):** Utilizamos o conta-gotas do CCA para avaliar o azul claro usado nos menus do Sabin sobre fundo branco, confirmando que a relação de contraste (2.1:1) reprova no critério 1.4.3 da WCAG.  

**Tipo:** Aplicativo desktop – manual assistido  
**Critérios cobertos:** WCAG 1.4.3 (contraste de texto), 1.4.11 (contraste de componentes), 2.4.13 (aparência do foco)  
**Ideal para:** Designers ao criar paletas; desenvolvedores ao validar estados de hover/focus  

> **[NOVO - TG10/Grupo07]** Ferramenta recomendada especificamente para validação do critério **WCAG 2.4.13 (AAA)** – Aparência do Foco, que exige contraste mínimo de 3:1 no indicador de foco. Não coberta por ferramentas automatizadas.

**Passo a passo:**

1. Baixe e instale o CCA em [tpgi.com/color-contrast-checker](https://www.tpgi.com/color-contrast-checker/)
2. Abra o aplicativo – você verá dois seletores de cor (Foreground / Background)
3. Clique no **conta-gotas** ao lado de "Foreground" e clique sobre o texto ou elemento na tela
4. Clique no conta-gotas de "Background" e clique sobre o fundo do elemento
5. O painel mostra a razão de contraste e indica se passa em:
   - **AA Normal Text** (4.5:1) – texto ≤ 18pt normal ou ≤ 14pt bold
   - **AA Large Text** (3:1) – texto > 18pt normal ou > 14pt bold
   - **AA UI Components** (3:1) – botões, campos, ícones informativos
   - **AAA Normal Text** (7:1)
6. Para testar o indicador de foco (WCAG 2.4.13): meça a cor do outline contra o fundo adjacente – deve ser ≥ 3:1

**Referência:** [tpgi.com/color-contrast-checker](https://www.tpgi.com/color-contrast-checker/)

---

### 5. NVDA – NonVisual Desktop Access (NV Access)
**Nível de Dificuldade:** Difícil  
**Prós:** Gratuito, código aberto e altamente configurável; reflete a realidade de milhões de usuários Windows.  
**Contras:** Curva de aprendizado altíssima (dezenas de atalhos de teclado); requer familiaridade para distinguir bugs do leitor de bugs do site.  
**Teste na prática (Exemplo Sabin):** Ao tentar agendar um hemograma no site do Sabin usando o NVDA, notou-se que o Modal de seleção de data não anunciava a mudança de contexto, deixando o usuário cego confuso sobre onde o foco estava.  

**Tipo:** Leitor de tela – Windows – gratuito e open source  
**Critérios cobertos:** Todos os critérios relacionados a tecnologias assistivas (WCAG 4.1.2, 2.1.x, 1.3.x)  
**Ideal para:** Teste funcional real de como usuários de leitores de tela experimentam a interface  

> **[NOVO - TG10/Grupo07]** Recomendado pela ABNT NBR 17225:2025 e Guia DAP para testes manuais funcionais. Cobre critérios que nenhuma ferramenta automatizada alcança.

**Passo a passo básico:**

1. Baixe em [nvaccess.org/download](https://www.nvaccess.org/download/) e instale
2. Inicie o NVDA – você ouvirá uma voz de síntese anunciar "NVDA iniciado"
3. Configure o navegador: **NVDA + Chrome** é a combinação mais comum em produção
4. Teclas essenciais:
   - `NVDA` = tecla Insert (por padrão)
   - `Tab`: navegar por elementos interativos
   - `H`: navegar por headings
   - `F`: navegar por formulários
   - `B`: navegar por botões
   - `NVDA + F7`: listar todos os elementos da página (links, headings, botões)
   - `NVDA + espaço`: alternar entre modo de navegação e modo de foco
5. Roteiro mínimo de teste:
   - [ ] O leitor anuncia o título da página ao carregar?
   - [ ] Todos os links têm texto descritivo (não "clique aqui")?
   - [ ] Imagens têm alt text significativo?
   - [ ] Formulários anunciam o label antes de cada campo?
   - [ ] Mensagens de erro são anunciadas sem mover o foco?
   - [ ] Modais prendem o foco corretamente (Tab circula dentro)?
   - [ ] Ao fechar um modal, o foco retorna ao elemento que o abriu?

**Referência:** [nvaccess.org](https://www.nvaccess.org/)

---

### 6. VoiceOver (Apple)
**Nível de Dificuldade:** Difícil  
**Prós:** Nativo em todos os Macs e iPhones; integração perfeita com Safari; simula usuários mobile de forma nativa e gestual.  
**Contras:** Curva de aprendizado alta; comportamento pode variar bastante em relação ao NVDA e JAWS.  
**Teste na prática (Exemplo Sabin):** Pelo Safari no macOS, o VoiceOver conseguiu ler o menu superior do Sabin, mas ficou preso (focus trap parcial) dentro de um iframe de chat de atendimento.  

**Tipo:** Leitor de tela nativo – macOS e iOS – gratuito  
**Critérios cobertos:** Idem ao NVDA, com foco em ecossistema Apple  
**Ideal para:** Testar em Safari (combinação mais usada por usuários reais em macOS/iOS)  

**Passo a passo básico (macOS):**

1. Ative com `Cmd + F5` ou em Preferências do Sistema → Acessibilidade → VoiceOver
2. Teclas essenciais:
   - `VO` = `Control + Option`
   - `VO + A`: leitura contínua da página
   - `VO + H`: listagem de headings
   - `VO + U`: Rotor (abre menu de navegação por tipo de elemento)
   - `Tab`: próximo elemento interativo
3. Use `VO + U` (Rotor) para inspecionar: Links, Headings, Formulários, Tabelas, Landmarks
4. Combine VoiceOver + Safari para simular o perfil mais comum de usuário real em macOS

**Referência:** [support.apple.com/guide/voiceover/welcome](https://support.apple.com/guide/voiceover/welcome/mac)

---

### 7. Teste Manual por Teclado
**Nível de Dificuldade:** Médio  
**Prós:** Indispensável para acessibilidade funcional real; não requer softwares adicionais.  
**Contras:** Demorado; exige paciência e conhecimento prático dos padrões de interação previstos.  
**Teste na prática (Exemplo Sabin):** Navegando apenas com 'Tab' no site do Sabin, foi constatado que diversos links de rodapé não possuíam indicador de foco visível (outline), ferindo gravemente a WCAG 2.4.7.  

**Tipo:** Teste manual puro – sem instalação  
**Critérios cobertos:** 2.1.1, 2.1.2, 2.4.3, 2.4.7, 2.4.11, 2.4.13  
**Ideal para:** Validar foco visível, ordem de navegação, armadilhas de teclado  

> **[NOVO - TG10/Grupo07]** Método insubstituível por ferramentas automatizadas. Cobre os critérios WCAG 2.2 **2.4.11 (Foco Não Obscurecido)** e **2.4.13 (Aparência do Foco)** que não têm cobertura automatizada satisfatória.

**Passo a passo:**

1. Desconecte o mouse (ou ignore-o completamente)
2. Recarregue a página
3. Pressione `Tab` repetidamente e verifique:
   - [ ] Um indicador de foco visível aparece em cada elemento interativo?
   - [ ] O foco segue uma ordem lógica (esquerda→direita, cima→baixo)?
   - [ ] O elemento focado fica **completamente visível** (não obscurecido por header sticky ou banner)?
   - [ ] Skip link aparece ao pressionar Tab pela primeira vez?
4. Em formulários: `Tab` entre campos, `Enter` para submeter, `Espaço` para checkboxes
5. Em modais: ao abrir, o foco vai para dentro do modal? `Tab` circula apenas dentro? `Esc` fecha?
6. Em menus dropdown: `Enter` abre, setas navegam, `Esc` fecha e retorna foco?
7. Verifique que não há **armadilhas de foco não intencionais** (elementos que capturam Tab sem possibilidade de sair)

---

### 8. JAWS (Freedom Scientific)
**Nível de Dificuldade:** Difícil  
**Prós:** Padrão ouro corporativo; recursos avançados e scripts personalizados para softwares.  
**Contras:** Muito caro; pesado no sistema.  
**Teste na prática:** (Não testado diretamente no site do Sabin por não termos acesso à licença paga no momento do estudo, usamos NVDA como principal em Windows).  

**Tipo:** Leitor de tela – Windows – comercial  
**Ideal para:** Equipes com orçamento para licença que precisam do leitor mais usado por usuários reais  

O JAWS é o leitor de tela mais utilizado por usuários com deficiência visual no mundo corporativo. Para testes de acessibilidade profissionais, é o padrão de mercado. Para uso acadêmico ou open source, o NVDA é equivalente funcional e gratuito.

**Referência:** [tecassistiva.com.br/catalogo/jaws](https://www.tecassistiva.com.br/catalogo/jaws/)

---

### 9. WebAIM Contrast Checker
**Nível de Dificuldade:** Fácil  
**Prós:** Rápido, não requer instalação, explica de forma didática as taxas de aprovação (AA e AAA).  
**Contras:** Requer que o avaliador saiba o código Hex/RGB da cor; não ajuda com gradientes.  
**Teste na prática (Exemplo Sabin):** Inserimos as cores retiradas via Inspecionar Elemento do CSS do Sabin e confirmamos que a cor do botão primário passava nos critérios AA.  

**Tipo:** Ferramenta web online  
**Ideal para:** Verificação rápida por código hex/RGB sem instalar o CCA  

Digite os códigos hex das cores de texto e fundo para obter a razão de contraste e o resultado de conformidade para os níveis AA e AAA. Não usa conta-gotas – para isso, use o Colour Contrast Analyser.

**Referência:** [webaim.org/resources/contrastchecker](https://webaim.org/resources/contrastchecker/)

---

### 10. ACHECKS
**Nível de Dificuldade:** Fácil  
**Prós:** Não requer instalação.  
**Contras:** Interface legada; menos detalhado e menos atualizado com WCAG 2.2 que o axe.  
**Teste na prática:** Avaliação preliminar apontou erros similares aos do WAVE, mas sem as comodidades de integração do axe.  

**Tipo:** Ferramenta web online – automatizado  
**Ideal para:** Verificação rápida sem instalar extensão  
**Referência:** [achecks.org](https://www.achecks.org/)

---

### 11. Framework de Testes Android (Google)
**Nível de Dificuldade:** Difícil  
**Prós:** Nativo para pipelines Android; testa tamanhos de touch targets e labels.  
**Contras:** Específico apenas para Android nativo (Java/Kotlin), inútil para Web pura.  
**Teste na prática:** (Não se aplica ao fluxo principal do site responsivo avaliado).  

**Tipo:** Biblioteca Java/Kotlin – automatizado  
**Ideal para:** Equipes com aplicações Android nativas  
**Referência:** [github.com/google/Accessibility-Test-Framework-for-Android](https://github.com/google/Accessibility-Test-Framework-for-Android)

---

### 12. DynoMapper – Sitemap Generator
**Nível de Dificuldade:** Médio  
**Prós:** Útil para ver a estrutura macro do site e títulos repetidos.  
**Contras:** Foco indireto em acessibilidade; serviço pago.  
**Teste na prática:** O escopo do projeto focou mais nas páginas já mapeadas manualmente.  

**Tipo:** Ferramenta online  
**Ideal para:** Mapear estrutura de navegação e identificar páginas sem título único (WCAG 2.4.2)  
**Referência:** [dynomapper.com](https://dynomapper.com/)

---


---

### 13. Accessibility Insights for Web (Microsoft)
**Tipo:** Extensão de navegador (Chrome/Edge) – Híbrido (Automatizado + Guiado)  
**Critérios cobertos:** Todos os WCAG 2.1 AA através do teste guiado; automatizado cobre ~30%.  
**Ideal para:** Desenvolvedores e QA que buscam conformidade rigorosa.  
**Nível de Dificuldade:** Médio  
**Prós:** A funcionalidade "FastPass" é extremamente rápida; a funcionalidade "Assessment" oferece instruções passo a passo brilhantes de como testar manualmente cada critério WCAG, incluindo como testar por teclado.  
**Contras:** A versão completa do Assessment é longa e pode desmotivar iniciantes.  
**Teste na prática (Exemplo Sabin):** O uso da aba *Tab Stops* no FastPass evidenciou um caminho de foco (focus order) confuso na home, desenhando flechas visuais desordenadas sobre a tela do Sabin.  

**Passo a passo básico:**
1. Instale a extensão no Edge ou Chrome (Web Store).
2. Abra a página desejada e clique no ícone do plugin.
3. Escolha **FastPass** para testes automatizados instantâneos.
4. Ligue o toggle **Tab Stops** e navegue usando a tecla Tab para traçar o mapa visual do foco.

---

### 14. Stark
**Tipo:** Plugin para editores de design (Figma, Sketch) e extensões de navegador  
**Critérios cobertos:** Contraste, simulação de daltonismo, tipografia e foco  
**Ideal para:** Designers (shift-left accessibility, resolvendo problemas no protótipo).  
**Nível de Dificuldade:** Fácil  
**Prós:** Resolve a acessibilidade visual na origem (antes do código); simulador de daltonismo excelente; anotações automáticas de hierarquia.  
**Contras:** Muitos recursos avançados exigem a conta Pro (paga).  
**Teste na prática (Exemplo Sabin):** Usado para reprojetar a tela de agendamento em nossos protótipos Figma, garantindo que as novas cores sugeridas para os botões tivessem contraste superior a 4.5:1, diferente da versão original.  

**Passo a passo básico:**
1. Instale o plugin Stark no Figma.
2. Selecione dois layers sobrepostos (ex: texto e retângulo de fundo).
3. Abra a opção **Contrast Checker** no menu do Stark.
4. Use o **Vision Simulator** para prever como a tela é vista por usuários com daltonismo (Protanopia ou Deuteranopia).

## Matriz de Cobertura por Critério WCAG 2.2


**Legenda:** `Sim` = cobre bem · `Parcial` = cobertura parcial · `Não` = não cobre · `[novo]` = critério exclusivo do WCAG 2.2

| Critério WCAG 2.2 | axe | Lighthouse | WAVE | CCA | NVDA | Teclado | AccInsights | Stark |
|---|---|---|---|---|---|---|---|---|
| 1.1.1 Alt text | Sim | Sim | Sim | Não | Sim | Não | Parcial (Guiado) | Não |
| 1.4.3 Contraste texto | Sim | Sim | Sim | Sim | Não | Não | Sim | Sim |
| 1.4.11 Contraste componentes | Parcial | Parcial | Parcial | Sim | Não | Não | Sim | Sim |
| 2.1.1 Teclado | Não | Não | Não | Não | Sim | Sim | Parcial (Guiado) | Não |
| 2.4.1 Skip links | Sim | Parcial | Sim | Não | Sim | Sim | Parcial (Guiado) | Não |
| 2.4.7 Foco visível | Parcial | Parcial | Não | Não | Não | Sim | Parcial (Visual) | Sim |
| **2.4.11 Foco não obscurecido** `[novo]` | Não | Não | Não | Não | Não | Sim | Parcial | Não |
| **2.4.13 Aparência do foco** `[novo]` | Não | Não | Não | Sim | Não | Sim | Parcial | Sim |
| **2.5.7 Movimentos arrastar** `[novo]` | Não | Não | Não | Não | Não | Sim | Não | Não |
| **2.5.8 Tamanho alvo 24px** `[novo]` | Parcial | Não | Não | Não | Não | Não | Parcial | Sim |
| 3.1.1 Idioma da página | Sim | Sim | Sim | Não | Não | Não | Sim | Não |
| 3.3.1 Identificação de erro | Parcial | Não | Parcial | Não | Sim | Não | Parcial (Guiado) | Não |
| **3.3.7 Entrada redundante** `[novo]` | Não | Não | Não | Não | Não | Não | Não | Não |
| **3.3.8 Autenticação acessível** `[novo]` | Não | Não | Não | Não | Não | Não | Não | Não |
| 4.1.2 Nome, Função, Valor | Sim | Sim | Parcial | Não | Sim | Não | Sim | Não |

**Conclusão:** Os critérios novos do WCAG 2.2 (marcados com `[novo]`) **não têm cobertura automatizada**. O teste manual por teclado e com leitor de tela é obrigatório para conformidade com WCAG 2.2 e ABNT NBR 17225:2025.

---

## Referências Bibliográficas

> 1. W3C. Web Content Accessibility Guidelines (WCAG) 2.2. World Wide Web Consortium, outubro 2023. Disponível em: [https://www.w3.org/TR/WCAG22/](https://www.w3.org/TR/WCAG22/). Acesso em: jun. 2026.

> 2. ABNT. NBR 17225:2025 – Acessibilidade em ambientes virtuais – Requisitos e Recomendações. Associação Brasileira de Normas Técnicas, 2025.

> 3. GRUPO 7 – IHC 2026.1. TG10 – Estudo Aprofundado da WCAG 2.2. Universidade de Brasília, junho de 2026.

> 4. W3C WAI. Understanding WCAG 2.2. Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/](https://www.w3.org/WAI/WCAG22/Understanding/). Acesso em: jun. 2026.

> 5. DEQUE SYSTEMS. Axe Core Accessibility Rules. Disponível em: [https://dequeuniversity.com/rules/axe/](https://dequeuniversity.com/rules/axe/). Acesso em: jun. 2026.

## Bibliografia

> DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R. Guia de Boas Práticas para Acessibilidade Digital. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf). Acesso em: jun. 2026.
