# Planejamento do Teste de Usabilidade — Site Sabin

> **Site avaliado:** [sabin.com.br](https://www.sabin.com.br)
> **Método:** Think Aloud (Protocolo de Verbalização Simultânea)
> **Data de planejamento:** Junho/2026
> **Responsável:** Equipe IHC 2026.1 Grupo 07

---

## 1. Objetivo do Teste

Avaliar a usabilidade do site Sabin Diagnóstico e Saúde sob a perspectiva de usuários reais, identificando problemas que dificultam a realização das tarefas mais comuns: localizar informações sobre exames, agendar atendimento e acessar resultados de exames. O teste busca:

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

### Quantidade mínima de participantes

**5 participantes** (Nielsen, 1993: 5 avaliadores identificam ~75–85% dos problemas de usabilidade em testes moderados). Recomenda-se recrutar 7 para garantir 5 sessões válidas em caso de desistências.

---

## 3. Tarefas a Serem Executadas

As tarefas foram criadas com base nos fluxos principais do site e nos problemas identificados na avaliação heurística (ver `avaliacao-heuristica/index.md`).

| # | Tarefa | Critério de sucesso | Heurísticas relacionadas |
|---|---|---|---|
| T1 | "Você precisa fazer um hemograma. Encontre no site quais são as instruções de preparo (jejum, restrições)." | Participante localiza a página de preparo do exame hemograma com as instruções corretas | H6, H7 |
| T2 | "Você quer agendar um exame de sangue presencialmente. Use o site para iniciar o agendamento." | Participante chega à tela de agendamento (ou identifica o fluxo correto) | H3, H5, H9 |
| T3 | "Encontre a unidade Sabin mais próxima ao CEP 70040-010 (Brasília, Asa Norte) e descubra o horário de funcionamento." | Participante localiza pelo menos 1 unidade com endereço e horário | H1, H6, H7 |
| T4 | "Você realizou um exame há 2 dias e quer ver o resultado online. Acesse a área de resultados de exames." | Participante chega à tela de login do portal de laudos | H2, H9, H10 |
| T5 | "Você tem dúvidas sobre o exame TSH. Encontre no site se o Sabin aceita seu convênio (Unimed Brasília)." | Participante localiza a seção de convênios e verifica Unimed | H2, H6 |

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

1. Divulgação via grupos de WhatsApp, lista de e-mails da universidade e redes sociais.
2. Formulário Google Forms com perguntas de triagem (faixa etária, escolaridade, experiência com sites de saúde).
3. Seleção de 7 participantes que atendam ao perfil; confirmação por e-mail/WhatsApp.
4. Envio de TCLE (Termo de Consentimento Livre e Esclarecido) 48h antes da sessão.

---

## 7. Cronograma

| Etapa | Período |
|---|---|
| Recrutamento de participantes | Semana 1 |
| Piloto (1 sessão com membro do grupo) | Semana 2 — dia 1 |
| Sessões com participantes (5–7 sessões) | Semana 2–3 |
| Análise dos resultados | Semana 3–4 |
| Redação do relato | Semana 4 |

---

## 8. Materiais Necessários

- [ ] TCLE assinado por cada participante
- [ ] Roteiro impresso de tarefas (entregue uma tarefa por vez)
- [ ] Planilha de observação (por participante)
- [ ] Questionário SUS impresso ou digital
- [ ] Cronômetro
- [ ] Software de gravação configurado e testado
- [ ] Notebook com Chrome limpo (sem histórico do site Sabin)

---

## Referências

> NIELSEN, Jakob. *Usability Engineering*. Academic Press, 1993.

> RUBIN, Jeffrey; CHISNELL, Dana. *Handbook of Usability Testing*. 2ª ed. Wiley, 2008.

> BROOKE, John. SUS: A "Quick and Dirty" Usability Scale. In: JORDAN, P. W. et al. (eds.). *Usability Evaluation in Industry*. Taylor & Francis, 1996. p. 189–194.
