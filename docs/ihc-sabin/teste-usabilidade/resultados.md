# Resultados do Teste de Usabilidade — Site Sabin

> **Método:** Think Aloud | **Tarefa:** "Agende um exame de hemograma completo na unidade Ceilândia Centro."
> **Participantes:** 2 estudantes de Engenharia de Software (ver [Persona do Participante](persona.md))
> **Data das sessões:** 24/06/2026
> **Avaliador(es):** Gustavo Xavier Evangelista, Lucas Andrade Zanetti

---

## 1. Resumo Quantitativo por Participante

| Participante | Concluiu? | Tempo (s) | Exame correto? | Unidade correta? | Nº de erros/desvios | SUS (0–100) |
|---|---|---|---|---|---|---|
| P1 | [x] Sim, sem ajuda [ ] Sim, com ajuda [ ] Não concluiu | 240 | [x] Sim [ ] Não | [x] Sim [ ] Não | Vários cliques em seções incorretas | 50 |
| P2 | [x] Sim, sem ajuda [ ] Sim, com ajuda [ ] Não concluiu | 195 | [x] Sim [ ] Não | [x] Sim [ ] Não | Confusão com nomenclaturas e "atendimento domiciliar" | 40 |
| **Média** | — | 217.5 | — | — | — | 45 |

### Taxa de conclusão da tarefa

`(Nº de "Sim, sem ajuda" × 1 + Nº de "Sim, com ajuda" × 0,5 + Nº de "Não concluiu" × 0) ÷ 2 = 100%`

---

## 2. Detalhamento por Participante

> Repita esta estrutura para cada um dos 2 participantes, com base na planilha de observação preenchida durante a sessão.

### P1

| Campo | Registro |
|---|---|
| Perfil (idade, curso/período, familiaridade com Sabin) | 20 anos, estudante de Engenharia de Software. Usa internet diariamente, alto letramento digital. Já usou os serviços do Sabin, mas nunca realizou agendamentos pelo site. |
| Caminho percorrido (URLs/cliques, na ordem) | Menu (três barras) -> Exames laboratoriais -> Preparo de exames -> Serviços digitais -> Unidades -> Compra online -> Busca por hemograma completo -> Comprar agora -> Prosseguir com a compra -> Nossas unidades -> Ceilândia -> Ceilândia Centro. |
| Verbalizações marcantes (citações literais) | "Eu achei bem complicado. Os nomes não eram o que eu estava esperando [...] tive que entrar em várias outras páginas para conseguir achar esse hemograma completo que não estava onde eu estava esperando, que seria lá na parte de exames." / "Eu senti falta também na questão da data" |
| Erros / desvios observados | Procurou o agendamento em abas informativas ("Exames laboratoriais", "Preparo de exames", "Serviços digitais", "Solicitação de serviço domiciliar") antes de ir para "Compra online". |
| Onde travou ou hesitou | Hesitou ao não encontrar a opção de agendamento diretamente na aba de "Exames". Sentiu falta de um campo para selecionar a data do exame. |
| Observações do avaliador | O participante explorou grande parte do menu principal tentando encontrar a opção correta, demonstrando que a taxonomia do menu não está alinhada com as expectativas (esperava achar agendamento em "Exames" e não em "Compra online"). |
| Respostas às perguntas pós-tarefa | SUS: 50 (Mediano) |

---

### P2

| Campo | Registro |
|---|---|
| Perfil (idade, curso/período, familiaridade com Sabin) | 19 anos, estudante de Engenharia de Software. Usa celular como dispositivo principal. Alto letramento digital. Já fez exames na unidade Ceilândia Centro. |
| Caminho percorrido (URLs/cliques, na ordem) | Página inicial -> Menu principal -> Abas informativas diversas -> Volta à página inicial -> Procure seu exame (Hemograma completo) -> Agendar o exame (cai em atendimento móvel) -> Voltar navegador -> Refaz a busca -> Comprar online -> Comprar -> Termos de uso -> Nossas unidades -> Ceilândia -> Ceilândia Centro. |
| Verbalizações marcantes (citações literais) | "Achei os termos um pouco confusos... a primeira opção é agendar exame, mas ele vai para um local que não faz sentido que é o atendimento domiciliar. A opção certa é comprar exame, que pra mim faria mais sentido você agendar, né?" / "Senti falta de não ter como selecionar um local e uma data" |
| Erros / desvios observados | Clicou em "agendar o exame" dentro da busca, mas foi direcionado para "atendimento domiciliar/móvel". Não encontrou botão de voltar no site, usando o do navegador e perdendo o preenchimento da busca. |
| Onde travou ou hesitou | Confundiu a nomenclatura "comprar online" (que é o caminho correto) com "agendar exame" (que levava ao serviço móvel). |
| Observações do avaliador | O participante também evidenciou um problema grave de taxonomia: "comprar" não é associado mentalmente a "agendar". Além disso, o botão de agendar no exame redireciona para um tipo de serviço restrito, frustrando o fluxo. |
| Respostas às perguntas pós-tarefa | SUS: 40 (Inaceitável) |

---

## 3. Resultado do SUS (System Usability Scale)

> Use o cálculo descrito em [Questionário SUS](questionario-sus.md) para cada participante.

| Participante | Pontuação SUS | Classificação |
|---|---|---|
| P1 | 50 | [ ] Inaceitável (<50) [x] Mediano (50–68) [ ] Bom (>68) [ ] Excelente (>80) |
| P2 | 40 | [x] Inaceitável (<50) [ ] Mediano (50–68) [ ] Bom (>68) [ ] Excelente (>80) |
| **Média** | 45 | Inaceitável (<50) |

---

## 4. Problemas de Usabilidade Identificados

> Liste cada problema observado em pelo menos 1 sessão. Use a mesma escala de severidade da [Avaliação Heurística](../avaliacao-heuristica/index.md) para permitir comparação cruzada entre as duas frentes de avaliação.

| ID | Problema observado | Participante(s) afetado(s) | Severidade | Heurística/critério relacionado | Evidência |
|---|---|---|---|---|---|
| TU-01 | Nomenclatura ambígua ("Compra online" vs "Agendar exame" vs "Serviços digitais") não corresponde ao modelo mental do usuário | P1, P2 | [x] Crítico [ ] Alto [ ] Médio [ ] Baixo | Correspondência com o mundo real (H2) | P1 procurou exames em várias abas informativas. P2 apontou que "comprar não faz sentido, deveria ser agendar". |
| TU-02 | Botão "Agendar o exame" no resultado da pesquisa direciona para atendimento móvel sem aviso prévio e sem opção clara de voltar | P2 | [ ] Crítico [x] Alto [ ] Médio [ ] Baixo | Controle e liberdade (H3), Prevenção de erros (H5) | P2 caiu na página de atendimento móvel, teve que usar o botão de voltar do navegador e perdeu a busca. |
| TU-03 | Falta de etapa para seleção de data e horário do exame no fluxo | P1, P2 | [x] Crítico [ ] Alto [ ] Médio [ ] Baixo | Visibilidade do status do sistema (H1) | Ambos os participantes reclamaram explicitamente que não lhes foi dada a opção de escolher a data do agendamento. |

---

## 5. Cruzamento com Avaliação Heurística

> Indique quais problemas previstos na [Avaliação Heurística](../avaliacao-heuristica/index.md) (HE-01 a HE-21) foram **confirmados**, **não observados** ou **não testados** nesta rodada empírica — a tarefa única cobre principalmente busca de exame e fluxo de agendamento (heurísticas H3, H5, H6, H7, H9).

| ID Heurística | Problema previsto | Confirmado no teste? | Observação |
|---|---|---|---|
| H2 / H4 | Problemas de taxonomia e nomenclatura no menu principal | [x] Confirmado [ ] Não observado [ ] Não testado | "Compra online" não é reconhecido como agendamento de exames. |
| H3 / H5 | Falta de controle/saída clara ao entrar em fluxos específicos (ex: atendimento móvel) | [x] Confirmado [ ] Não observado [ ] Não testado | O usuário precisou usar o "Voltar" do navegador e perdeu sua pesquisa. |
| H1 | Ausência de opções básicas de agendamento (ex: data e hora) | [x] Confirmado [ ] Não observado [ ] Não testado | A expectativa do agendamento não é cumprida ao final do fluxo. |

---

## 6. Síntese e Recomendações

**Principais achados:**

- A taxonomia do site (como o uso do termo "Comprar online" em vez de "Agendar") confunde os usuários e atrasa a conclusão das tarefas, indo contra o modelo mental dos pacientes.
- O redirecionamento surpresa para o serviço de atendimento móvel prejudica a fluidez, fazendo o usuário pensar que errou o caminho ou que não pode agendar em uma unidade física.
- A ausência de um calendário para marcação de data frustra os usuários no final da tarefa, passando a impressão de que o processo está incompleto.
- O SUS médio de 45 (Inaceitável) reflete um alto custo cognitivo e insatisfação com a interface.

**Recomendações priorizadas:**

| Prioridade | Problema (ID) | Ação recomendada |
|---|---|---|
| [x] Imediata [ ] Alta [ ] Média | TU-03 | Integrar a seleção de data e horário como uma etapa clara dentro do fluxo de marcação/carrinho antes da confirmação. |
| [x] Imediata [ ] Alta [ ] Média | TU-01 | Refatorar os rótulos do menu. Trocar termos como "Compra online" para "Agendamento de Exames" para ficar mais intuitivo. |
| [ ] Imediata [x] Alta [ ] Média | TU-02 | Adicionar um modal ou opção de escolha (Unidade Física vs Domiciliar) antes de jogar o usuário no formulário de atendimento móvel. |

**Limitações da rodada:**

- Amostra pequena (2 participantes) e homogênea (estudantes de Engenharia de Software da mesma faculdade) — ver nota em [Persona do Participante](persona.md#1-persona-primária). Resultados são indicativos do fluxo de agendamento, não conclusivos sobre a usabilidade geral do site para o público real do Sabin (idosos, baixa literacia digital, etc.).
- Apenas 1 tarefa testada (agendamento) — fluxos de preparo de exame, acesso a resultados e busca de unidade por outros critérios não foram cobertos nesta rodada.

---

## Referências

> NIELSEN, Jakob. *Usability Engineering*. Academic Press, 1993.

> RUBIN, Jeffrey; CHISNELL, Dana. *Handbook of Usability Testing*. 2ª ed. Wiley, 2008.

> BROOKE, John. SUS: A "Quick and Dirty" Usability Scale. In: JORDAN, P. W. et al. (eds.). *Usability Evaluation in Industry*. Taylor & Francis, 1996. p. 189–194.
