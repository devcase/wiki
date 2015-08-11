---
layout: post
title:  "Melhorando a velocidade de seu site"
date:   2015-08-11 13:32:38
categories: web
excerpt: Ferramentas e técnicas para melhorar o tempo de carregamento de seu site.
author: Thiago Hirata
---

## Ferramentas para analisar a velocidade de sua página

Se seu website já está na Internet, seguem duas ferramentas que o ajudarão a identificar potenciais problemas e pontos a trabalhar:

  * [https://developers.google.com/speed/pagespeed/insights/](https://developers.google.com/speed/pagespeed/insights/)
  * [GT Metrix](https://gtmetrix.com/)
  
## Compactação de imagens

### PNG

Sem você perceber, seu website pode conter imagens PNG que ocupam muito mais espaço que o necessário. O **[PNGOUT](http://www.advsys.net/ken/util/pngout.htm)** é um programa que compacta imagens PNG sem perder qualidade.

Se você usa o Windows, siga o seguinte passo-a-passo:

   1. Faça o download do [PNGOUT.EXE](http://advsys.net/ken/util/pngout.exe) - escolha uma pasta de destino local, como `c:\users\{???}\bin`
   2. Adicione o diretório onde você gravou o PNGOUT.exe na variável de ambiente PATH ([veja como](https://www.java.com/pt_BR/download/help/path.xml))
   3. Abra o prompt de comando `cmd.exe`
   4. Vá até o diretório onde estão os arquivos png de seu site (ex: `cd c:\users\{???}\git\devcasewiki\images\`)
   5. Faça o backup dos arquivos!
   5. Execute o comando `for %i in (*.png) do pngout "%i" /kp`

### JPEG
 
Se seus arquivos de foto JPEG estão ocupando mais de 1 mega, seu site ficará muito lento para acessar pela rede móvel. O **[cjpeg](http://mozjpeg.codelove.de/binaries.html)** vai ajudar a comprimir suas imagens JPEG - em troca de uma pequena redução da qualidade.

   1. Faça o download do arquivo [libmozjpeg_3.0_x86.zip](http://mozjpeg.codelove.de/bin/libmozjpeg_3.0_x86.zip)
   2. Descompacte o conteúdo do arquivo em uma pasta local (sugestão: `c:\users\{???}\bin`)
   3. Adicione a pasta na variável de ambiente PATH
   4. Vá até o diretório onde estão os arquivos png de seu site (ex: `cd c:\users\{???}\git\devcasewiki\images\`)
   5. Execute o comando `cjpeg -quality 80 imagem1.jpg > imagem1-compressed.jpg`
   6. Compare o arquivo original e o novo arquivo antes de substituir

   
## Carregando arquivos javascript e css

Em seu HTML, evite colocar as tags de css e javascript dentro da tag `<head>` - prefira colocar essas tags após o fechamento da tag `<html>`.



Exemplo: 
{% highlight html %}
<html>
    <head>
        <!-- conteúdo do head aqui -->
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css"> <!-- Este é o único CSS no cabeçalho -->
    </head>
    <body>
        <!-- conteúdo do body aqui -->
    </body>
</html>
<link href="/css/carousel.css" rel="stylesheet">
<link rel="stylesheet" href="/css/tusite-style.css">
<link href='http://fonts.googleapis.com/css?family=Cabin:400,400italic,500,500italic,600,600italic,700,700italic' rel='stylesheet' type='text/css'>
<link href='http://fonts.googleapis.com/css?family=Open+Sans:300,400' rel='stylesheet' type='text/css'>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js"></script>
<script src="https://code.jquery.com/ui/1.11.4/jquery-ui.min.js"></script>	
{% endhighlight %}
   