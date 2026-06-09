# Heurísticas de Usabilidade

> **Base bibliográfica principal:**
> - NIELSEN, Jakob; MOLICH, Rolf. Heuristic Evaluation of User Interfaces. *CHI '90 Proceedings*, 1990.
> - NIELSEN, Jakob. 10 Usability Heuristics for User Interface Design. Nielsen Norman Group, 1994 (revisado 2020). Disponível em: https://www.nngroup.com/articles/ten-usability-heuristics/
> - SHNEIDERMAN, Ben et al. *Designing the User Interface*. 6ª ed. Pearson, 2016.
>
> A avaliação heurística é um método de inspeção de usabilidade em que especialistas examinam uma interface e julgam sua conformidade com princípios de usabilidade reconhecidos ("heurísticas"). É mais rápido e barato que testes com usuários, mas complementar — não substituto.

---

## O que é Avaliação Heurística?

Introduzida por Nielsen e Molich (1990), a avaliação heurística envolve entre **3 e 5 avaliadores** inspecionando uma interface de forma independente, registrando violações heurísticas com severidade. Os resultados são consolidados e priorizados.

**Por que 3–5 avaliadores?** Um único avaliador encontra ~35% dos problemas. Com 5 avaliadores independentes, a cobertura sobe para ~75%. Mais de 5 tem retorno decrescente. <a id="HEU_INTRO" href="#RH1">[1]</a>

---

## Processo de Avaliação Heurística

### Fase 1 – Preparação
- [ ] Definir o <b>escopo</b>: qual fluxo ou parte da interface será avaliado (ex: "fluxo de cadastro", "tela de checkout").
- [ ] Selecionar <b>3 a 5 avaliadores</b> independentes com conhecimento em usabilidade. Avaliadores não precisam ser usuários finais do produto.
- [ ] Fornecer a cada avaliador um <b>briefing</b>: contexto do produto, perfil de usuário-alvo, tarefas representativas a percorrer.
- [ ] Definir o <b>protocolo de registro</b>: planilha ou ferramenta compartilhada com campos para: problema encontrado, localização na interface, heurística violada, severidade.
- [ ] Garantir que os avaliadores realizem a inspeção de forma <b>independente</b>, sem discutir entre si antes da consolidação.

### Fase 2 – Inspeção Individual
- [ ] Cada avaliador percorre a interface pelo menos <b>duas vezes</b>: na primeira, entende o fluxo geral; na segunda, inspeciona em detalhe buscando violações. <a id="HEU1" href="#RH1">[1]</a>
- [ ] Registrar cada problema com:
  - **Descrição:** o que está errado e onde
  - **Heurística violada:** qual das 10 heurísticas (ou conjunto delas)
  - **Severidade:** escala 0–4 (ver tabela de severidade abaixo)
  - **Evidência:** captura de tela ou referência ao passo do fluxo
- [ ] Um mesmo problema pode violar múltiplas heurísticas — registrar todas.
- [ ] Registrar também <b>problemas positivos</b> (o que funciona bem): útil para preservar durante redesign.

### Fase 3 – Consolidação
- [ ] Reunir todos os avaliadores para <b>consolidar listas individualmente</b> em uma lista única, eliminando duplicatas.
- [ ] Avaliadores discutem e chegam a <b>consenso sobre severidade</b> de cada item consolidado.
- [ ] Priorizar por severidade e frequência (quantos avaliadores identificaram o mesmo problema).

### Fase 4 – Reporte e Ação
- [ ] Cada problema deve ter uma <b>recomendação de correção</b> associada.
- [ ] Organizar o relatório por severidade, não por heurística.
- [ ] Apresentar resultados para a equipe de design/desenvolvimento com <b>evidências visuais</b>.
- [ ] Integrar problemas críticos e sérios como <b>itens de backlog</b> com critério de aceitação.

---

## Escala de Severidade (Nielsen, 1994)

| Nível | Severidade | Descrição | Ação |
|---|---|---|---|
| **0** | Não é problema | O avaliador não concorda que seja um problema de usabilidade | Ignorar |
| **1** | Cosmético | Problema menor, só precisa ser corrigido se houver tempo | Backlog baixa prioridade |
| **2** | Minor | Problema que causa frustração menor; usuário consegue prosseguir | Backlog média prioridade |
| **3** | Major | Problema que impede ou atrapalha significativamente a conclusão de tarefas | Alta prioridade |
| **4** | Catastrófico | Problema que impede o uso do produto; deve ser corrigido antes de publicar | Bloqueador de release |

---

## As 10 Heurísticas de Nielsen (1994, revisadas 2020)

### H1 – Visibilidade do Status do Sistema
*"O design sempre deve manter os usuários informados sobre o que está acontecendo, através de feedback apropriado dentro de um tempo razoável."* <a id="H1" href="#RH1">[1]</a>

**Checklist:**
- [ ] O sistema exibe <b>indicador de carregamento</b> para operações que demoram mais de 1 segundo.
- [ ] <b>Confirmações de ação</b> são exibidas (ex: "Item adicionado ao carrinho", "Formulário enviado com sucesso").
- [ ] O usuário sabe em que <b>etapa de um fluxo multi-passo</b> se encontra (ex: "Passo 2 de 4").
- [ ] <b>Estado atual</b> de elementos interativos é visível (ex: item selecionado, filtro ativo, aba em foco).
- [ ] Progresso de uploads ou downloads é exibido com <b>porcentagem ou barra de progresso</b>.

---

### H2 – Correspondência entre Sistema e Mundo Real
*"O design deve falar a língua do usuário. Use palavras, frases e conceitos familiares ao usuário, não jargão interno do sistema."* <a id="H2" href="#RH1">[1]</a>

**Checklist:**
- [ ] Rótulos, botões e mensagens usam <b>vocabulário familiar ao usuário-alvo</b>, não termos técnicos ou internos.
- [ ] A <b>ordem das informações</b> segue convenções do mundo real (ex: data antes de hora, nome antes de sobrenome).
- [ ] Metáforas visuais (ícones, imagens) têm <b>correspondência clara</b> com o conceito que representam (ex: ícone de carrinho para compras).
- [ ] Valores de dados são apresentados em <b>unidades e formatos familiares</b> ao contexto local (ex: R$ não $, DD/MM/AAAA não MM/DD/YYYY).
- [ ] O conteúdo usa <b>Linguagem Simples (Plain Language)</b>: frases diretas, ativas, sem jargão.

---

### H3 – Controle e Liberdade do Usuário
*"Os usuários frequentemente escolhem funções do sistema por engano e precisam de uma 'saída de emergência' claramente marcada para sair do estado indesejado."* <a id="H3" href="#RH1">[1]</a>

**Checklist:**
- [ ] Todas as ações críticas (excluir, enviar, publicar) têm um <b>passo de confirmação</b> ou são reversíveis.
- [ ] Existe funcionalidade de <b>Desfazer (Undo)</b> para ações que alteram dados.
- [ ] Fluxos multi-etapa permitem <b>Voltar</b> para etapas anteriores sem perda de dados já preenchidos.
- [ ] O usuário pode <b>cancelar operações em andamento</b> (ex: upload, processo longo).
- [ ] Modais e overlays têm <b>forma clara de fechar</b> (botão X, tecla Esc, clique fora).
- [ ] O usuário pode <b>sair de um fluxo</b> a qualquer momento sem ser forçado a completá-lo.

---

### H4 – Consistência e Padrões
*"Os usuários não deveriam ter que se perguntar se palavras, situações ou ações diferentes significam a mesma coisa."* <a id="H4" href="#RH1">[1]</a>

**Checklist:**
- [ ] O mesmo elemento funcional usa o <b>mesmo nome, ícone e posição</b> em todas as telas.
- [ ] <b>Padrões de plataforma</b> são respeitados (ex: ícone de hambúrguer para menu mobile, padrão de navegação do SO).
- [ ] Botões do mesmo tipo (primário, secundário, destrutivo) têm <b>aparência visual consistente</b> em todo o produto.
- [ ] A <b>terminologia é uniforme</b>: o mesmo conceito não tem nomes diferentes em partes distintas do produto.
- [ ] Fluxos semelhantes (ex: criar conta, criar projeto, criar evento) seguem o <b>mesmo padrão de passos</b>.

---

### H5 – Prevenção de Erros
*"Ainda melhor que boas mensagens de erro é um design cuidadoso que previne problemas em primeiro lugar."* <a id="H5" href="#RH1">[1]</a>

**Checklist:**
- [ ] Campos de formulário têm <b>validação inline</b> (antes do envio) para erros previsíveis (formato de e-mail, CPF).
- [ ] Ações destrutivas irreversíveis (deletar, arquivar) pedem <b>confirmação explícita</b>, preferencialmente com digitação do nome do item.
- [ ] <b>Restrições são aplicadas na entrada</b>: campos de data não aceitam datas inválidas; campos numéricos não aceitam letras.
- [ ] O sistema <b>previne estados inválidos</b>: botão de submissão desabilitado enquanto formulário está incompleto.
- [ ] Mensagens de erro aparecem <b>próximas ao campo problemático</b>, não só no topo da página.

---

### H6 – Reconhecimento em vez de Lembrança
*"Minimize a carga de memória do usuário tornando visíveis os elementos, ações e opções."* <a id="H6" href="#RH1">[1]</a>

**Checklist:**
- [ ] O usuário não precisa memorizar informações de uma tela para outra: <b>contexto relevante é mantido visível</b> (ex: resumo do pedido durante checkout).
- [ ] <b>Histórico de pesquisa e ações recentes</b> é exibido para facilitar retomada de tarefas.
- [ ] <b>Dicas e rótulos</b> aparecem dentro ou próximos a campos de entrada, sem depender de tooltip hover.
- [ ] O <b>caminho de navegação (breadcrumb)</b> indica onde o usuário está na hierarquia do produto.
- [ ] Opções e comandos disponíveis são <b>visíveis</b> sem exigir que o usuário memorize teclas de atalho.

---

### H7 – Flexibilidade e Eficiência de Uso
*"Atalhos — ocultos para o usuário iniciante — podem acelerar a interação para o usuário especialista."* <a id="H7" href="#RH1">[1]</a>

**Checklist:**
- [ ] <b>Atalhos de teclado</b> estão disponíveis para ações frequentes (ex: `Ctrl+S`, `/` para busca).
- [ ] Usuários experientes podem <b>personalizar ou configurar</b> a interface (ex: colunas de tabela, ordem de widgets).
- [ ] <b>Sugestões e autocompletar</b> reduzem a entrada manual em campos frequentes.
- [ ] Ações comuns estão acessíveis com o <b>menor número possível de cliques/toques</b>.
- [ ] O produto oferece <b>múltiplos caminhos</b> para realizar a mesma tarefa (ex: menu + atalho + botão direto).

---

### H8 – Estética e Design Minimalista
*"As interfaces não devem conter informações irrelevantes ou raramente necessárias. Toda unidade extra de informação compete com as unidades relevantes."* <a id="H8" href="#RH1">[1]</a>

**Checklist:**
- [ ] Cada tela exibe apenas as <b>informações necessárias</b> para a tarefa atual; informações secundárias são progressivamente reveladas.
- [ ] Elementos decorativos <b>não competem visualmente</b> com o conteúdo principal.
- [ ] A hierarquia visual guia o olhar: <b>o mais importante é o mais proeminente</b>.
- [ ] Texto de interface é <b>conciso</b>: sem textos introdutórios longos, instruções óbvias ou mensagens redundantes.
- [ ] Cores, tipografia e espaçamento são usados com <b>propósito funcional</b>, não apenas ornamental.

---

### H9 – Ajuda ao Usuário para Reconhecer, Diagnosticar e Recuperar Erros
*"Mensagens de erro devem ser expressas em linguagem simples (sem códigos), indicar precisamente o problema e sugerir uma solução."* <a id="H9" href="#RH1">[1]</a>

**Checklist:**
- [ ] Mensagens de erro são escritas em <b>linguagem do usuário</b>, não em códigos de sistema (ex: não "Erro 403", mas "Você não tem permissão para acessar esta página").
- [ ] A mensagem descreve <b>o que deu errado e onde</b> (campo específico, etapa do processo).
- [ ] A mensagem sugere <b>como corrigir</b> o problema (ex: "O CEP deve ter 8 dígitos. Ex: 70040-010").
- [ ] Erros de sistema (timeout, conexão) explicam a <b>causa e oferecem ação de recuperação</b> (ex: botão "Tentar novamente").
- [ ] <b>Mensagens de sucesso</b> também são claras sobre o que foi concluído e o próximo passo.

---

### H10 – Ajuda e Documentação
*"Mesmo que seja melhor que o sistema possa ser usado sem documentação, pode ser necessário fornecer ajuda."* <a id="H10" href="#RH1">[1]</a>

**Checklist:**
- [ ] A documentação de ajuda é <b>facilmente localizável</b> (acesso por menu, ícone `?`, campo de busca).
- [ ] O conteúdo de ajuda é <b>focado em tarefas</b>: "como fazer X", não apenas "o que é X".
- [ ] A ajuda contextual aparece <b>no momento em que o usuário precisa</b> (ex: tooltip em campo complexo, link "Saiba mais" próximo ao termo).
- [ ] Documentação usa <b>passos numerados, imagens e exemplos</b> quando aplicável.
- [ ] A documentação é <b>mantida atualizada</b> a cada versão relevante do produto.

---

## Heurísticas Complementares

### Regras de Ouro de Shneiderman (8 Golden Rules)
Alternativa às heurísticas de Nielsen, mais orientada a sistemas interativos: <a id="SHN" href="#RH2">[2]</a>

- [ ] **Consistência:** mesmos termos, sequências e comandos em situações similares.
- [ ] **Atalhos para usuários experientes:** teclas de atalho, abreviações, macros.
- [ ] **Feedback informativo:** cada ação do usuário gera resposta do sistema.
- [ ] **Diálogos que indicam conclusão:** sequências organizadas em início, meio e fim com feedback de conclusão.
- [ ] **Prevenção e tratamento simples de erros:** design que previne erros graves; recuperação fácil dos erros menores.
- [ ] **Reversão fácil de ações:** encorajar exploração pelo usuário, pois ações são reversíveis.
- [ ] **Controle interno percebido:** usuário inicia ações, não reage a elas.
- [ ] **Redução da carga de memória de curto prazo:** interfaces simples, consolidação de informação, instruções no contexto.

---

## Checklist de Aplicação Rápida (Quick Wins)

Use este checklist como primeira passagem antes de uma avaliação completa:

- [ ] Existe feedback visual para toda ação que demora mais de 1s? (H1)
- [ ] Todos os rótulos e mensagens estão em linguagem do usuário-alvo? (H2)
- [ ] É possível desfazer a última ação realizada? (H3)
- [ ] Botões e ícones têm o mesmo significado em todas as telas? (H4)
- [ ] Formulários validam entrada antes do envio? (H5)
- [ ] O usuário sabe onde está na navegação sem precisar memorizar? (H6)
- [ ] Ações frequentes podem ser feitas com poucos cliques? (H7)
- [ ] A tela apresenta apenas o necessário para a tarefa atual? (H8)
- [ ] Mensagens de erro dizem o que deu errado E como corrigir? (H9)
- [ ] É possível encontrar ajuda contextual sem sair da tarefa? (H10)

---

## Referências Bibliográficas

> <a id="RH1" href="#H1">1.</a> NIELSEN, Jakob. *10 Usability Heuristics for User Interface Design*. Nielsen Norman Group, 1994 (revisado 2020). Disponível em: [https://www.nngroup.com/articles/ten-usability-heuristics/](https://www.nngroup.com/articles/ten-usability-heuristics/). Acesso em: jun. 2026.

> <a id="RH2" href="#SHN">2.</a> SHNEIDERMAN, Ben; PLAISANT, Catherine; COHEN, Maxine; JACOBS, Steven; ELMQVIST, Niklas. *Designing the User Interface: Strategies for Effective Human-Computer Interaction*. 6ª ed. Pearson, 2016.

> <a id="RH3" href="#H1">3.</a> NIELSEN, Jakob; MOLICH, Rolf. Heuristic Evaluation of User Interfaces. In: *CHI '90: Proceedings of the SIGCHI Conference on Human Factors in Computing Systems*. New York: ACM, 1990. p. 249–256. DOI: 10.1145/97243.97281.

## Bibliografia

> NIELSEN, Jakob. *Usability Engineering*. Academic Press, 1993.

> NORMAN, Don. *The Design of Everyday Things*. Revised and expanded edition. Basic Books, 2013.

> ROGERS, Yvonne; SHARP, Helen; PREECE, Jenny. *Interaction Design: Beyond Human–Computer Interaction*. 5ª ed. Wiley, 2019.

> KALBACH, Jim. *Mapping Experiences: A Complete Guide to Customer Alignment through Journeys, Blueprints, and Diagrams*. 2ª ed. O'Reilly Media, 2020.

> DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R. Guia de Boas Práticas para Acessibilidade Digital. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf). Acesso em: jun. 2026.
