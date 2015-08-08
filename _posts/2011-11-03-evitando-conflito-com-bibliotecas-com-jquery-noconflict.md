---
layout: post
title: Evitando conflito com bibliotecas com jQuery.noConflict
date: 2011-11-03 06:14
description: "Muitas vezes necessitamos utilizar mais de uma biblioteca jQuery em nossos projetos, e quanto mais bibliotecas na em uma página corre-se o risco de ter conflito entre elas, ocorrendo assim um mal funcionamento"
keywords: "jQuery, Dicas, Programação, noConflict"
comments: true
categories:
- jquery
tags:
- dicas
- jquery
- programacao
---

Muitas vezes necessitamos utilizar mais de uma biblioteca **jQuery** em nossos projetos, e quanto mais bibliotecas na em uma página corre-se o risco de ter conflito entre elas, ocorrendo assim um mal funcionamento.

Para resolvermos esse problema podemos utilizar uma função própria do jQuery – `jQuery.noConflict().`

Os conflitos  ocorrem porque as diferentes bibliotecas, com diferentes métodos, usam uma sintaxe comum para chamar suas funcionalidades(o alias $ ou o construtor $()), o que faz com que as diferentes bibliotecas tentem interpretar o mesmo código, criando estes conflitos.

Eu geralmente crio um arquivo externo chamado `funcoes.js` e nele coloco as funções das bibliotecas aplicadas no site.

Logo na primeira linha do arquivo `funcoes.js` adiciono a função `jQuery.noConflict()` em uma variável.

{% highlight javascript %}
var $j = jQuery.noConflict();
{% endhighlight %}

E em todas funções substituímos o `$` (dólar) pela variável criada. Ficaria assim:

Antes...

{% highlight javascript %}
$(document).ready(function(){
  $(".logos-apoio").jCarouselLite({
    auto: 500
  });
});
{% endhighlight %}

Depois...

{% highlight javascript %}
var $j = jQuery.noConflict();
$j(document).ready(function(){
  $j(".logos-apoio").jCarouselLite({
    auto: 500
  });
});
{% endhighlight %}

É isso ai! Espero ter ajudado e um forte abraço.
