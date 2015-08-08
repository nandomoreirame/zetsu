---
layout: post
title: "10 dicas de otimização em programação PHP"
date: 2011-11-03 12:27
description: "10 dicas de otimização em programação PHP"
keywords: "Dicas, PHP, Programação"
comments: true
categories:
- php
- programacao
tags:
- dicas
- php
- programacao
cover: '/assets/images/posts/php-default.jpg'
---

**1** - Usar `echo` ao invés de `print`.

**2** - Usar argumentos no echo ao invés de concatenar. Ex.:

{% highlight php %}
<?php
echo 'Meu programa ',$nome,' funciona perfeitamente.'
?>
{% endhighlight %}

**3** - Prefira sempre usar aspas simples (') ao invés de aspas duplas ("), pois quando se usa aspas simples o PHP trata como uma string literal, ou seja, não vai interpretá-la. Portanto, se não precisar, não use aspas duplas. Ex.:

{% highlight php %}
<?php
$registros = 100;

echo 'Total de $registros';
// resultado: Total de $registros

echo "Total de $registros";
// resultado: Total de 100
?>
{% endhighlight %}

**4** - Use `require` ao invés de `require_once`.

**5** - Evite de usar `@` antes das variáveis ou outros lugares para suprimir as mensagens de erros.

**6** - Em array, `$linha['id']` é até 7 vezes mais rápido do que `$linha[id]`.

**7** - Evite de usar `for($i=0; $i &lt; count($_linhas); $i++`. Use:

{% highlight php %}
<?php
$total = count($_linhas);
for($i = 0; $i < $total; $i++) {

}
?>
{% endhighlight %}

Pois o `for` sempre irá executar a função count, pesando na velocidade do seu programa.

**8** - Habilite o `mod_deflate` do apache, você poderá ganhar consumo de banda, ou seja, ele vai comprimir os dados para ser enviado para o cliente (navegador). Dependendo da página, poderá ter uma compressão perto dos 90%. Assim sendo, economia de banda, e carregamento mais rápido para o cliente.

**9** - Prefira sempre usar HTML se não tiver nada de dinâmico na sua página, pois scripts PHP podem ser de 2-10 vezes mais lento.

**10** - Com uso de banco de dados, também prefira por usar cache de objetos ou resultados, se está tendo muitas consultas no Banco de Dados, pode ser que uma hora o seu banco de dados não suporte muitas requisições simultâneas, então com cache poderá diminuir em muito estas requisições e assim melhorando a velocidade de respostas. Procure por `memcache`, este é bom para isso.

<small>Fonte: <a href="http://www.vivaolinux.com.br/" target="_blank">http://www.vivaolinux.com.br</a></small>