# Planejamento do Teste de Usabilidade — Site Sabin

> **Site avaliado:** [sabin.com.br](https://www.sabin.com.br)
> **Método:** Think Aloud (Protocolo de Verbalização Simultânea)
> **Data de planejamento:** Junho/2026
> **Responsável:** Equipe IHC 2026.1 Grupo 07

---

## 1. Objetivo do Teste

Avaliar a usabilidade do site Sabin Diagnóstico e Saúde sob a perspectiva de usuários reais, identificando problemas que dificultam a realização do fluxo de agendamento de exames — desde a busca pelo exame até a seleção da unidade de atendimento. O teste busca:

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

**3 participantes**, todos estudantes de Engenharia de Software da faculdade da equipe avaliadora, recrutados conforme os critérios de inclusão/exclusão acima. Por restrição de tempo e disponibilidade da equipe, o teste foi reduzido de 5 para 3 sessões e de múltiplas tarefas para **1 tarefa única por sessão** — concentrando a observação no fluxo de agendamento ponta a ponta, em vez de cobertura ampla de fluxos secundários.

> **Observação metodológica:** com 3 participantes, 1 tarefa e uma amostra homogênea (mesma faculdade, mesmo curso), a rodada é menor e menos diversa que o recomendado por Nielsen (1993) para saturação de problemas (~5 avaliadores variados). Os resultados devem ser tratados como indicativos do fluxo de agendamento em si, não conclusivos sobre a usabilidade geral do site, e relatados como tal no seminário final.

---

## 3. Tarefas a Serem Executadas

Cada um dos 3 participantes realiza **a mesma tarefa única**, para permitir comparação direta dos resultados entre sessões. A tarefa foi escolhida por cobrir, em um único fluxo, busca de exame, seleção de unidade e início do agendamento — pontos associados a problemas identificados na avaliação heurística (ver `avaliacao-heuristica/index.md`).

| # | Tarefa | O que o participante deve fazer | Critério de sucesso | Heurísticas relacionadas |
|---|---|---|---|---|
| T1 | "Agende um exame de hemograma completo na unidade Ceilândia Centro." | Partindo da homepage do Sabin, sem ajuda do avaliador, o participante deve localizar o exame "Hemograma Completo", iniciar o fluxo de agendamento e selecionar a unidade "Ceilândia Centro", avançando o quanto conseguir no processo (não precisa concluir o agendamento real, ex.: pagamento ou confirmação final). | Participante chega a uma tela real do fluxo de agendamento com o exame "Hemograma Completo" e a unidade "Ceilândia Centro" corretamente selecionados — falha notável é não localizar o exame, não localizar a unidade ou cair em erro 404 | H3, H5, H6, H7, H9 |

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
| Sessões com participantes (3 sessões, 1 tarefa cada) | Semana 2–3 |
| Análise dos resultados | Semana 3–4 |
| Redação do relato | Semana 4 |

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
