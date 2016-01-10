---
layout: post
fb_type: article
fb_section: Tutorials - Jekyll
title: O que é Jekyll - e para que ele serve
fb_title: O que é Jekyll - e para que ele serve
categories: [jekyll, Github, Blog, Tutoriais]
tags: [jekyll, git, blog, markdown]
meta_keywords: jekyll, git, blog, blogs, markdown
description: Entenda o que é Jekyll e porque tem tanta gente que usa.
image: https://goo.gl/OhXc4z
image_schema: 'https://c1.staticflickr.com/1/750/20337135198_51ac94d762_b.jpg'
imageUrl: https://goo.gl/loSOe4
author: Marcia Ramos
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
author_fb: marciaramosmdr
author_twitter: xmdramos
authorEmail: virtua.creative@gmail.com
comments: true
date: 2015-08-17 22:32:11 UTC
date_update: 2016-01-09 00:16:02 UTC
# language: [en_US, en_UK]
---

# **O que é Jekyll**

**[Jekyll](http://jekyllrb.com/)** é um programa que permite a criação de websites e blogs utilizando apenas **html**, **css** e **javascript**. Websites em Jekyll são escritos utilizando três tecnologias de programação: **[Liquid Templating Language](https://github.com/Shopify/liquid/wiki)**, **[Yaml](https://pt.wikipedia.org/wiki/YAML)** e **[Markdown](https://guides.github.com/features/mastering-markdown/)**, que são então automaticamente compiladas para formar páginas em html. 

<br>

### **Markdown**

Markdown é uma linguagem simplificada para escrever arquivos publicados em websites. Por exemplo, em `html` usa-se a tag _strong_ `<strong>Texto</strong>` para marcar palavras e frases em negrito. No markdown utilizado pelo Jekyll, o mesmo propósito é atingido apenas com dois asteriscos `**` antes e depois do texto que se deseja em negrito:

{% highlight html %}
**Texto**
<!-- é compilado para: -->
<strong>Texto</strong>
{% endhighlight %}

No nosso artigo **[Jekyll e GitHub Markdown]({{ site.baseurl }}{% post_url 2015-08-02-jekyll-github-markdown %})** você poderá encontrar uma lista completa dos markdowns utilizados com mais frequência ao escrever em Jekyll.

O arquivo em markdown pode ter algumas extensões. A mais abreviada e utilizada é `.md`. Para se ter uma ideia do quanto este tipo de arquivo é utilizado, o Github utiliza a extensão `.md` em todos os seus `README`. Portanto, o arquivo `.md` pode ser utilizado como está, como no caso do Github, ou, como no caso do Jekyll, poderá ser compilado para formar um html "normal", com todas as tags em html.

<br>

### **Yaml**

O Yaml é utilizado para definir as configurações e como seu site será compilado. Para isso, existe na pasta raíz um arquivo de configuração chamado `_config.yml`. Neste arquivo você definirá as configuração para todo o site - e não para arquivos individuais.

Há uma série de configurações padrão que você pode aplicar no seu website e recuperá-las com facilidade utilizando a [Liquid](#liquid), próximo tópico deste artigo. Há outras variáveis que você mesmo poderá definir e recuperar com a mesma facilidade. Basta entender a lógica que você aprenderá a usá-las e poderá ver como são úteis.

<br>

#### **<mkp-blue>_config.yml</mkp-blue>**

Neste arquivo `_config.yml`, você definirá variáveis do seu site, como por exemplo:
 - Título da Home Page
 - Descrição da Home Page
 - Autor (do site)

Além das variáveis comuns você deverá configurar o seguinte:
  - _<mkp-blue>baseurl</mkp-blue>_ = é o caminho padrão do seu site, ou seja, o domínio que você vai utilizar para seu site
  - _<mkp-blue>markdown</mkp-blue>_ = qual é o tipo de markdown você vai utilizar nos seus arquivos
  - _<mkp-blue>exclude</mkp-blue>_ = é um parâmetro para excluir da compilação arquivos que você não deseja que façam parte do seu site

No fim, você terá seu `_config.yml` parecido com este exemplo:

{% highlight yaml %}
---
markdown: kramdown
exclude: ["README.md"]

title: Meu website interessante
description: Vamos falar de coisas interessantes por aqui!
author: Meu Nome

baseurl: http://meudominio.com.br
---
{% endhighlight %}

Este é apenas um exemplo simples de configuração. Conforme você vai aprendendo a usar as ferramentas do Jekyll, você vai atribuindo mais variáveis ao seu `_config.yml`. 

Note que __não há espaço__ entre a variável e o começo da linha e que há apenas __um espaço__ entre os `:` e o valor da variável. Estes espaços devem ser estritamente respeitados, sob pena de gerar erros difíceis de encontrar no futuro. Isso acontece porque você poderá usar espaços para definir vários atributos a uma única variável. Mas não vamos aprofundar este detalhe neste artigo introdutório. Fica a menção apenas para que você tome cuidado com os espaços e símbolos e detalhes deste tipo na hora de escrever em partes `Yaml` do seu novo projeto em Jekyll.

<br>

#### **<mkp-blue>Arquivos individuais</mkp-blue>**

Os arquivos individuais são compostos por duas partes: a parte superior, ou __cabeçalho yaml__, e o corpo - em html ou markdown.

A parte do cabeçalho define as __variáveis particulares daquela página em questão__. Por exemplo, se o seu website vai comportar um blog, você terá o autor da obra - do website - e o autor dos artigos publicados no blog. Desta forma, você terá dois tipos de variáveis, ambas chamadas "autor": uma será autor do __site__ e outra autor do __post__. Para chamá-las ao longo do website, basta especificar de qual você está falando, utilizando a linguagem [Liquid](#liquid) apropriada.

As suas páginas individuais deverão conter sempre a seguinte estrutura:

{% highlight yaml %}
---
configurações específicas da página
---

Texto da página
{% endhighlight %}

Neste link você poderá encontrar toda a [documentação do Yaml](http://www.yaml.org/start.html). Nesta página para a qual o link aponta, você poderá ver o quão útil ela poderá tornar-se para seu website.

Neste link você encontrará o [tutorial do Jekyll](http://jekyllrb.com/docs/frontmatter/) sobre o uso do Yaml.

<br>
<a name="liquid"></a>

### **Liquid**

A **Liquid** é uma ferramenta excelente para trabalhar com textos que se repetem ao longo de um website. Podemos considerá-lo o "irmão" dos `php includes` para **html**. A Liquid dinamiza o conteúdo do website, assim como muitos desenvolvedores fazem utilizando o php.

<br>

#### **<mkp-blue>Variáveis</mkp-blue>**

Por exemplo, se você deseja repetir a informação de uma url única ao longo do site, você poderá atribuir a ela uma variável no arquivo _config.yml:

{% highlight yaml %}
---
...suas configurações...

my_url: meudominio.com.br/meuarquivo.html

...suas configurações...
---
{% endhighlight %}

...e repeti-la ao longo do site utilizando uma chamada para o objeto:

{% highlight yaml %} 
<a href"{% raw %}{{ site.my_url }}{% endraw %}">My url title</a> => em arquivos .html
ou
[My url title]({% raw %}{{ site.my_url }}{% endraw %})  => em arquivos .md
{% endhighlight %}

Obs.: _Talvez tenha ficado confuso e você se pergunte: "mas eu vou escrever em html ou markdown?"_ Ambos. _Alguns arquivos são escritos diretamente em html. Mas não vamos aprofundar a estrutura de arquivos do Jekyll neste momento._

Digamos que você tenha que alterar esta url que você tinha inserido. Ao invés de ter que procurar e alterar manualmente todas as tags que a contém no seu wesite, utilizando o Liquid você altera apenas nas configurações e pronto! Sua alteração será repetida em todo o site:

{% highlight yaml %}
---
...configurações...

my_url: meudominio.com.br/meu_NOVO_arquivo.html

...configurações...
---
{% endhighlight %}

Note que a chamada para esta variável utiliza a marcação `site.` precedente à variável em si. Esta é a chave da Liquid. Para as variáveis do **site**, que se encontram no `_config.yml`, as chamadas são precedidas pela palavra `site.`. Para recuperar as variáveis de uma página individual, a chamada será através da marcação `page.`. Portanto, complementando o exemplo que demos acima em relação à autoria do site e de um artigo, as chamadas ao objeto seriam feitas da seguinte forma:

{% highlight yaml %} 
{% raw %}{{ site.author }}{% endraw %} => refere-se ao autor do site
{% endhighlight %}

{% highlight yaml %} 
{% raw %}{{ page.author }}{% endraw %} => refere-se ao autor do artigo
{% endhighlight %}

<br>

#### **<mkp-blue>Funcionalidades</mkp-blue>**

Mais uma vantagem em relação ao `php` é que cada `php include` faz um _request_ para um arquivo diferente, enquanto a Liquid não: todos os _"includes"_ são processados quando o site é compilado para html. Portanto, você escreve com dinamismo e publica com estaticidade! É tão bom quanto parece! :smiley:

Além dos _"includes"_, a Liquid também tem seus análogos para `if`, `else` e `elseif`, para `arrays` e para `loops`.

A **[Liquid Templating Language](https://docs.shopify.com/themes/liquid-documentation/basics)** possui uma estrutura que pode ser muito explorada e utilizada com muita praticidade. Siga o link para um ver um panorama completo sobre esta linguagem.

<br>

#### **<mkp-blue>Compilação</mkp-blue>**

A compilação do website se dá de forma automática. Basta executar o comando `jekyll serve` no seu prompt de comando que o seu html será gerado automaticamente - na pasta `_site`. Mas abordamos melhor este assunto no artigo **[Criando Blogs com Jekyll no Windows]({{ site.baseurl }}{% post_url 2015-07-30-jekyll-github-blog %})**.

<br>

<hr/>

# **Por que usar o Jekyll**

Após a introdução que acabamos de fazer, imagino que você já tenha entendido boa parte da funcionalidade e praticidade que o Jekyll provê. Mas, caso você ainda se sinta perdido no assunto, segue neste tópico uma série de motivos interessantes.

<br>

### **Blogs sem bases de dados**

Sempre que criamos um blog, há necessidade de haver uma forma de chamar cada artigo. Normalmente, utilizamos as variávies criadas em php para estabelecer as dependências.  Entretanto, caso haja necessidade de publicar o seu site em html, não há como utilizar o php. Toda página que contém alguma parte em php deve conter a extensão `.php`. Caso contrário, o código php não funcionará. Além disso, costumamos utilizar uma base de dados para inserir os conteúdos e recuperá-los depois.

Com o Jekyll, como explicado anteriormente, há a possibilidade de dinamizar o conteúdo e, mais interessante ainda, não há necessidade da criação de uma base de dados, o que o torna absolutamente seguro, livre de ataques conhecidos como "injections", que podem ocorrer via php / SQL.

Além dos casos que comentamos acima, a Liquid permite a inserção dinâmica de dados como data, hora e localização geográfica.


<br>

### **Hospedagem gratuita no GitHub**

Mais interessante ainda para quem deseja publicar blogs, é que o Jekyll é suportado pelo [GitHub Pages][github-pages], permitindo assim que websites e blogs escritos em Jekyll sejam hospedados gratuitamente no GitHub. Há vários outros provedores de blogs, mas via de regra é necessário que você se adeque aos layouts deles, sem muita interatividade com seu próprio código e design. Por isso, a escrita de blogs em Jekyll tem se propagado imensamente pela internet. Você termina com um blog absolutamente seguro - pois é publicado em html - e totalmente personalizado.

<br>

### **Agilidade para escrita e publicação**

Além da segurança e personalização, depois que você pega a prática, escrever em markdown fica muito mais rápido que em html. Pensa quantas tags eu não precisei abrir e fechar ao escrever este artigo!

Depois de escrito o artigo, caso você use o GitHub Pages, basta fazer um "git commit" do `.md` para o seu repositório que seu blog será compilado e publicado em html. Não tem mistério.

Caso não queira publicar o blog com GitHub, mas queira usar seu código no seu domínio hospedado em um servidor Apache, por exemplo, basta copiar o conteúdo da pasta `_site` e colar no seu `public_html` via FTP e pronto, seu blog estará atualizado. 
<br>

<hr/>

# **Jekyll para Profissionais**

<br>

### **Jekyll para Web Designers**


O Jekyll combina muito bem com preprocessadores como o **Sass**. E você pode turbinar o Sass com o Bourbon, Bitter, Neat, Animate... conforme preferir! Além de você poder montar seu CSS da melhor forma possível com essa ferramenta fantástica de design, seus arquivos `.sass` ou `.scss` são convertidos em css pelo comando `jekyll serve`. Você não precisa nem rodar um `sass --watch` no seu prompt! 

Basta definir a variável no `_config.yml` (conforme abaixo), colocar todos os arquivos que serão processados na pasta `_sass` do seu projeto Jekyll e pronto, o programa faz o resto pra você! 

{% highlight yaml %} 
---
sass:
    sass_dir: _sass
---
{% endhighlight %}

Você pode ainda escolher como quer que o css seja compilado: da forma expandida ou comprimida, basta inserir mais uma linha no arquivo de configuração:

{% highlight yaml %} 
---
sass:
    style: :compressed
---
{% endhighlight %}

A leitura da [documentação do Jekyll](http://jekyllrb.com/docs/assets/) que explica o assunto **SASS** em detalhes, incluindo como trabalhar com "imports" **é fundamental** para estruturar o projeto corretamente. 

<br>

### **Jekyll para Desenvolvedores Web**

Além das funcionalidades da Liquid, com inserção de __variáveis__, trabalho com __dados__, __coleções de dados__, __variáveis múltiplas__ e mais um monte de **[atrativos](http://webdesign.tutsplus.com/tutorials/getting-started-with-liquid-shopifys-template-language--cms-19747)** para qualquer desenvolvedor, há ainda editores de códigos que podem facilitar a vida de **autores de artigos** de blog em Jekyll. 

Particularmente, eu sou fã do Dreamweaver, mas o [Brackets](http://brackets.io/) é um editor muito interessante, pois é leve, gratuito, não costuma dar panes e é muito fácil de usar. Você poderá facilmente indicá-lo aos autores do blog. Utilizando os highlights para arquivos markdown fica muito simples de escrever. 

O [Sublime](http://www.sublimetext.com/) é outro editor de texto muito interessante. Seu uso não é tão imediato como o Brackets, mas há quem diga que é um dos melhores editores de código do mercado. O que ele provê de mais interessante (para o caso em questão) é uma extensão chamada [Sublime-Jekyll](https://packagecontrol.io/packages/Jekyll) que permite que você trabalhe muito mais facilmente com o Jekyll. Este pacote de extensão permite criar novos posts com todo o cabeçalho superior previamente estruturado, criar rascunhos e facilmente promovê-los a artigos, inserir data e hora com apenas dois comandos no teclado e assim por diante.

Portanto, caso você seja um desenvolvedor e pense duas vezes antes de escrever em Jekyll a estrutura de **blogs para terceiros**, pode ficar tranquilo. Mesmo que você mesmo tenha que publicar os artigos para seu cliente, transformar um arquivos de texto em markdown é "uma passada", e um _git commit_ dá pra fazer "com as mãos nas costas"... O bacana é que sai tudo do forno com a uma simplicidade impressionante de comandos. :dancers:

<br>

### **Uso de Marcadores de Dados Estruturados**

Depois de aprender a lidar com as variáveis dos _posts_, das _pages_ e do _site_, você poderá "inventar" um monte de coisas bacanas. Por exemplo, utilizar _accordions_, _tabbed panels_, e outras ferramentas de design para inserir dados chamados com a Liquid. Para ver um exemplo, sugiro que dê uma olhada nas páginas de [tags][tags] ou [categorias][categ] deste blog. Nelas, utilizamos _collapsible panels_ para exibir (dinamicamente) os artigos pertencentes a cada uma das variáveis aplicando _loops_ em valores de _arrays_.

Utilizando essas ferramentas, você poderá montar como quiser os seus __marcadores de dados estruturados__, como por exemplo, [Schema Markup](http://schema.org/), [Facebook Open Graph](http://ogp.me/) e [Twitter Card](https://dev.twitter.com/cards/overview). A estrutura Liquid para criar as tags de modo inteligente é longa e por isso não a descreveremos neste artigo introdutório. Em breve publicaremos um artigo com um passo a passo de como estruturar seus marcadores, por isso o convidamos para seguir-nos no [Twitter](https://twitter.com/virtuacreative) para receber nossos artigos em primeira mão!

<br>

### **Formulários de Contato para Jekyll**

Formulários de contato são mais delicados para formular no Jekyll. Há como fazer? Há. Mas este assunto abordaremos assim que terminarmos o nosso mais novo projeto **<mkp-green>Virtua Creative Tools: Contact Form Handler</mkp-green>** para sites estáticos! E mais: nosso diferencial é que não passaremos os dados inseridos pelos seus clientes para uma base de dados para depois recuperá-los para você. As informações serão enviadas diretamente: somente você deterá as informações do seu contato, no seu email. 

Se você tem pressa para montar seu formulário de contato, fale com a gente por um dos nossos [canais de relacionamento](http://www.virtuacreative.com.br/virtua-contato.php) que poderemos preparar um script exclusivo para você ou para a sua empresa, que poderá ser usado com segurança em páginas `html` ou `php`. Para ver um exemplo, acesse nossa [página de contato][contact] deste blog.

<br>

<hr/>

#### Documentação de Referência & Leitura Complementar

<br>

\- [Jekyll - Documentation][jekyll]
\- [Jekyll Help][jekyll-help]
\- [Liquid Design][Liquid Design]
\- [GitHub - Markdown][Markdown]
\- [Yaml - Documentation][Yaml]
\- [Jekyll - SASS - Article][sass-jekyll]
\- [GitHub Pages][github-pages]
\- [Jekyll Video Tutorial][jekyll-youtube1]


[jekyll]: http://jekyllrb.com
[jekyll-gh]:   	https://github.com/jekyll/jekyll
[jekyll-help]: 	https://github.com/jekyll/jekyll-help
[Liquid Design]: https://github.com/Shopify/liquid/wiki
[Markdown]: https://guides.github.com/features/mastering-markdown/
[Yaml]: https://pt.wikipedia.org/wiki/YAML
[github-pages]: http://pages.github.com
[pain-jekyll]: http://cristianobetta.com/blog/2013/08/21/the-joy-and-pain-of-using-jekyll/
[how-to-jekyll]: http://yizeng.me/2013/05/10/setup-jekyll-on-windows/
[jekyll-youtube1]: https://www.youtube.com/playlist?list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-
[devtips-jekyll]: https://www.youtube.com/watch?v=iWowJBRMtpc
[sass-jekyll]: http://markdotto.com/2014/09/25/sass-and-jekyll/
[tags]: http://virtuacreative.github.io/blog/tags.html
[categ]: http://virtuacreative.github.io/blog/categories.html
[devtips-not-jekyll]: https://www.youtube.com/watch?v=u22CLlw4_hg
[contact]: http://virtuacreative.github.io/git/contact.html
