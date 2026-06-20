# UX Canvas (Lean UX Canvas)

> **Base bibliográfica principal:** GOTHELF, Jeff; SEIDEN, Josh. *Lean UX: Designing Great Products with Agile Teams*. 3ª ed. Sebastopol, CA: O'Reilly Media, 2021.
>
> **Base complementar:** ZAWADZKI, Leszek. *User-Centered Design Canvas (UCDC)*. Desenvolvido e validado em ambiente acadêmico na Universidade de Wrocław.
>
> O **UX Canvas** — popularizado como *Lean UX Canvas* por Jeff Gothelf — é uma ferramenta de facilitação para equipes multifuncionais. Ele codifica o processo apresentado no livro *Lean UX*: enquadrar o trabalho como um **problema de negócio a resolver** (não uma solução a implementar), decompor esse problema em **suposições**, transformá-las em **hipóteses** e desenhar **experimentos** para testar as mais arriscadas.

---

## O que é um UX Canvas?

Um UX Canvas é um quadro visual de uma página que organiza, numa única imagem, **o problema de negócio**, **os usuários e seus resultados desejados**, **as soluções candidatas** e **as suposições mais arriscadas** a serem validadas. Em vez de começar pela solução, a equipe começa pela pergunta "o que mudou no mundo que precisa ser resolvido?" e progride até definir o menor experimento possível para aprender.

Características centrais:

- **Centrado no resultado (*outcome*), não na entrega (*output*)** — desloca a conversa de "o que vamos construir" para "que mudança de comportamento queremos provocar". <a id="UXC1" href="#RUXC1">[1]</a>
- **Documento vivo** — preenchido com suposições, não certezas; é revisado à medida que a equipe aprende. <a id="UXC2" href="#RUXC2">[2]</a>
- **Colaborativo** — alinha equipe de produto, design, desenvolvimento e negócio em torno de um entendimento comum do usuário e do problema. <a id="UXC1" href="#RUXC1">[1]</a>

### Por que usar o UX Canvas?

| Valor | O que entrega |
|---|---|
| **Foco no "porquê"** | A equipe entende a razão do trabalho antes de discutir telas e funcionalidades |
| **Expõe lacunas de entendimento** | Torna visíveis as suposições não declaradas sobre usuários e negócio |
| **Garante aprendizado** | Funciona como "apólice de seguro" de que cada ciclo gera aprendizado, não apenas código |
| **Alinhamento multifuncional** | Cria uma conversa centrada no cliente entre áreas que normalmente não conversam |
| **Decisões baseadas em evidência** | Conecta suposições a hipóteses e a experimentos que produzem dados reais |

> O objetivo não é preencher o quadro com a "resposta certa", mas provocar a **conversa** e o **aprendizado** que levam à resposta. <a id="UXC2" href="#RUXC2">[2]</a>

---

## Anatomia do Lean UX Canvas (V2)

O canvas é dividido em **8 caixas numeradas**. Cada caixa responde a uma pergunta.

| # | Caixa | Pergunta que responde |
|---|---|---|
| **1** | **Problema de Negócio** (*Business Problem*) | O que mudou no mundo/mercado que impacta o negócio e precisa ser resolvido? |
| **2** | **Resultados de Negócio** (*Business Outcomes*) | Que mudança de comportamento do usuário indica que o problema foi resolvido? (ex.: "+25% de retenção") |
| **3** | **Usuários** (*Users*) | Quais personas — clientes, administradores, compradores — buscamos atender? |
| **4** | **Resultados e Benefícios do Usuário** (*User Outcomes & Benefits*) | Que objetivo emocional ou prático o usuário quer alcançar ao usar a solução? |
| **5** | **Soluções** (*Solutions*) | Que ideias — de funcionalidades táticas a novos modelos de negócio — podem produzir os resultados desejados? |
| **6** | **Hipóteses** (*Hypotheses*) | Como conectamos usuários, resultados e soluções em afirmações testáveis? |
| **7** | **O que precisamos aprender primeiro?** | Qual é a suposição mais arriscada que, se falsa, derruba todo o plano? |
| **8** | **Qual o menor trabalho para aprender isso?** | Qual o menor experimento (MVP) capaz de testar essa suposição? |

> **Formato da hipótese (caixa 6):** *"Acreditamos que [resultado de negócio] será alcançado se [usuário] atingir [benefício] com [solução]."* <a id="UXC1" href="#RUXC1">[1]</a>

### Ordem de preenchimento

O fluxo lógico segue a numeração, mas a sequência conceitual é: **problema de negócio → suposições → hipóteses → experimentos**.

```
[1] Problema de negócio
      ↓
[2] Resultados de negócio  ←→  [3] Usuários  ←→  [4] Benefícios do usuário
      ↓
[5] Soluções
      ↓
[6] Hipóteses (conectam 2, 3, 4 e 5)
      ↓
[7] Suposição mais arriscada
      ↓
[8] Menor experimento para validar
```

> O canvas é frequentemente preenchido fora de ordem e revisitado: ao descobrir uma suposição arriscada (7), a equipe pode voltar e reescrever hipóteses (6) ou redefinir resultados (2). <a id="UXC2" href="#RUXC2">[2]</a>

---

## UX Canvas vs. outros canvas

| Canvas | Foco | Pergunta-chave |
|---|---|---|
| **Lean UX Canvas** | Suposições e aprendizado sobre produto/experiência | "O que precisamos aprender primeiro?" |
| **Business Model Canvas** | Modelo de negócio completo (Osterwalder) | "Como a empresa cria e captura valor?" |
| **Value Proposition Canvas** | Encaixe entre dores/ganhos do cliente e a oferta | "Por que o cliente escolheria isso?" |
| **User-Centered Design Canvas** | Pesquisa de usuário ↔ objetivos de negócio | "Quem é o usuário e o que o move?" |

> Os canvas são **complementares**: o Lean UX Canvas foca no ciclo de descoberta e validação; o User-Centered Design Canvas aprofunda o entendimento do usuário antes de propor soluções.

---

## User-Centered Design Canvas (complementar)

Criado por **Leszek Zawadzki** e refinado com a psicóloga Alina Prelicz, foi desenvolvido e testado no ensino de UX na Universidade de Wrocław. Coloca o **usuário no centro**: o lado esquerdo trata do usuário, o direito do negócio. Possui **9 campos** preenchidos em ordem:

| # | Campo | Captura |
|---|---|---|
| 1 | **Negócio** | Nome/descrição do produto ou empresa |
| 2 | **Usuários** | Tipos de clientes reais ou potenciais |
| 3 | **Problemas** | Necessidades e desafios do usuário |
| 4 | **Motivações** | Drivers emocionais ou ocultos do comportamento |
| 5 | **Medos** | Ansiedades do usuário em relação à oferta |
| 6 | **Soluções** | Formas de endereçar problemas e medos |
| 7 | **Alternativas** | Opções concorrentes disponíveis ao usuário |
| 8 | **Vantagens Competitivas** | Qualidades que diferenciam a oferta |
| 9 | **Proposta Única de Valor** | Síntese de uma frase de todas as descobertas |

> O canvas alimenta diretamente artefatos de UX: estratégia de conteúdo, arquitetura da informação, mapas de jornada e refinamento de personas. <a id="UXC3" href="#RUXC3">[3]</a>

---

## Fase 1 – Preparação da Sessão

- [ ] <b>Definir o objetivo da sessão:</b> qual produto, feature ou problema será explorado no canvas.
- [ ] <b>Reunir equipe multifuncional:</b> representantes de produto, design, desenvolvimento e negócio na mesma sessão. <a id="UXC1" href="#RUXC1">[1]</a>
- [ ] <b>Reunir dados de pesquisa existentes:</b> entrevistas, dados analíticos, pesquisas de mercado — o canvas é preenchido com suposições, mas suposições informadas são melhores.
- [ ] <b>Escolher o suporte:</b> quadro físico (post-its) ou ferramenta digital (Miro, Mural, FigJam) para manter o artefato vivo e editável.
- [ ] <b>Definir um facilitador</b> que guie a conversa e mantenha o foco em resultados, não em soluções prematuras.

---

## Fase 2 – Preenchimento do Canvas

- [ ] <b>Caixa 1 – Problema de negócio:</b> escrever o que mudou no mercado/contexto que motiva o trabalho, sem citar a solução. <a id="UXC1" href="#RUXC1">[1]</a>
- [ ] <b>Caixa 2 – Resultados de negócio:</b> definir métricas de mudança de comportamento (não funcionalidades a entregar).
- [ ] <b>Caixa 3 – Usuários:</b> descrever as personas relevantes (clientes, administradores, compradores).
- [ ] <b>Caixa 4 – Benefícios do usuário:</b> descrever o objetivo emocional/prático que faz o usuário buscar a solução. <a id="UXC1" href="#RUXC1">[1]</a>
- [ ] <b>Caixa 5 – Soluções:</b> brainstorm de ideias, de funcionalidades táticas a novos modelos de negócio.
- [ ] <b>Caixa 6 – Hipóteses:</b> escrever afirmações testáveis conectando resultado + usuário + benefício + solução.
- [ ] <b>Caixa 7 – Aprendizado prioritário:</b> identificar a suposição mais arriscada (a que, se falsa, derruba o plano). <a id="UXC2" href="#RUXC2">[2]</a>
- [ ] <b>Caixa 8 – Menor experimento:</b> definir o MVP/experimento mínimo capaz de testar essa suposição.

---

## Fase 3 – Validação e Iteração

- [ ] <b>Executar o experimento</b> definido na caixa 8 e coletar evidências.
- [ ] <b>Revisar o canvas com base no aprendizado:</b> confirmar, descartar ou reformular hipóteses e suposições.
- [ ] <b>Tratar o canvas como documento vivo:</b> reabri-lo a cada ciclo de descoberta, não como entrega única. <a id="UXC2" href="#RUXC2">[2]</a>
- [ ] <b>Conectar a outros artefatos de UX:</b> personas, jornadas, user stories e critérios de aceitação devem refletir o que foi aprendido.

---

## UX Canvas com Lente de Acessibilidade

Ao preencher o canvas, considere os perfis de usuário descritos na seção de [Gestão de Projetos](../gestaoProjeto/gestaoProjeto.md) (deficiência visual, física, auditiva, na fala, neurodiversidade, múltiplas deficiências e limitações decorrentes do envelhecimento).

- [ ] **Usuários com deficiência nas personas (caixa 3):** ao menos uma persona representa um usuário de tecnologia assistiva (leitor de tela, navegação só por teclado, ampliação de tela).
- [ ] **Benefícios acessíveis (caixa 4):** os resultados desejados do usuário incluem realizar a tarefa de forma autônoma com tecnologia assistiva, não apenas com mouse e visão. (WCAG 2.2 – NBR 17225:2025)
- [ ] **Soluções inclusivas (caixa 5):** o brainstorm contempla a remoção de barreiras de acessibilidade como solução de valor.
- [ ] **Hipóteses de acessibilidade (caixa 6):** ao menos uma hipótese trata de inclusão (ex.: "acreditamos que reduzir o abandono será alcançado se usuários de leitor de tela concluírem o cadastro sem CAPTCHA inacessível").
- [ ] **Experimentos com público diverso (caixa 8):** o experimento mínimo inclui pessoas com deficiência entre os participantes do teste.
- [ ] **Resultados de negócio inclusivos (caixa 2):** as métricas de comportamento são segmentadas para verificar se a melhoria alcança usuários com deficiência ou introduz fricção exclusiva a esse público.

---

## Checklist de Qualidade do UX Canvas

- [ ] A caixa 1 descreve um **problema de negócio**, não uma solução disfarçada.
- [ ] Os **resultados de negócio** (caixa 2) são mudanças de comportamento mensuráveis, não listas de funcionalidades.
- [ ] As **personas** (caixa 3) estão descritas com características reais, baseadas em pesquisa.
- [ ] Cada **hipótese** (caixa 6) é uma afirmação testável que conecta usuário, benefício e solução.
- [ ] A **suposição mais arriscada** (caixa 7) está explicitamente identificada.
- [ ] O **experimento** (caixa 8) é o menor trabalho possível para gerar aprendizado.
- [ ] O canvas foi preenchido por uma **equipe multifuncional**, não por uma única área.
- [ ] O canvas é tratado como **documento vivo** e datado, revisado a cada ciclo.
- [ ] Acessibilidade está presente em pelo menos uma persona, hipótese e experimento.

---

## Referências Bibliográficas

> <a id="RUXC1" href="#UXC1">1.</a> GOTHELF, Jeff; SEIDEN, Josh. *Lean UX: Designing Great Products with Agile Teams*. 3ª ed. Sebastopol, CA: O'Reilly Media, 2021.

> <a id="RUXC2" href="#UXC2">2.</a> GOTHELF, Jeff. *The Lean UX Canvas V2*. 2019. Disponível em: [https://jeffgothelf.com/blog/leanuxcanvas-v2/](https://jeffgothelf.com/blog/leanuxcanvas-v2/). Acesso em: jun. 2026.

> <a id="RUXC3" href="#UXC3">3.</a> ZAWADZKI, Leszek. *Introducing the User-Centered Design Canvas*. UX Magazine. Disponível em: [https://uxmag.com/articles/introducing-the-user-centered-design-canvas](https://uxmag.com/articles/introducing-the-user-centered-design-canvas). Acesso em: jun. 2026.

## Bibliografia

> OSTERWALDER, Alexander; PIGNEUR, Yves. *Business Model Generation*. John Wiley & Sons, 2010.

> OSTERWALDER, Alexander; PIGNEUR, Yves; BERNARDA, Greg; SMITH, Alan. *Value Proposition Design: How to Create Products and Services Customers Want*. John Wiley & Sons, 2014.

> RIES, Eric. *The Lean Startup: How Today's Entrepreneurs Use Continuous Innovation to Create Radically Successful Businesses*. Crown Business, 2011.

> DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R. Guia de Boas Práticas para Acessibilidade Digital. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf). Acesso em: jun. 2026.
