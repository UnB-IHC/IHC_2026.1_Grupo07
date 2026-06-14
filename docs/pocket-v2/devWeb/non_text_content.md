# Desenvolvimento

> **[NOVO - TG10/Grupo07]** Esta seção foi atualizada para incluir os critérios novos do **WCAG 2.2** (out/2023) e referências à **ABNT NBR 17225:2025**, que incorpora o WCAG 2.2 como base legal no Brasil. Itens marcados com `[NOVO WCAG 2.2]` não estavam presentes na versão V1 (VerificaAAA, 2024). Referência: TG10 – Estudo Aprofundado WCAG 2.2 (Grupo 7, 2026).

"Nessa fase, é importante garantir que a equipe de desenvolvimento saiba como implementar acessibilidade, verificá-la e usar as ferramentas disponíveis no mercado para
testes e padronizações. Também é importante que a equipe saiba como as pessoas com deficiência usam os sítios web e aplicativos". Nesse caso, foram incluídas técnicas relacionadas ao desenvolvimento e também formas de verificar.

## Imagens
- [ ] <b> Adicionar ``` alt ``` </b> para imagens, botões-imagem, gráficos e imagens de mapas com pontos de acesso. <a id="TEC1" href="#RP1">[1]</a>
- [ ] <b> Adicionar ``` alt="" ``` </b> para imagens decorativas que não tem significado. <a id="TEC1" href="#RP1">[1]</a>
- [ ] <b> Incluir a descrição no ``` alt ```</b> para imagens que contém texto. <a id="TEC1" href="#RP1">[1]</a>

## Vídeos
- [ ] <b> Adicionar legendas</b> para áudio em vídeos existentes. <a id="TEC2" href="#RP2">[2]</a>
- [ ] <b> Evitar conteúdo com <i>flashes</i> (gatilhos para convulsões)</b> ou manter abaixo dos limites. <a id="TEC3" href="#RP3">[3]</a>

## Controles
- [ ] <b> Adicionar ``` href ```</b> para links. <a id="TEC4" href="#RP4">[4]</a>
- [ ] <b> Adicionar underline</b> nos links. <a id="TEC5" href="#RP5">[5]</a>
- [ ] <b> Adicionar estados de foco</b> em campos de entrada, botões, e elementos interativos. <a id="TEC6" href="#RP6">[6]</a>
- [ ] <b> Adicionar ```type="button"```</b> nos botões. <a id="TEC4" href="#RP4">[4]</a>
- [ ] <b> Adicionar skip-link </b> (link para pular) para o conteúdo principal. <a id="TEC7" href="#RP7">[7]</a>
- [ ] <b> Identifique e comunique </b> links que abrem em uma nova guia ou janela. <a id="TEC8" href="#RP8">[8]</a>

## Formulário
- [ ] <b> Adicionar ``` label ```</b> para os campos de entradas associadas ao elemento correspondente. <a id="TEC9" href="#RP9">[9]</a>
- [ ] <b> Adicionar ``` <fildset> ``` e ``` <legend> ```</b> para seção no formulário. <a id="TEC4" href="#RP4">[4]</a>
- [ ] <b> Adicionar ``` autocomplete ```</b> para campos de entrada. <a id="TEC10" href="#RP10">[10]</a>
- [ ] <b> Exibir ``` errors ``` </b> (erros) de entrada acima do formulário, após envio. <a id="TEC11" href="#RP11">[11]</a>
- [ ] <b> Adicionar ``` aria-describedby ```</b> para os campos de entrada. <a id="TEC11" href="#RP11">[11]</a>
- [ ] <b> Exibir mensagens de erro e sucesso</b> não só visualmente. <a id="TEC5" href="#RP5">[5]</a>

## Mídia
- [x] <b> Impedir ``` autoplay ```</b> para vídeos e audios. <a id="TEC12" href="#RP12">[12]</a>
- [ ] <b> Adicionar ``` type ```</b> para botões e entradas. <a id="TEC4" href="#RP4">[4]</a>
- [x] <b> Adicionar pausa </b> para todas as mídias. <a id="TEC13" href="#RP13">[13]</a>
- [x] <b> Adicionar transcrição </b> para audios. <a id="TEC1" href="#RP1">[1]</a>

## Semântica
- [x] Uso de elementos <b>nativos HTML</b>. 
- [x] Fluxo continuo e <b>Lógico</b>. 
- [x] Tem <b>descrições</b> que podem ser <b>facilmente compreendidas</b>. 
- [x] Tem a <b>semântica correta</b>. 
- [x] É <b>objetivo</b> nos <b>rótulos</b>. 

## Texto
- [ ] <b>Evitar</b> o uso de <b>textos dentro de imagens</b>. 
- [x] <b>Redimensiona os textos na página</b>, aumentando o zoom em até 200%. 
- [x] <b>Alturas </b> das fontes <b> não é fixa </b>. 

## Teclado
- [ ] <b> Funcionalidades </b> da página web estão <b> disponíveis por teclado </b>. 
- [ ] Quando se tem o <b>mouseover é permitido o uso de teclado </b>. 
- [ ] <b>Foco visível</b> remova elementos focalizáveis ​​invisíveis. 
- [ ] Adicione o <b> ``` .hover, .focus { } ```</b>  para tornar o foco visível. 
- [ ] Permite/visa o uso de <b> Atalhos de teclado </b> como o ```TAB```. 
- [ ] <b> Primeiro </b> item interativo da página é um link para o <b> conteúdo principal </b>. 
- [ ] **[NOVO WCAG 2.2]** O elemento que recebe foco de teclado **não fica completamente oculto** por cabeçalhos fixos (sticky headers), banners de cookies ou outros elementos sobrepostos feitos pelo autor — pelo menos parte do elemento focado deve ser visível. <a id="TEC_NEW1" href="#RP_NEW1">[N1]</a>
- [ ] **[NOVO WCAG 2.2]** Usar `scroll-margin-top` no CSS para garantir que cabeçalhos fixos não cubram o elemento em foco ao usar Tab: ```css scroll-margin-top: 80px; /* altura do header fixo */```. <a id="TEC_NEW1b" href="#RP_NEW1">[N1]</a>

## Título
- [ ] A <b>hierarquia</b> de conteúdo da página é definida por sua <b>lógica</b> não pelo tamanaho do texto. <a id="TEC17" href="#RP17">[17]</a>
- [ ] Use <b>elementos de título  ``` h1 h2 h3 ```</b> para apresentar o conteúdo.<a id="TEC17" href="#RP17">[17]</a>
- [ ] <b>Não pular níveis lógicos</b>.
- [ ] <b>Toda página contem um título  ``` h1 ```</b> descrevendo a página. <a id="TEC17" href="#RP17">[17]</a></b><a id="TEC19" href="#RP19">[19]</a>

## Tabela
- [ ] <b> Use o ``` table ``` </b> para elementos em formato de tabela.  <a id="TEC4" href="#RP4">[4]</a>
- [ ] Insira cabeçalhos para explicar os dados, <b>use ``` th ``` com  ``` scope ``` correto</b>.<a id="TEC15" href="#RP15">[15]</a>
- [ ] <b> Use o ``` captione ``` </b> lemento para fornecer um título para a tabela.<a id="TEC17" href="#RP17">[17]</a>

## Modais
- [ ] Deve ser <b> fácil fechar </b>.<a id="TEC19" href="#RP19">[19]</a>
- [ ] Permiti o <b> uso da tecla escape ``` ESC ```</b>.</b><a id="TEC19" href="#RP19">[19]</a>
- [ ] A interação é  uma <b> tarefa simples</b>.</b><a id="TEC19" href="#RP19">[19]</a>
- [ ] <b> Evita </b> modais em <b> tela cheia </b>.</b><a id="TEC19" href="#RP19">[19]</a>
- [ ] <b> Não abrir um modal a partir de outro modal </b>.</b><a id="TEC19" href="#RP19">[19]</a>

## Dispositivo Móvel e tocável
- [ ] O site pode ser <b> rotacionado </b> para qualquer orientação.  <a id="TEC15" href="#RP15">[15]</a>
- [ ] <b> Impedir </b> rolgem horizontal. <a id="TEC16" href="#RP15">[16]</a>
- [ ] <b> Garantir </b> que botões e links possam ser ativados facilmente. <a id="TEC18" href="#RP18">[18]</a>
- [ ] <b> Garantir </b> espaço suficiente entre elementos interativos. <a id="TEC7" href="#RP7">[7]</a>

## Ferramentas e extras
- [ ] Permiti <b> pausar, parar ou ocultar conteúdo em movimento </b>.
- [ ] Usar <b> Breadcrumbs </b> informando a localização atual nas páginas.
- [ ] Colocar página ou <b> área de esclarecimento de dúvidas e dicas de acessibilidade </b>.
- [ ] **[NOVO WCAG 2.2 – corrigido]** Áreas clicáveis com no mínimo **24×24 pixels CSS** de altura e largura (requisito AA, WCAG 2.5.8). O tamanho **44×44px** continua sendo a **recomendação** (nível AAA, WCAG 2.5.5). <a id="TEC_NEW2" href="#RP_NEW2">[N2]</a>
- [ ] **[NOVO WCAG 2.2 – corrigido]** Funcionalidades que exigem **arrastar (drag-and-drop)** devem ter alternativa operável por clique/toque único (ex: botões "Mover para cima/baixo"). <a id="TEC_NEW3" href="#RP_NEW3">[N3]</a>
- [ ] **[NOVO WCAG 2.2]** No caso de <b>captcha</b> garanta alternativas **sem testes cognitivos** (sem resolver quebra-cabeça, sem transcrição de texto distorcido): use magic link por e-mail, OAuth, biometria ou WebAuthn. <a id="TEC_NEW4" href="#RP_NEW4">[N4]</a>
- [ ] **[NOVO WCAG 2.2]** Em fluxos multi-etapa, **não re-solicitar dados** já fornecidos pelo usuário – pré-preencher campos ou oferecer seleção (exceto se essencial por segurança). <a id="TEC_NEW5" href="#RP_NEW5">[N5]</a>
- [ ] **[NOVO WCAG 2.2]** Se mecanismo de ajuda (chat, FAQ, telefone) estiver disponível em múltiplas páginas, deve aparecer na **mesma posição relativa** em todas. <a id="TEC_NEW6" href="#RP_NEW6">[N6]</a>
- [ ] Incluir um <b> campo de busca </b>.

## Referência Bibliográfica

> <a id="RP1" href="#TEC1">1.</a> WCAG 2.2 Understanding Docs. SC 1.1.1 Non-text Content (Level A) . Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/non-text-content.html](https://www.w3.org/WAI/WCAG22/Understanding/non-text-content.html). Acesso em: 9 Mai. 2024.

> <a id="RP2" href="#TEC2">2.</a> WCAG 2.2 Understanding Docs. SC 1.2.2 Captions (Prerecorded) (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html](https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html). Acesso em: 9 Mai. 2024.

> <a id="RP3" href="#TEC3">3.</a> WCAG 2.2 Understanding Docs. SC 2.3.1 Three Flashes or Below Threshold (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html). Acesso em: 9 Mai. 2024.

> <a id="RP4" href="#TEC4">4.</a> WCAG 2.2 Understanding Docs. SC 1.3.1 Info and Relationships (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships.html](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships.html). Acesso em: 9 Mai. 2024.

> <a id="RP5" href="#TEC5">5.</a> WCAG 2.2 Understanding Docs. SC 1.4.1 Use of Color (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html). Acesso em: 9 Mai. 2024.

> <a id="RP6" href="#TEC6">6.</a> WCAG 2.2 Understanding Docs. SC 2.4.7 Focus Visible (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html). Acesso em: 9 Mai. 2024.

> <a id="RP7" href="#TEC7">7.</a> WCAG 2.2 Understanding Docs. SC 2.4.1 Bypass Blocks (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/bypass-blocks.html](https://www.w3.org/WAI/WCAG22/Understanding/bypass-blocks.html). Acesso em: 9 Mai. 2024.

> <a id="RP8" href="#TEC8">8.</a> WCAG 2.2 Understanding Docs. G201 Giving users advanced warning when opening a new window. Disponível em: [https://www.w3.org/WAI/WCAG22/Techniques/general/G201](https://www.w3.org/WAI/WCAG22/Techniques/general/G201). Acesso em: 9 Mai. 2024.

> <a id="RP9" href="#TEC9">9.</a> WCAG 2.2 Understanding Docs. SC 3.2.2 On Input (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/on-input.html](https://www.w3.org/WAI/WCAG22/Understanding/on-input.html). Acesso em: 9 Mai. 2024.

> <a id="RP10" href="#TEC10">10.</a> WCAG 2.2 Understanding Docs. SC 1.3.5 Identify Input Purpose (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/identify-input-purpose.html](https://www.w3.org/WAI/WCAG22/Understanding/identify-input-purpose.html). Acesso em: 9 Mai. 2024.

> <a id="RP11" href="#TEC11">11.</a> WCAG 2.2 Understanding Docs. SC 3.3.1 Error Identification (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/error-identification.html](https://www.w3.org/WAI/WCAG22/Understanding/error-identification.html). Acesso em: 9 Mai. 2024.

> <a id="RP12" href="#TEC12">12.</a> WCAG 2.2 Understanding Docs. SC 1.4.2 Audio Control (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/audio-control.html](https://www.w3.org/WAI/WCAG22/Understanding/audio-control.html). Acesso em: 9 Mai. 2024.

> <a id="RP13" href="#TEC13">13.</a> WCAG 2.2 Understanding Docs. SC 2.1.1 Keyboard (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/keyboard.html](https://www.w3.org/WAI/WCAG22/Understanding/keyboard.html). Acesso em: 9 Mai. 2024.

> <a id="RP14" href="#TEC14">14.</a> WCAG 2.2 Understanding Docs. SC 1.3.4 Orientation (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/orientation.html](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html). Acesso em: 9 Mai. 2024.

> <a id="RP15" href="#TEC15">15.</a> WCAG 2.2 Understanding Docs. SC 4.1.1 Orientation (Level). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/parsing.html](https://www.w3.org/WAI/WCAG22/Understanding/parsing.html). Acesso em: 9 Mai. 2024.

> <a id="RP16" href="#TEC16">16.</a> WCAG 2.2 Understanding Docs. SC 1.4.10 Reflow (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/reflow.html](https://www.w3.org/WAI/WCAG22/Understanding/reflow.html). Acesso em: 9 Mai. 2024.

> <a id="RP17" href="#TEC17">17.</a> WCAG 2.2 Understanding SC 2.4.6 Headings and Labels (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels.html](https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels.html). Acesso em: 9 Mai. 2024.

> <a id="RP18" href="#TEC18">18.</a> WCAG 2.2 Understanding Docs. SC 2.5.5 Target Size (Enhanced) (Level AAA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html](https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html). Acesso em: 9 Mai. 2024.

> <a id="RP19" href="#TEC19">19.</a> GUIA DE BOAS PRÁTICAS PARA ACESSIBILIDADE DIGITAL. Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html](https://www.w3.org/WAI/WCAG22/Understandin/target-size-enhanced.html). Acesso em: 9 Mai. 2024.

> <a id="RP_NEW1" href="#TEC_NEW1">N1.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 2.4.11 Focus Not Obscured (Minimum) (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum.html](https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum.html). Acesso em: jun. 2026. | NBR 17225:2025 (5.1.1, 5.1.3)

> <a id="RP_NEW2" href="#TEC_NEW2">N2.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 2.5.8 Target Size (Minimum) (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html). Acesso em: jun. 2026. | NBR 17225:2025 (5.8.7)

> <a id="RP_NEW3" href="#TEC_NEW3">N3.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 2.5.7 Dragging Movements (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/dragging-movements.html](https://www.w3.org/WAI/WCAG22/Understanding/dragging-movements.html). Acesso em: jun. 2026. | NBR 17225:2025 (5.8.13)

> <a id="RP_NEW4" href="#TEC_NEW4">N4.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 3.3.8 Accessible Authentication (Minimum) (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/accessible-authentication-minimum.html](https://www.w3.org/WAI/WCAG22/Understanding/accessible-authentication-minimum.html). Acesso em: jun. 2026. | NBR 17225:2025 (5.9.18)

> <a id="RP_NEW5" href="#TEC_NEW5">N5.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 3.3.7 Redundant Entry (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/redundant-entry.html](https://www.w3.org/WAI/WCAG22/Understanding/redundant-entry.html). Acesso em: jun. 2026. | NBR 17225:2025 (5.9.15)

> <a id="RP_NEW6" href="#TEC_NEW6">N6.</a> **[NOVO WCAG 2.2]** WCAG 2.2 Understanding Docs. SC 3.2.6 Consistent Help (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/consistent-help.html](https://www.w3.org/WAI/WCAG22/Understanding/consistent-help.html). Acesso em: jun. 2026. | NBR 17225:2025 (5.7.15)

## Bibliografia

> </a> DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R. Guia de Boas Práticas para Acessibilidade Digital. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023. Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf). Acesso em: 9 Mai. 2024.