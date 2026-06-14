# User Journey e User Flows

## Introdução

No desenvolvimento de produtos digitais acessíveis, compreender a experiência do usuário em diferentes níveis de detalhe é essencial. Duas ferramentas amplamente utilizadas no design de Experiência do Usuário (UX) cumprem esse papel de formas complementares: o **User Journey** e o **User Flow**. Embora relacionadas, cada uma aborda aspectos distintos da interação entre usuário e produto.

---

## User Journey (Jornada do Usuário)

O **User Journey** — ou Jornada do Usuário — é uma representação visual e estratégica da **experiência completa** de uma pessoa ao interagir com um produto, serviço ou marca ao longo do tempo.

Seu foco é **humano e empático**: compreende emoções, pensamentos, motivações, pontos de dor e momentos de satisfação ao longo de todo o percurso, desde o primeiro contato com o produto até o uso contínuo ou abandono.

O User Journey responde perguntas como:

- *O que o usuário sente em cada etapa?*
- *Quais dificuldades ele encontra?*
- *Quais são seus objetivos e motivações?*
- *Em que momento ele desiste ou prossegue?*

---

## User Flow (Fluxo do Usuário)

O **User Flow** é uma ferramenta mais **técnica e funcional**. Ele descreve, de forma lógica e sequencial, os **passos que um usuário realiza dentro de uma interface** para atingir um objetivo específico.

O User Flow responde perguntas como:

- *Como o usuário realiza esta tarefa?*
- *Quais telas ele percorre?*
- *Quais decisões ele toma ao longo do caminho?*
- *Onde ele pode se perder ou travar?*

---

## Diferenças entre User Journey e User Flow

| Dimensão | User Journey | User Flow |
|---|---|---|
| **Escopo** | Experiência completa e macro | Tarefa específica e micro |
| **Foco** | Emoções, percepções, contexto | Passos, decisões, navegação |
| **Perspectiva** | Centrada no ser humano | Centrada na interface |
| **Uso** | Descoberta de oportunidades e pontos de dor | Identificação de problemas de usabilidade |
| **Artefato** | Mapa de jornada (com fases, ações, emoções) | Diagrama de fluxo (telas, ramificações, decisões) |
| **Quando usar** | Fases de pesquisa e estratégia | Fases de design e prototipação |

> As duas ferramentas são **complementares**: o User Journey oferece o mapa estratégico; o User Flow oferece o detalhamento tático de uma etapa específica dessa jornada.

---

## Exemplo de User Journey Map — Persona com Deficiência Visual

O mapa a seguir representa a jornada da **Ana Beatriz** (nossa persona com deficiência visual) ao acessar um portal de serviços públicos para emitir uma certidão online.

---

**Persona**: Ana Beatriz Ferreira | **Tecnologia assistiva**: NVDA (leitor de tela) | **Dispositivo**: Desktop (Windows)

---

| Fase | Ação | Pensamento | Emoção | Pontos de Dor | Oportunidades |
|---|---|---|---|---|---|
| **1. Descoberta** | Pesquisa no Google pelo serviço desejado | "Espero que o site do governo seja acessível dessa vez." | 😐 Neutro | Resultados de busca com snippets pouco descritivos | Links com títulos claros e descritivos |
| **2. Acesso ao site** | Navega até a página inicial pelo NVDA | "Vou pressionar H para ver os headings…" | 😕 Frustração | Headings ausentes ou fora de ordem lógica | Estrutura semântica consistente com H1 > H2 > H3 |
| **3. Localização do serviço** | Tenta encontrar o link para emissão de certidão | "Cadê o menu? Estou ouvindo muita coisa repetida." | 😠 Frustração | Navegação repetitiva; skip links ausentes | Skip link "Ir para o conteúdo principal" no topo |
| **4. Preenchimento do formulário** | Preenche campo a campo via NVDA | "Esse campo tem legenda? O NVDA não está lendo nada." | 😰 Ansiedade | Labels desassociadas dos inputs; campos sem descrição | Labels associados via `for`/`id`; mensagens de erro descritivas |
| **5. Autenticação** | Encontra um CAPTCHA de imagem | "Não tem alternativa de áudio? Vou ter que pedir ajuda." | 😤 Raiva / Impotência | CAPTCHA visual sem alternativa acessível | Remover CAPTCHA ou oferecer alternativa (e-mail, SMS) |
| **6. Envio e Confirmação** | Não sabe se o formulário foi enviado | "Será que funcionou? Não ouvi nenhuma confirmação." | 😟 Incerteza | Feedback de sucesso apenas visual; sem anúncio ao leitor de tela | Região `aria-live` anunciando o resultado da operação |
| **7. Download** | Tenta baixar a certidão | "Que nome é esse no arquivo? 'doc1234.pdf' não me diz nada." | 😐 Resignação | PDF com nome genérico; conteúdo não acessível | PDF com nome descritivo e conteúdo em texto, com tags de acessibilidade |

---

### Síntese da Jornada

**Emoção predominante**: Frustração e impotência em múltiplos pontos críticos.

**Principais pontos de dor**:

1. Ausência de estrutura semântica (headings, labels, skip links).
2. CAPTCHA visual sem alternativa acessível (viola WCAG 3.3.8).
3. Falta de feedback acessível após ações importantes.

**Principais oportunidades de melhoria**:

1. Implementar hierarquia semântica de headings e skip links.
2. Substituir CAPTCHA por métodos de verificação acessíveis.
3. Usar `aria-live` para anunciar mudanças de estado e confirmações.

---

## Exemplo de User Flow — Emissão de Certidão (Perspectiva de Teclado)

O User Flow abaixo detalha os passos técnicos da mesma tarefa, focando na navegação por teclado:

```
[Início] → Pressionar Tab para acessar o menu principal
     ↓
[Menu Principal] → Navegar até "Serviços" com setas do teclado → Enter
     ↓
[Listagem de Serviços] → Tab até o link "Certidões" → Enter
     ↓
[Página da Certidão] → Tab até o botão "Emitir Certidão" → Enter
     ↓
[Formulário]
  ├── Tab → Campo "CPF" → Digitar CPF
  ├── Tab → Campo "Nome" → Digitar nome
  ├── Tab → Campo "Data de nascimento" → Digitar data
  └── Tab → Botão "Enviar" → Enter
     ↓
[Autenticação]
  ├── CAPTCHA acessível? → [SIM] → Resolver → Continuar
  └──              ↓ [NÃO] → BARREIRA → Usuário abandonou ❌
     ↓
[Confirmação] → Anuncio via aria-live: "Certidão emitida com sucesso"
     ↓
[Download] → Link "Baixar certidão (PDF)" → Enter
     ↓
[FIM] ✅
```

> [!NOTE]
> Este User Flow evidencia que a **barreira do CAPTCHA** é um ponto de abandono total para usuários que dependem de teclado ou leitores de tela. A sua remoção ou substituição por alternativa acessível é uma prioridade crítica.

---

## Acessibilidade nos User Flows: Regras Essenciais

Ao mapear User Flows para usuários com necessidades de acessibilidade, considere sempre:

- **Navegação por teclado**: todo caminho deve ser percorrível sem mouse.
- **Foco visível**: o indicador de foco deve estar presente e visível em cada passo.
- **Ordem de navegação lógica**: o Tab deve percorrer os elementos de cima para baixo e da esquerda para a direita, seguindo o fluxo visual.
- **Ações com mouse têm alternativa**: gestos de arrastar, cliques com precisão e double-clicks devem ter equivalentes por teclado.
- **Feedback após ações**: toda ação crítica (envio, confirmação, erro) deve gerar um feedback perceptível por leitores de tela.
- **Nenhuma armadilha de foco**: o usuário pode entrar e sair de qualquer componente (modal, dropdown, carrossel) usando apenas o teclado.

---

## Referências Bibliográficas

> <a id="RP1" href="#TEC1">1.</a> BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Rio de Janeiro: Elsevier, 2010.

> <a id="RP2" href="#TEC2">2.</a> NIELSEN NORMAN GROUP. **Journey Mapping 101**. Disponível em: [https://www.nngroup.com/articles/journey-mapping-101/](https://www.nngroup.com/articles/journey-mapping-101/). Acesso em: jun. 2026.

> <a id="RP3" href="#TEC3">3.</a> NIELSEN NORMAN GROUP. **User Flow Is the New Wireframe**. Disponível em: [https://www.nngroup.com/articles/user-flow-wireframe/](https://www.nngroup.com/articles/user-flow-wireframe/). Acesso em: jun. 2026.

> <a id="RP4" href="#TEC4">4.</a> W3C. **Web Content Accessibility Guidelines (WCAG) 2.2**. World Wide Web Consortium, outubro 2023. Disponível em: [https://www.w3.org/TR/WCAG22/](https://www.w3.org/TR/WCAG22/).

> <a id="RP5" href="#TEC5">5.</a> ABNT. **NBR 17225:2025** — Acessibilidade em ambientes virtuais. Associação Brasileira de Normas Técnicas, 2025.

> <a id="RP6" href="#TEC6">6.</a> DINIZ, V. et al. **Guia de Boas Práticas para Acessibilidade Digital**. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf).
