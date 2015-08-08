---
layout: post
title: Forçando download com PHP
date: 2011-11-03 06:15:46.000000000 -02:00
categories:
- php
tags:
- dicas
- php
- programacao
comments: true
cover: '/assets/images/posts/php-default.jpg'
---


Primeiramente precisamos montar o arquivo <em><code>"download.php".</code></em>

{% highlight php %}
<?php
  $file = $_GET['arquivo'];
  header("Content-Type: application/save");
  header("Content-Length:".filesize($file));
  header('Content-Disposition: attachment; filename="' . $file . '"');
  header("Content-Transfer-Encoding: binary");
  header('Expires: 0');
  header('Pragma: no-cache');
  $fp = fopen("$file", "r");
  fpassthru($fp);
  fclose($fp);
?>
{% endhighlight %}


Agora precisamos chamar o nosso arquivo em nosso HTML.

{% highlight html %}<a href="download.php?arquivo=aula.pdf">Download</a>{% endhighlight %}

Espero ter ajudado.

Um forte abraço e fiquem com Deus!
