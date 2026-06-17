# Ferramentas Utilizadas

## Lighthouse

O Lighthouse é uma ferramenta integrada aos navegadores baseados em Chromium utilizada para auditoria automática de páginas web.

### Configuração

* Navegador: Brave Browser
* Categoria avaliada: Accessibility
* Modo: Mobile
* Página analisada: Unidade Brasília-DF do site Sabin

### Resultado

A página analisada obteve pontuação de **93/100** em acessibilidade.

### Problemas Identificados

#### Links sem nome discernível

Foram encontrados links sem nome acessível adequadamente definido, dificultando a interpretação por tecnologias assistivas.

**Referência:** WCAG 2.2 – Critério 4.1.2 (Name, Role, Value)

#### Área de toque insuficiente

Foram identificados elementos interativos com tamanho ou espaçamento reduzido para interação em dispositivos móveis.

**Referência:** WCAG 2.2 – Critério 2.5.8 (Target Size – Minimum)

### Evidências

![Pontuação de acessibilidade do Lighthouse](../assets/nota-Lighthouse.png)

![Links sem nome acessível identificados pelo Lighthouse](../assets/links-Lighthouse.png)

![Problemas de melhores práticas identificados pelo Lighthouse](../assets/best-LightHouse.png)

---

## WAVE

O WAVE (Web Accessibility Evaluation Tool) foi utilizado para complementar a avaliação automática de acessibilidade e identificar problemas relacionados à estrutura semântica, textos alternativos e contraste.

### Resultados Gerais

| Categoria           | Quantidade |
| ------------------- | ---------- |
| Errors              | 9          |
| Contrast Errors     | 5          |
| Alerts              | 10         |
| Features            | 108        |
| Structural Elements | 68         |
| ARIA                | 426        |

### Erros Encontrados

#### Linked Image Missing Alternative Text

Foram identificadas 4 imagens utilizadas como links sem texto alternativo.

**Referência:** WCAG 2.2 – Critério 1.1.1 (Non-text Content)

#### Broken ARIA Reference

Foram identificadas 5 referências ARIA inválidas.

**Referência:** WCAG 2.2 – Critério 4.1.2 (Name, Role, Value)

### Problemas de Contraste

Foram identificados 5 elementos com contraste muito baixo entre texto e fundo.

**Referência:** WCAG 2.2 – Critério 1.4.3 (Contrast Minimum)

### Alertas Encontrados

* 1 texto alternativo redundante;
* 1 texto alternativo suspeito;
* 1 ausência de cabeçalho de primeiro nível (H1);
* 1 salto na hierarquia de títulos;
* 6 links redundantes.

### Evidências

![Resumo da análise do WAVE](../assets/nota-Wave.png)

![Erros encontrados pelo WAVE](../assets/erros-Wave.png)

![Alertas encontrados pelo WAVE](../assets/alertas-Wave.png)

![Problemas de contraste identificados pelo WAVE](../assets/contraste-Wave.png)

![Problemas adicionais de contraste identificados pelo WAVE](../assets/contraste2-Wave.png)
