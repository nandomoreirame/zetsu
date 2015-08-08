---
layout: post
title: Como fazer Accordion Simples com jQuery em 5 linhas de código
date: 2011-11-03 11:44
comments: true
categories:
- css
tags:
- css
- dicas
- html
- jquery
---

O accordion, também conhecido como "menu sanfona", serve para estruturar conteúdo em tópicos. Ele é bem simples de fazer, a maioria das pessoas que visitam devem saber fazer de olhos vendados. E com a biblioteca jQuery no seu site, é possível fazer um accordion com apenas 5 linhas de código.

Veja os exemplos que também ensinam como fazer:

#### Código em jQuery

{% highlight javascript %}
$(document).ready(function(){
  $('h2.accordion').click(function(){
    $(this).parent().find('div.accordion').slideToggle("slow");
  });
});
{% endhighlight %}

#### A estrutura em HTML

{% highlight html %}
<div class="exemplo">
  <h2 class="accordion">Título/h2>
  <div class="accordion">
    <p> texto de descrição </p>
  </div>
</div>
{% endhighlight %}

#### O CSS

{% highlight css %}
h2.accordion {
  cursor: pointer;
}
div.accordion {
  display: none;
}
{% endhighlight %}

<small>Fonte: [tidbits.com.br](http://www.tidbits.com.br/)</small>
