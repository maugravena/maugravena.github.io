---
layout: post
title: "ITCSS - Uma arquitetura para CSS"
date: 2019-04-15
categories: css
---

## O que é ITCSS?

* ITCSS - Inverted triangle ITCSS
* Metodologia que ajuda na arquitetura de código CSS
* Não temos oficialmente um padrão onde os desenvolvedores podem se basear para a construção de projetos.

ITCSS siginifica *Inverted Trangle CSS*, que é uma metodologia que ajuda na arquitetura e organização do seu código. Com ele você pode controlar alguns aspectos do CSS que podem deixar o seu desenvolvimento confuso, esses aspectos são: sua naureza global, "efeito cascata" e a especificidade de seletores. Ela é muito flexível e compatível com várias outras metodologias como SMACSS, OOCSS, RSCSS e BEM.

* Trabalha juntamente com uma arquitetura de UI componentizada
* Não utiliza IDs
* O triâgulo invertido é separado em várias camadas onde cada uma tem sua função

É importante pensar em uma arquitetura de UI componentizada, além disso temos que separar nossos códigos em camadas, onde cada camada tem uma função bem definida. Se pensarmos na organização do nosso projeto, cada camada vai representar uma pasta diferente.

![Invered Triangle](/assets/img/inveted-triangle.jpg)

Essas camadas são as seguintes:

* **Settings** - Configurações globais, contém fontes, definições de cores, etc.

* **Tools** - Mixins e funções. Ex: Gradient mixins, font-sizing.

* **Generics** - É a primeira camada que realmente produz código CSS, essa é uma camada raramente modifidaca e pode ser usada em outros projetos. Contém o Normalize.css, regras de box-sizing globais e Resets.

* **Elements** - É onde fica elementos HTML sem classe, é uma camada raramente modificada depois do setup inicial

* **Objects** - Primeira camada onde encontramos seletores de classe, por isso é uma camada com maior especificidade. Pode conter algo simples como um elemento *.wrapper*, e seu uso pode ser descartado caso você não esteja utilizando OOCSS.

* **Components** - Aqui começamos a estilizar de fato nossos "padaços" da UI. Continuamos a usar classes aqui, então nossa especificidade não foi aumentada. É onde a maioria do nosso trabalho acontece.

* **Utilities** - "Derruba" ou "supera" todas as outras camadas, tem o poder de sobrescrever todas as anteriores. Isso é muito deselegante, então deve ser utilizada com muita cautela. Contém classes utilitárias e auxiliares e é a camada com maior especificidade, formando a ponta do triângulo.

Na representação do triaĝulo invertido teremos um fluxo que vai de cima para baixo, onde existe 3 pontos principais nesse fluxo:

 1. Genérico para explícito
 2. Baixa especificidade para alta especificidade
 3. Amplo alcance para localizado

## Conclusão

Essa abordagem nos ajuda a criar uma arquitetura CSS muito mais fácil de manejar, além de controlar alguns aspectos confusos do CSS.
Sabemos onde cada regra deve estar e onde colocar nossos estilos, assim temos certeza de que todos seletores vão funcionar sem interferir uns aos outros.

#### Fonte
<https://www.creativebloq.com/web-design/manage-large-css-projects-itcss-101517528>

<https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/>
