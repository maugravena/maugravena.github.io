---
layout: post
title: "RSCSS - CSS de uma formar sensata"
date: 2019-04-15
categories: css
---

Como o próprio nome já diz RSCSS (Reasonable System for CSS Stylesheet Structure) é uma espécie de sistema para estruturar seu código CSS e deixá-lo razoavelmente compreensível e organizado.

Com um conjunto de ideias simples podemos guiar nosso processo de construção para um CSS de fácil manutenção (não gosto da palavra manutenível xD). Isso é muito importante pois nossos projetos inevitavelmente terão uma grande quantidade de linhas em CSS e assim podemos cair em algumas armadilhas comuns como por exemplo o motivo da criação de uma classe e o que ele significa exatamente. Dito isso, sabemos que pensar na organização do CSS nos ajudará a manter e melhorar nosso código futuramente.

Existem alguns conceitos que são a base do RSCSS que são: Components, Elements, Variants, Layout e Helpers. Vamos ver cada item em detalhes a seguir.

## Componentes (Components)

Quando trabalhamos com RSCSS temos que pensar em Componentes. Cada pedaço da nossa UI (user interface) será considerada um componente individual.

A nomeação dos componentes precisa de uma atenção especial e existe uma regra específica para eles, nosso componente deve ter pelo menos duas palavras com um traço entre elas. Um exemplo:

* Um campo de pesquisa  .search-form
![Exemplo de componente](/assets/img/component-example.png)

## Elementos (Elements)
Os elementos ficam dentro dos componentes, ou seja, são filhos diretos dos componentes. Assim podemos ter mais de um elemento contido em um componente.

Aqui a regra de nomeação é um pouco diferente, eles devem ter uma classe com apenas uma palavra e caso haja necessidade de se usar duas ou mais palavras, a junção deve ser feita sem o uso de traços ou sublinhados (underscores).

### Seletores de elemento (Element selectors)
É recomendado o uso do seletor filho (child selector) sempre que possível, isso é útil para prevenir o “vazamento” de estilos para os componentes aninhados, e também tem melhor performance que os seletores descendentes.

## Variações (Variants)
Os componentes podem ter variações assim como os elementos. Isso seria um tipo de customização, uma forma de modificar seu estilo criando um componente/elemento com algumas características diferentes.

A nomeação das classes de variantes são prefixados por um traço.

![Modificadores de componente](/assets/img/component-modifiers.png)

## Auxiliares (Helpers)
Por último vamos falar dos helpers que são classes de propósito geral destinadas a substituir valores. Coloque-os em um arquivo separado e seus nomes devem começar com um underscore ( _ ). É comum marcá-lo como !important. Use-os com muito cuidado, o uso de muito helpers é uma má prática e deve ser desencorajada.

## Layouts
Temos que ter o cuidado de deixar os nossos componentes o mais genérico possível para que possamos utilizá-los em diferentes contextos. Assim, devemos evitar o uso de propriedades como: Posicionamento (position, top, left, right, bottom), Floats (float, clear), Margem e Dimensões (width, height).

Caso seja necessário utilizar algum tipo de posicionamento, tente defini-los no contexto em que estão envolvidos, por exemplo,  aplique as propriedades no componente pai e não no componentes em si.

## Conclusão
Achei essa forma de pensar em como devemos escrever nosso CSS muito interessante, com esse sistema conseguimos estruturar e organizar melhor o nosso código, além de termos mais controle na manutenção e refatoração do nosso CSS no futuro.

#### Fonte:
 - RSCSS - Styling CSS without losing your sanity - <https://rscss.io>
 - CSS Formatting - <https://kolosek.com/css-formatting/>
 - RSCSS: Writing CSS without losing your sanity - <https://www.youtube.com/watch?v=tY2UQPZAK14>
