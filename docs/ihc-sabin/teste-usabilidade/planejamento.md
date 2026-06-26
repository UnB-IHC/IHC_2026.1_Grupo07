# Planejamento do Teste de Usabilidade — Site Sabin

> **Site avaliado:** [sabin.com.br](https://www.sabin.com.br)
> **Método:** Think Aloud (Protocolo de Verbalização Simultânea)
> **Data de planejamento:** Junho/2026
> **Responsável:** Equipe IHC 2026.1 Grupo 07

---

## 1. Objetivo do Teste

Avaliar a usabilidade do site Sabin Diagnóstico e Saúde sob a perspectiva de usuários reais, identificando problemas que dificultam três tarefas centrais e não-autenticadas do site: agendar um exame, verificar instruções de preparo e localizar uma unidade. O teste busca:

1. Mensurar a **taxa de conclusão** (task completion rate) das tarefas definidas.
2. Identificar **pontos de fricção** e erros cometidos espontaneamente pelos participantes.
3. Coletar **tempo médio por tarefa** (time-on-task) como indicador de eficiência.
4. Avaliar a **satisfação subjetiva** dos participantes (escala SUS).

---

## 2. Perfil dos Participantes

### Critérios de inclusão

| Critério | Especificação |
|---|---|
| Faixa etária | 18 a 65 anos |
| Escolaridade | Ensino médio completo ou superior |
| Acesso à internet | Uso frequente (diário ou semanal) de sites e aplicativos |
| Relação com o serviço | Realiza ou já realizou exames laboratoriais (próprio ou familiar) |
| Familiaridade com Sabin | Conhece o nome, mas não necessariamente usa o site regularmente |

### Critérios de exclusão

- Funcionários ou estagiários do Sabin ou de laboratório concorrente.
- Profissionais de TI ou UX/design com experiência em testes de usabilidade (viés de especialista).

### Personas-alvo (referência para recrutamento)

| # | Perfil | Idade | Descrição |
|---|---|---|---|
| P1 | Adulto que acompanha familiar idoso | 38–50 | Agenda exames para pais; usa smartphone com frequência; não é nativo digital |
| P2 | Jovem adulto, primeira vez no Sabin | 22–30 | Recebeu indicação médica; busca resultado e preparo online |
| P3 | Usuário com restrição visual leve | 45–65 | Usa óculos; zoom do navegador em 125%; não usa leitor de tela |
| P4 | Usuário frequente de plano de saúde | 30–45 | Busca unidades cobertas pelo convênio; acostumado a portais de saúde |
| P5 | Usuário com baixa literacia digital | 55–70 | Usa internet principalmente para WhatsApp e YouTube; primeiro contato com site de laboratório |

### Quantidade de participantes

**3 participantes (3 entrevistados)**, todos estudantes de Engenharia de Software da faculdade da equipe avaliadora, recrutados conforme os critérios de inclusão/exclusão acima. Cada um dos 3 participantes realiza **as mesmas 3 tarefas**, na mesma ordem — não há divisão de tarefas entre participantes diferentes.

> **Observação metodológica:** com apenas 3 participantes e uma amostra homogênea (mesma faculdade, mesmo curso), a rodada é menor e menos diversa que o recomendado por Nielsen (1993) para saturação de problemas (~5 avaliadores variados). Os resultados devem ser tratados como indicativos, não conclusivos sobre a usabilidade geral do site, e relatados como tal no seminário final.

---

## 3. Tarefas a Serem Executadas

Cada um dos 3 participantes realiza **as 3 tarefas abaixo, na mesma ordem**, para permitir comparação direta dos resultados entre sessões. Todas as tarefas têm dois critérios de seleção em comum:

1. **Envolvem alguma dificuldade real para o usuário** — T1 está associada a um problema Catastrófico já catalogado na avaliação heurística (ver `avaliacao-heuristica/index.md`); T2 introduz uma complicação clínica real (restrição de idade para vacina) que testa se o site comunica isso adequadamente; T3 testa se a listagem de exames dá contexto mínimo sem exigir clique extra (achado HE-12/HE-13).
2. **Não exigem login** — nenhuma tarefa depende de credenciais ou de área autenticada do site (portal de laudos), para que qualquer um dos 3 participantes consiga executá-la até o fim sem barreira de acesso.
3. **Ocorrem em páginas diferentes do site** — cada tarefa usa um exame/serviço e fluxo distinto (hemograma, vacina, check-up), evitando que o aprendizado de uma tarefa facilite artificialmente a seguinte.

| # | Tarefa | O que o participante deve fazer | Critério de sucesso | Heurísticas relacionadas |
|---|---|---|---|---|
| T1 | "Agende um exame de hemograma completo na unidade Ceilândia Centro." | Partindo da homepage do Sabin, sem ajuda do avaliador, o participante deve localizar o exame "Hemograma Completo", iniciar o fluxo de agendamento e selecionar a unidade "Ceilândia Centro", avançando o quanto conseguir no processo (não precisa concluir o agendamento real, ex.: pagamento ou confirmação final). | Participante chega a uma tela real do fluxo de agendamento com o exame "Hemograma Completo" e a unidade "Ceilândia Centro" corretamente selecionados — falha notável é não localizar o exame, não localizar a unidade ou cair em erro 404 | H3, H5, H6, H7, H9 |
| T2 | "Você quer agendar uma vacina de febre amarela no site, para o seu filho de 9 meses, na unidade Águas Claras." | Partindo da homepage (reiniciada), o participante deve localizar a vacina "Febre Amarela", iniciar o agendamento informando um dependente de 9 meses e selecionar a unidade "Águas Claras", avançando o quanto conseguir. *Observação para o avaliador:* a vacina de febre amarela tem restrição de idade mínima (geralmente 9 meses) — observar se o site comunica essa restrição de forma clara ou se deixa o usuário confuso/sem aviso. | Participante chega a uma tela real do fluxo de agendamento com a vacina "Febre Amarela" e a unidade "Águas Claras" selecionados — falha notável é não localizar a vacina, não conseguir informar o dependente/idade, ou não localizar a unidade | H2, H3, H5, H9 |
| T3 | "Você quer ver as orientações de preparo para um agendamento de check-up executivo." | Partindo da homepage (reiniciada), o participante deve localizar a página do "Check-up Executivo" e identificar as orientações de preparo, lendo em voz alta o que encontrar. | Participante chega à página correta do check-up executivo e indica verbalmente as orientações de preparo encontradas — falha notável é não localizar a página ou informar dado incorreto/inventado | H6, H7, H1 |

### Storyboards — Hipóteses de fricção nos 3 fluxos (antes do teste)

A equipe mapeou, para cada uma das 3 tarefas, o fluxo *esperado* de atrito que um usuário enfrentaria ao tentar concluí-la sozinho. Estes storyboards são **hipóteses a serem confirmadas ou refutadas** pelas 3 sessões reais de Think Aloud — não são dado coletado.

#### Storyboard T1 — Agendamento de hemograma

![Storyboard do fluxo de agendamento de hemograma completo na unidade Ceilândia Centro, mostrando 6 etapas de fricção: início do agendamento com banners confusos, busca de exame lenta, dificuldade para encontrar a unidade, calendário lento com erro, formulário de confirmação exaustivo e cansaço ao final do processo.](imagens/storyboard-agendamento-hemograma.png)

| Etapa do storyboard | Hipótese de problema | Heurística relacionada |
|---|---|---|
| 1. Início do Agendamento | Homepage com excesso de banners/anúncios; CTA de agendamento pouco evidente | H8 (Estética e design minimalista), H6 (Reconhecimento em vez de memorização) |
| 2. Busca de Exame Complexa | Busca lenta; lista de exames sugeridos desorganizada ou vazia | H1 (Visibilidade do status do sistema), H7 (Flexibilidade e eficiência de uso) |
| 3. Unidade Difícil de Encontrar | Menu de seleção de unidade extenso, sem organização geográfica clara | H6 (Reconhecimento em vez de memorização), H8 |
| 4. Calendário Lento e Indisponível | Calendário demora a carregar; erro ao tentar selecionar data | H1, H9 (Ajuda a reconhecer e corrigir erros) |
| 5. Confirmação e Formulários Exaustivos | Cadastro longo, sem validação imediata dos campos | H5 (Prevenção de erros), H9 |
| 6. Fim do Processo: Cansaço | Mais de 10 minutos de fricção até a confirmação final | H7 — eficiência de uso comprometida |

---

#### Storyboard T2 — Agendamento de vacina de febre amarela (dependente, Águas Claras)

![Storyboard do fluxo de agendamento de vacina de febre amarela para um dependente de 9 meses na unidade Águas Claras, mostrando 6 etapas de fricção: dificuldade no login e cadastro de dependente, busca de vacina ambígua, alerta de restrição de idade incomunicado, localização de unidade ineficiente, calendário de vacinação instável e formulário de confirmação exaustivo.](imagens/storyboard-vacina-febre-amarela.png)

| Etapa do storyboard | Hipótese de problema | Heurística relacionada |
|---|---|---|
| 1. Dificuldade no Login e Cadastro de Dependente | Portal exige login complexo e processo obscuro para adicionar um dependente menor de idade | H2 (Correspondência com o mundo real), H9 |
| 2. Busca de Vacina Ambígua | Busca por "Febre Amarela" retorna termos técnicos e múltiplas opções genéricas, sem indicar qual é a vacina pediátrica correta para um bebê de 9 meses | H2, H6 (Reconhecimento em vez de memorização) |
| 3. Alerta de Restrição de Idade Incomunicado | Ícone de alerta genérico ao selecionar a vacina, com informação vaga sobre restrição de idade, sem confirmar se o bebê de 9 meses é elegível | H1 (Visibilidade do status do sistema), H9 (Ajuda a reconhecer e corrigir erros) |
| 4. Localização de Unidade Águas Claras Ineficiente | Menu de seleção de unidade desorganizado, tornando difícil e demorado encontrar "Águas Claras" | H6, H8 (Estética e design minimalista) |
| 5. Calendário de Vacinação Instável | Calendário de disponibilidade da unidade instável, sem horários claros para a vacina pediátrica | H1, H9 |
| 6. Formulário de Confirmação Exaustivo para Dependente | Etapa final exige muitos dados do bebê, sem validação dos campos em tempo real | H5 (Prevenção de erros), H9 |

> Este storyboard tem um valor especial: a tarefa real **não exige login** (critério de seleção das 3 tarefas), mas a hipótese prevê que o site *force* um login/cadastro de dependente mesmo assim. Se isso for confirmado nas sessões reais, é em si um achado crítico — significa que o fluxo de vacina pediátrica viola o requisito de acesso sem autenticação que as outras áreas do site cumprem.

---

#### Storyboard T3 — Preparo para check-up executivo

![Storyboard do fluxo de busca por orientações de preparo para um check-up executivo, mostrando 6 etapas de fricção: orientações ocultas no perfil do usuário, busca de conteúdo ineficiente, navegação por menus complexos, falta de informação específica, chatbot insatisfatório e desistência final.](imagens/storyboard-preparo-checkup-executivo.png)

| Etapa do storyboard | Hipótese de problema | Heurística relacionada |
|---|---|---|
| 1. Localização de Orientações Oculta | Perfil do usuário não mostra links diretos para orientações de preparo do exame já agendado, forçando busca manual | H6, H7 (Flexibilidade e eficiência de uso) |
| 2. Busca de Conteúdo Ineficiente | Pesquisa por "preparo check-up executivo" falha em retornar link direto, gerando resultados genéricos e links quebrados | H1, H7 |
| 3. Navegação de Menus Complexos | Usuário desiste da busca e tenta os menus, mas a estrutura é complexa e as orientações específicas ficam escondidas em subcategorias | H6, H8 |
| 4. Falta de Informação Específica | Página de preparo encontrada é genérica para todos os tipos de check-up, sem detalhes do "executivo" nem opção de download em PDF | H2, H6 |
| 5. Chatbot Insatisfatório | Chatbot não consegue fornecer as informações específicas do check-up executivo e sugere ligar para a central de atendimento | H9, H10 (Ajuda e documentação) |
| 6. Fim do Processo: Desistência | Usuário desiste após perder tempo e não conseguir as informações necessárias | H7 — eficiência de uso comprometida |

> Ao final das 3 sessões, comparar estas hipóteses com os resultados reais em [Resultados do Teste de Usabilidade](resultados.md), seção 5 (Cruzamento com Avaliação Heurística).

---

## 4. Métricas Coletadas

| Métrica | Tipo | Instrumento |
|---|---|---|
| **Taxa de conclusão de tarefa** | Quantitativa | Planilha de observação (0 = não concluiu / 0,5 = concluiu com ajuda / 1 = concluiu sem ajuda) |
| **Tempo por tarefa (time-on-task)** | Quantitativa | Cronômetro (início: leitura completa da tarefa; fim: declaração do participante ou timeout de 5min) |
| **Número de erros por tarefa** | Quantitativa | Contagem de cliques errados, páginas erradas acessadas, voltas ao início |
| **Verbalizações espontâneas** | Qualitativa | Gravação de áudio + transcrição seletiva |
| **Satisfação subjetiva (SUS)** | Quantitativa | Questionário SUS (System Usability Scale) — 10 itens, aplicado pós-teste |
| **Observações do avaliador** | Qualitativa | Notas livres durante a sessão |

### Timeout por tarefa

Caso o participante não conclua a tarefa em **5 minutos**, o avaliador interrompe e registra como não concluída (com observação da razão).

---

## 5. Ambiente de Teste

| Item | Especificação |
|---|---|
| **Modalidade** | Presencial (preferencial) ou remoto via Google Meet com compartilhamento de tela |
| **Dispositivo** | Notebook do participante ou notebook do avaliador em modo de convidado |
| **Navegador** | Google Chrome atualizado (versão estável), sem extensões |
| **Resolução** | 1366×768 (simulando uso médio) |
| **Conexão** | Wi-Fi estável — mínimo 10 Mbps |
| **Gravação** | Tela + áudio (com consentimento escrito do participante) — software: OBS Studio (presencial) ou gravação nativa do Meet (remoto) |
| **Observadores** | Máximo 2 observadores silenciosos (não interagem com o participante) |
| **Incentivo** | Vale-presente ou agradecimento formal (sem pagamento para não enviesar respostas) |

---

## 6. Roteiro de Recrutamento

1. Divulgação direta em turmas e grupos de WhatsApp de Engenharia de Software da faculdade da equipe.
2. Triagem rápida (conversa ou formulário curto) com as perguntas de apoio da [Persona do Participante](persona.md#23-perguntas-de-apoio-para-a-triagem).
3. Seleção de 3 participantes que atendam ao perfil; confirmação por e-mail/WhatsApp.
4. Envio de TCLE (Termo de Consentimento Livre e Esclarecido) antes da sessão.

---

## 7. Cronograma

| Etapa | Período |
|---|---|
| Recrutamento de participantes | Semana 1 |
| Piloto (1 sessão com membro do grupo) | Semana 2 — dia 1 |
| Sessões com participantes (3 sessões, 3 tarefas cada) | Semana 2–3 |
| Análise dos resultados | Semana 3–4 |
| Redação do relato | Semana 4 |

> Detalhes da execução e a gravação do piloto estão em [Teste Piloto](teste-piloto/teste-piloto.md).

---

## 8. Materiais Necessários

- [ ] TCLE assinado por cada participante
- [ ] Roteiro impresso de tarefas (entregue uma tarefa por vez)
- [ ] Planilha de observação (por participante)
- [ ] Questionário SUS impresso (ver `questionario-sus.md`) — 1 cópia por participante
- [ ] Cronômetro
- [ ] Software de gravação configurado e testado
- [ ] Notebook com Chrome limpo (sem histórico do site Sabin)

---

## Referências

> NIELSEN, Jakob. *Usability Engineering*. Academic Press, 1993.

> RUBIN, Jeffrey; CHISNELL, Dana. *Handbook of Usability Testing*. 2ª ed. Wiley, 2008.

> BROOKE, John. SUS: A "Quick and Dirty" Usability Scale. In: JORDAN, P. W. et al. (eds.). *Usability Evaluation in Industry*. Taylor & Francis, 1996. p. 189–194.
