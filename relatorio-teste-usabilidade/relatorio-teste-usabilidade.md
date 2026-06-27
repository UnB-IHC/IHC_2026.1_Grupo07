# Relatório Técnico — Teste de Usabilidade do Portal Sabin

> **Disciplina:** Interação Humano-Computador (IHC) — 2026.1
> **Instituição:** Universidade de Brasília (UnB)
> **Equipe:** Grupo 07
> **Site avaliado:** [sabin.com.br](https://www.sabin.com.br)
> **Método:** Think Aloud (Nielsen, 1993) + System Usability Scale (Brooke, 1996)
> **Referência da tarefa:** Tg_IHC-03
> **Data das sessões:** Junho/2026
> **Versão:** 1.0
> **Participantes:** P1, P2 e P3 (anonimizados conforme TCLE)

---

## Sumário

1. [Introdução](#1-introducao)
2. [Perfil do Usuário](#2-perfil-do-usuario)
3. [Metodologia e Roteiro](#3-metodologia-e-roteiro)
4. [Resultados](#4-resultados)
5. [Achados de Acessibilidade (WCAG 2.2)](#5-achados-de-acessibilidade-wcag-22)
6. [Recomendações Priorizadas](#6-recomendacoes-priorizadas)
7. [Reflexão Final](#7-reflexao-final)
8. [Referências](#referencias)
9. [Anexos](#anexos)

---

## Resumo Executivo

Mesmo com participantes de **alto letramento digital**, o fluxo de agendamento do
portal Sabin revelou-se confuso e pouco intuitivo. O termo **"Compra online"** não é
reconhecido como "agendar exame", o botão **"Agendar"** desvia o usuário para o
atendimento domiciliar sem aviso, e **não há etapa de escolha de data**. O resultado
é um **SUS médio de 41,7** (faixa "Inaceitável"). Em contraste, a tarefa de consultar
o preparo de um check-up (T3) foi resolvida sem dificuldade em ~35 s — confirmando que
o problema está **concentrado no fluxo de agendamento**, não no site como um todo.

| Indicador | Valor |
|---|---|
| Participantes (usuários reais) | 3 (P1, P2, P3) |
| Tarefas avaliadas | 3 (agendar exame, agendar vacina, ver preparo) |
| Taxa de sucesso na T1 (agendamento de exame) | **83,3%** (n=3) |
| SUS médio | **41,7 — Inaceitável** (n=3) |
| Problemas críticos/altos identificados | 3 (TU-01, TU-02, TU-03) |

---

## 1. Introdução

### 1.1 Contexto

Este relatório documenta o **teste de usabilidade empírico** conduzido pelo Grupo 07 da
disciplina de Interação Humano-Computador (IHC 2026.1, UnB) sobre o **portal Sabin
Diagnóstico e Saúde** ([sabin.com.br](https://www.sabin.com.br)), um site real e público
de uma das maiores redes de medicina diagnóstica do Brasil. A avaliação dá continuidade
às frentes anteriores do grupo — a **avaliação heurística** (TG-02) e a **avaliação de
acessibilidade** — agora validando empiricamente, **com usuários reais**, os problemas
antes previstos apenas por inspeção especialista.

O portal concentra tarefas centrais do paciente: agendar exames, agendar vacinas, consultar
instruções de preparo, localizar unidades e acessar resultados. Esta rodada foca nas
**jornadas não autenticadas** (sem login), por serem as de maior alcance e as que qualquer
participante consegue executar até o fim sem barreira de acesso.

### 1.2 Objetivo do teste

Avaliar a qualidade de uso do portal Sabin sob a perspectiva de usuários reais,
identificando problemas que dificultam a realização de tarefas centrais. Especificamente,
o teste busca:

1. Mensurar a **eficácia** (taxa de sucesso/conclusão) das tarefas definidas;
2. Mensurar a **eficiência** (tempo médio por tarefa — *time-on-task*);
3. Identificar **erros e pontos de fricção** cometidos espontaneamente pelos participantes;
4. Aferir a **satisfação subjetiva** por meio do questionário SUS;
5. **Cruzar** os achados empíricos com os problemas previstos na avaliação heurística (TG-02).

### 1.3 Fundamentação metodológica

O estudo articula métodos consagrados de IHC. O protocolo **Think Aloud** (verbalização
simultânea) de **Nielsen (1993)** orienta a coleta qualitativa; o instrumento validado
**System Usability Scale (SUS)** de **Brooke (1996)** mensura a satisfação; e as métricas
de eficácia, eficiência e erros seguem a abordagem de **Rubin & Chisnell (2008)** para
condução e análise de testes de usabilidade. As referências bibliográficas completas estão
listadas na [seção de Referências](#referencias).

---

## 2. Perfil do Usuário

### 2.1 Persona primária — "Ana"

O público real do portal Sabin é amplo (pacientes de todas as idades, cuidadores, usuários
de convênio). Para esta rodada, definiu-se uma **persona primária** e critérios objetivos de
recrutamento, conforme orienta Krug (2014).

| Atributo | Descrição |
|---|---|
| **Nome / idade** | Ana, 20 anos |
| **Ocupação / escolaridade** | Estudante de Engenharia de Software (ensino superior em curso) |
| **Dispositivo principal** | Smartphone, com uso eventual de notebook |
| **Frequência de uso da internet** | Diária e intensa (estudo, redes sociais, apps de serviço) |
| **Letramento digital** | Alto — usuária avançada, rápida em identificar padrões de interface |
| **Experiência com sites de saúde** | Já fez exames de rotina e de sangue presencialmente; usa pouco o site |
| **Contexto de uso** | Quer agendar exames sem telefonar, conferir preparo e acessar resultados online |
| **Frustrações** | Pouca paciência para fluxos longos; abandona e liga para a central se travar por 1–2 min |

### 2.2 Participantes recrutados

Foram recrutados **3 participantes reais** que se encaixam na persona, nenhum deles colega
da disciplina nem envolvido na elaboração do roteiro. Critérios de exclusão aplicados:
vínculo com o Sabin ou concorrente; experiência profissional em UX/Design; condução prévia
de testes de usabilidade.

| Participante | Perfil (idade / escolaridade / uso de internet) | Experiência com sites de saúde |
|---|---|---|
| **P1** | 20 anos, estudante de Eng. de Software, uso diário de internet, alto letramento digital | Já fez exames presencialmente; **nunca agendou pelo site** |
| **P2** | 19 anos, estudante de Eng. de Software, usa o **celular** como dispositivo principal | Já fez exames na unidade **Ceilândia Centro** |
| **P3** | Estudante de Eng. de Software (feminino); demais dados pela ficha de triagem | Conhece o Sabin; **uso pouco frequente** do site |

> **Contexto de uso (por que usam sites médicos):** os participantes representam usuários que
> recorrem ao portal para **agendar exames para si ou para familiares sem telefonar**, **conferir
> instruções de preparo** (jejum, restrições) antes de ir ao laboratório, **acessar resultados
> online** e **confirmar a unidade** mais conveniente.

### 2.3 Limitação de amostra

Os três participantes são estudantes de Engenharia de Software da mesma faculdade — amostra
**homogênea e tecnicamente fluente**. Problemas que afetam idosos, pessoas com baixa literacia
digital ou baixa visão podem **não** ter sido detectados nesta rodada. Os resultados são
**indicativos do fluxo**, não conclusivos sobre toda a base de usuários do Sabin. O fato de
até usuários fluentes terem encontrado dificuldades graves, porém, torna os achados ainda mais
relevantes: se a tarefa é difícil para quem domina tecnologia, tende a ser pior para o público
diverso real do laboratório.

---

## 3. Metodologia e Roteiro

### 3.1 Método: Think Aloud (Nielsen, 1993)

Adotou-se o protocolo **Think Aloud** (verbalização simultânea): durante cada tarefa, o
participante narra em voz alta o que pensa, procura, espera e o que o confunde. O avaliador
**não auxilia** durante as tarefas — salvo intervenção pontual registrada após travamento
prolongado — e responde a pedidos de ajuda com *"O que você tentaria fazer?"*. Cada sessão
seguiu um roteiro padronizado: boas-vindas e contextualização, tarefa de aquecimento, execução
das tarefas com verbalização, perguntas abertas pós-tarefa e questionário SUS.

| Item do procedimento | Especificação |
|---|---|
| **Modalidade** | Presencial, em ambiente controlado e silencioso |
| **Gravação** | Tela + áudio, mediante consentimento (TCLE assinado antes do início) |
| **Cronometragem** | Início na leitura completa da tarefa; fim na declaração do participante ou *timeout* de 5 min |
| **Desfecho registrado** | Sucesso sem ajuda / sucesso com ajuda / não concluiu |
| **Navegador** | Google Chrome atualizado, sem histórico/login do site, resolução 1366×768 |
| **Ética** | TCLE com objetivo, aviso de gravação, anonimato (P1–P3) e direito de desistência |

### 3.2 Tarefas e cenários

Foram redigidas **três tarefas representativas**, formuladas como **cenários de uso** (e não
como instruções literais da interface), todas **sem necessidade de login** e em fluxos distintos
do site.

> **Nota de escopo:** o template de entregáveis da disciplina sugere "5 tarefas"; a equipe
> definiu, no [planejamento](../docs/ihc-sabin/teste-usabilidade/planejamento.md), **3 tarefas
> representativas** que cobrem fluxos diferentes (exame, vacina, conteúdo informativo) e
> heurísticas distintas, suficientes para expor os problemas centrais sem fadigar o participante.

**Tarefa 1 — Agendamento de exame**
> *"Agende um exame de **hemograma completo** na unidade **Ceilândia Centro**."*
> **Sucesso:** chegar a uma tela do fluxo de agendamento com o exame e a unidade corretos
> selecionados. **Falha notável:** não localizar o exame/unidade ou cair em erro 404.

**Tarefa 2 — Agendamento de vacina (dependente)**
> *"Você quer agendar uma vacina de **febre amarela** no site, para o seu **filho de 9 meses**,
> na unidade **Águas Claras**."*
> **Sucesso:** chegar ao fluxo com a vacina e a unidade selecionados. **Observar:** se o site
> comunica claramente a restrição de idade (9 meses).

**Tarefa 3 — Busca de informação**
> *"Você quer ver as **orientações de preparo** para um agendamento de **check-up executivo**."*
> **Sucesso:** chegar à página do check-up executivo e indicar verbalmente as orientações de preparo.

Antes do teste, a equipe mapeou hipóteses de fricção para cada fluxo (storyboards), a serem
confirmadas ou refutadas pelas sessões reais:

![Storyboard com as etapas de fricção previstas no agendamento de hemograma (T1).](img/storyboard-agendamento-hemograma.png)
*Figura 1. Storyboard de hipóteses de fricção da Tarefa 1 (agendamento de hemograma).*

![Storyboard com as etapas de fricção previstas no agendamento de vacina de febre amarela (T2).](img/storyboard-vacina-febre-amarela.png)
*Figura 2. Storyboard de hipóteses de fricção da Tarefa 2 (vacina de febre amarela para dependente).*

![Storyboard com as etapas de fricção previstas na busca de preparo do check-up executivo (T3).](img/storyboard-preparo-checkup-executivo.png)
*Figura 3. Storyboard de hipóteses de fricção da Tarefa 3 (preparo de check-up executivo).*

### 3.3 Métricas coletadas

| Métrica | Tipo | Instrumento / critério |
|---|---|---|
| **Taxa de sucesso (eficácia)** | Quantitativa | Planilha de observação: sem ajuda = 1,0 · com ajuda = 0,5 · não concluiu = 0 |
| **Tempo por tarefa (eficiência)** | Quantitativa | Cronômetro (início: leitura da tarefa; fim: declaração do participante ou *timeout* de 5 min) |
| **Número de erros** | Quantitativa | Contagem de cliques/seções erradas, redirecionamentos indevidos e voltas ao início |
| **Verbalizações espontâneas** | Qualitativa | Gravação de áudio + transcrição seletiva (*Think Aloud*) |
| **Satisfação subjetiva (SUS)** | Quantitativa | Questionário SUS (10 itens, escala 1–5), aplicado uma vez ao final da sessão |
| **Observações do avaliador** | Qualitativa | Notas livres durante a sessão |

> **Cobertura da coleta:** a **Tarefa 1** foi aplicada aos **3 participantes** (n=3); as
> **Tarefas 2 e 3**, apenas a **P3** (n=1), por dificuldade de conciliar agenda com P1 e P2. O
> questionário **SUS** foi respondido pelos **3 participantes** (n=3). As métricas a seguir
> deixam explícito o tamanho da amostra de cada tarefa.
