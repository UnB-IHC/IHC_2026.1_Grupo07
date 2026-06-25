# :material-map-outline: Mapeamento de Experiências – Service Blueprint

!!! quote "Base bibliográfica principal"
    KALBACH, Jim. *Mapping Experiences: A Complete Guide to Customer Alignment through Journeys, Blueprints, and Diagrams*. 2ª ed. O'Reilly Media, 2020.

O *Service Blueprint* é um dos diagramas de alinhamento apresentados por Kalbach. Originado por G. Lynn Shostack (1984) e refinado por Bitner, Ostrom e Morgan (2008), representa simultaneamente a perspectiva do cliente e os processos internos da organização, tornando a lacuna entre intenção e experiência visível para toda a equipe.

---

## O que é um Service Blueprint?

Um Blueprint de Serviço é um diagrama que mapeia, numa única visão, **o que o cliente experimenta** e **o que a organização faz** – visível e invisivelmente – para entregar esse serviço. É a ferramenta de alinhamento mais adequada quando o objeto de estudo envolve múltiplos canais, atores internos e processos de bastidores que afetam a experiência.

**Diferença em relação ao Customer Journey Map:**

| Aspecto | Journey Map | Service Blueprint |
|---|---|---|
| Foco | Perspectiva do cliente | Cliente + organização interna |
| Atores | Usuário | Usuário + funcionários + sistemas |
| Profundidade | Emoções e percepções | Processos operacionais e falhas |
| Uso primário | Empatia e descoberta | Alinhamento e melhoria de serviço |

---

## Anatomia do Blueprint (Raias e Linhas)

```
┌──────────────────────────────────────────────────┐
│  EVIDÊNCIAS FÍSICAS (Physical Evidence)          │
├──────────────────────────────────────────────────┤
│  AÇÕES DO CLIENTE (Customer Actions)             │
├ ─ ─ ─ ─ ─ ─ Linha de Interação ─ ─ ─ ─ ─ ─ ─ ─┤
│  AÇÕES FRONTSTAGE (Contato Visível)              │
├ ─ ─ ─ ─ ─ ─ Linha de Visibilidade ─ ─ ─ ─ ─ ─ ─┤
│  AÇÕES BACKSTAGE (Contato Invisível)             │
├ ─ ─ ─ ─ ─ Linha de Interação Interna ─ ─ ─ ─ ─ ┤
│  PROCESSOS DE SUPORTE (Supporting Processes)     │
└──────────────────────────────────────────────────┘
```

| Raia | Descrição | Exemplos |
|---|---|---|
| **Evidências físicas** | Artefatos tangíveis que o cliente encontra em cada etapa | App, e-mail de confirmação, embalagem, uniforme, recibo |
| **Ações do cliente** | O que o cliente faz, pensa e sente | Pesquisa produto, realiza cadastro, aguarda entrega |
| **Ações frontstage** | Ações visíveis do funcionário ou sistema que interagem diretamente com o cliente | Atendente responde chat, sistema exibe confirmação de pedido |
| **Ações backstage** | Ações da organização invisíveis ao cliente mas que o afetam diretamente | Gerente aprova crédito, operador separa itens no estoque |
| **Processos de suporte** | Sistemas e departamentos internos que sustentam as ações frontstage/backstage | ERP, sistema de pagamento, transportadora |

---

## Fase 1 – Preparação e Escopo

- [ ] <b>Definir o cenário</b> do serviço a ser mapeado: qual jornada específica (ex: "primeira compra online", "cancelamento de assinatura"). <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] <b>Estabelecer o nível de granularidade</b>: blueprint de alto nível (estratégico) ou detalhado (operacional). Não misturar os dois níveis no mesmo diagrama. <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] <b>Identificar o perfil de cliente</b> a ser representado (persona primária). Se múltiplos perfis existirem, considerar blueprints separados ou uma nota de variação. <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] <b>Reunir equipe multidisciplinar</b>: representantes de design, desenvolvimento, negócios, operações e atendimento ao cliente.
- [ ] <b>Coletar dados de pesquisa</b> existentes: entrevistas com usuários, registros de atendimento, logs de sistema, dados analíticos. O blueprint representa a realidade atual ("as-is") antes de propor melhorias ("to-be"). <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] <b>Mapear os atores internos</b> envolvidos em cada etapa do serviço (funcionários, departamentos, sistemas automatizados). <a id="BLU2" href="#RBLU2">[2]</a>

---

## Fase 2 – Construção das Raias

### Ações do Cliente
- [ ] Listar as <b>etapas cronológicas da jornada do cliente</b> de ponta a ponta (ex: pré-serviço → serviço → pós-serviço). <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] Registrar o que o cliente <b>faz</b> (ação concreta), não o que o sistema faz por ele.
- [ ] Incluir os <b>canais</b> em que cada ação ocorre (web, app mobile, telefone, presencial).
- [ ] Adicionar dimensão emocional: identificar o <b>estado emocional do cliente</b> em cada etapa (satisfeito, confuso, frustrado). Representar como curva de emoção abaixo das ações. <a id="BLU1" href="#RBLU1">[1]</a>

### Evidências Físicas
- [ ] Para cada etapa do cliente, identificar <b>todos os artefatos tangíveis ou digitais</b> com que o cliente entra em contato.
- [ ] Incluir evidências que influenciam a percepção antes e depois do serviço principal (ex: e-mail de boas-vindas antes do onboarding, NPS após a entrega). <a id="BLU2" href="#RBLU2">[2]</a>

### Ações Frontstage
- [ ] Mapear cada ação ou resposta do sistema/funcionário que o cliente **vê ou percebe** diretamente.
- [ ] Distinguir entre <b>ações humanas</b> (funcionário) e <b>ações automatizadas</b> (sistema): usar notação visual diferente.
- [ ] Verificar se cada ação frontstage está diretamente conectada a uma ação do cliente acima da Linha de Interação. <a id="BLU1" href="#RBLU1">[1]</a>

### Ações Backstage
- [ ] Mapear processos que <b>o cliente não vê</b> mas que são necessários para que a ação frontstage aconteça.
- [ ] Identificar <b>handoffs</b> (transferências de responsabilidade) entre pessoas e sistemas nessa raia.
- [ ] Registrar o <b>tempo médio</b> de cada ação backstage quando relevante para a percepção do cliente (ex: tempo de aprovação de crédito impacta a espera visível). <a id="BLU2" href="#RBLU2">[2]</a>

### Processos de Suporte
- [ ] Mapear todos os <b>sistemas, APIs, fornecedores externos e departamentos de apoio</b> acionados pelas ações backstage.
- [ ] Identificar <b>SLAs e dependências externas</b> que limitam a velocidade do serviço. <a id="BLU2" href="#RBLU2">[2]</a>

---

## Fase 3 – Análise e Anotações

- [ ] Marcar <b>Momentos da Verdade</b> (*Moments of Truth*): etapas em que a percepção do cliente sobre o serviço é formada ou alterada de forma decisiva. <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] Identificar e anotar <b>pontos de falha potencial</b> (*fail points*): onde processos internos têm maior probabilidade de gerar problemas visíveis ao cliente. <a id="BLU2" href="#RBLU2">[2]</a>
- [ ] Identificar <b>gargalos e tempos de espera</b> (*wait times*): etapas em que o cliente aguarda sem feedback ou ação perceptível. <a id="BLU2" href="#RBLU2">[2]</a>
- [ ] Anotar <b>oportunidades de melhoria</b> diretamente no diagrama: diferenciá-las visualmente dos elementos descritivos (ex: sticky note de cor diferente). <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] Verificar <b>consistência entre canais</b>: a experiência é coerente se o cliente muda de canal no meio do serviço (ex: começa no app e conclui por telefone)? <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] Identificar etapas com <b>esforço excessivo do cliente</b> (ações que deveriam ser automatizadas ou eliminadas). <a id="BLU1" href="#RBLU1">[1]</a>

---

## Fase 4 – Alinhamento e Uso

- [ ] Apresentar o blueprint em <b>workshop colaborativo</b> com stakeholders: usar o diagrama como objeto de conversa, não de entrega. <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] Criar versão <b>as-is</b> (estado atual) antes de versão <b>to-be</b> (estado desejado). Não misturar as duas no mesmo diagrama. <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] Usar o blueprint para <b>priorizar melhorias</b>: conectar falhas identificadas a métricas de impacto (NPS, taxa de abandono, tempo de resolução).
- [ ] <b>Manter o blueprint vivo</b>: revisar após mudanças significativas no serviço ou após ciclos de pesquisa com usuários. Um blueprint desatualizado gera alinhamento falso. <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] Conectar o blueprint a outros artefatos de UX: <b>user stories, protótipos e critérios de aceitação</b> devem referenciar etapas do blueprint.

---

## Variações de Diagramas de Alinhamento (Kalbach, Cap. 3-9)

Kalbach apresenta seis tipos de diagramas. Escolha o mais adequado ao contexto:

| Diagrama | Melhor Uso | Eixo Central |
|---|---|---|
| **Customer Journey Map** | Entender percepção emocional da jornada | Tempo × Emoção |
| **Service Blueprint** | Alinhar operações internas com experiência | Visibilidade × Processo |
| **Experience Map** | Jornadas sem produto específico (ex: comprar uma casa) | Fases de vida |
| **Mental Model Diagram** | Compreender modelos mentais e gaps de produto | Comportamentos × Funcionalidades |
| **Spatial Map / Ecosystem Map** | Relações entre atores em ecossistemas complexos | Topologia |
| **Org Chart / Diagram** | Estrutura de responsabilidades | Hierarquia |

---

## Service Blueprint com Lente de Acessibilidade

Ao mapear o serviço, considere os perfis de usuário descritos na seção de [Gestão de Projetos](../gestaoProjeto/gestaoProjeto.md) (deficiência visual, física, auditiva, na fala, neurodiversidade, múltiplas deficiências e limitações decorrentes do envelhecimento).

- [ ] **Persona com deficiência no cabeçalho:** ao menos um blueprint representa a jornada de um usuário de tecnologia assistiva (leitor de tela, navegação só por teclado, ampliação de tela). <a id="BLU1" href="#RBLU1">[1]</a>
- [ ] **Evidências físicas acessíveis:** cada artefato tangível/digital da raia de evidências é avaliado quanto à acessibilidade (e-mail com texto alternativo, app compatível com leitor de tela, documento em formato acessível). (WCAG 2.2 – NBR 17225:2025)
- [ ] **Ações do cliente por tecnologia assistiva:** as ações são descritas considerando como o usuário as executa com teclado, leitor de tela ou comando de voz — não apenas com mouse e visão.
- [ ] **Atores de suporte de acessibilidade:** a raia de processos de suporte inclui dependências como APIs de acessibilidade do sistema operacional, legendagem, intérprete de Libras ou atendimento prioritário, quando aplicável.
- [ ] ***Fail points* de acessibilidade:** os pontos de falha mapeados incluem barreiras de acessibilidade (CAPTCHA inacessível, foco perdido, ausência de legenda, contraste insuficiente) e não apenas falhas operacionais. <a id="BLU2" href="#RBLU2">[2]</a>
- [ ] **Momentos da verdade inclusivos:** verifica-se se os *Moments of Truth* permanecem positivos para usuários com deficiência, ou se introduzem fricção exclusiva a esse público.

## Checklist de Qualidade do Blueprint

- [ ] O diagrama tem **título, data, versão e autoria** registrados.
- [ ] A **persona ou perfil de cliente** está identificado no cabeçalho.
- [ ] O **cenário** (contexto de uso) está descrito.
- [ ] As **linhas de separação** (interação, visibilidade, interação interna) estão claramente demarcadas.
- [ ] As raias são **horizontais e paralelas**, cada uma representando um nível de responsabilidade.
- [ ] As colunas representam **etapas cronológicas**, não actores.
- [ ] Pontos de falha e momentos da verdade estão **anotados visualmente** de forma distinta.
- [ ] O blueprint foi **validado com pelo menos um funcionário** de cada área representada.
- [ ] Existe uma **legenda** explicando os símbolos e cores usados.

---

## Referências Bibliográficas

> <a id="RBLU1" href="#BLU1">1.</a> KALBACH, Jim. *Mapping Experiences: A Complete Guide to Customer Alignment through Journeys, Blueprints, and Diagrams*. 2ª ed. Sebastopol, CA: O'Reilly Media, 2020.

> <a id="RBLU2" href="#BLU2">2.</a> BITNER, Mary Jo; OSTROM, Amy L.; MORGAN, Felicia N. Service Blueprinting: A Practical Technique for Service Innovation. *California Management Review*, v. 50, n. 3, p. 66–94, 2008. DOI: 10.2307/41166446.

## Bibliografia

> SHOSTACK, G. Lynn. Designing Services That Deliver. *Harvard Business Review*, v. 62, n. 1, p. 133–139, jan./fev. 1984.

> STICKDORN, Marc; HORMESS, Markus; LAWRENCE, Adam; SCHNEIDER, Jakob. *This Is Service Design Doing*. O'Reilly Media, 2018.

> KALBACH, Jim. *The Jobs To Be Done Playbook*. Two Waves Books, 2020.

> DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R. Guia de Boas Práticas para Acessibilidade Digital. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf). Acesso em: jun. 2026.
