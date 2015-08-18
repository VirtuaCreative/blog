---
layout: post
fb_type: article
fb_section: Tutorials - Jekyll
title: Criando blogs com Jekyll no Windows
fb_title: Criando blogs com Jekyll no Windows
categories: [Jekyll, Github, Blog, Tutoriais]
tags: [jekyll, git, blog]
meta_keywords: jekyll, git, blog
description: Como criar blogs com Jekyll no Windows e publicar com o GitHub Pages.
image: https://goo.gl/R3kHKk
imageUrl: https://www.flickr.com/photos/virtuacreative/20329582166
author: Marcia Ramos
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
author_fb: marciaramosmdr
author_twitter: xmdramos
authorEmail: virtua.creative@gmail.com
comments: true
date: 2015-07-30 22:05:45 UTC
date_update: 2015-08-17 22:22:26 UTC
# language: [en_US, en_UK]
---

# **Jekyll**

[Jekyll](http://jekyllrb.com/) é um programa que permite a criação de websites e blogs utilizando apenas html, css e javascript. Entenda o que é o Jekyll neste artigo: "**[O que é e para que serve o Jekyll]({{ site.baseurl }}{% post_url 2015-08-17-jekyll-for-beginners-introduction %})**", no qual explicamos detalhadamente como ele funciona.

<br>

#### **<mkp-blue>Vantagens de utilizar o Jekyll</mkp-blue>**

Não há necessidade da criação de uma base de dados, o que o torna absolutamente seguro. Ele dinamiza o código html, assim como as extensões baseadas em liguagem de servidor (como php, por exemplo), mas sem a necessidade da leitura do próprio servidor.

O mais interessante é que o Jekyll é suportado pelo [GitHub Pages][github-pages], permitindo assim que websites e blogs escritos em Jekyll sejam hospedados gratuitamente no GitHub.

Ao criar um novo website com o comando  `jekyll new nome-do-blog`, uma pasta `nome-do-blog` é automaticamente formulada pelo Jekyll, trazendo a estrutura básica para desenvolvimento do site, incluindo a programação da formulação de blogs. Ou seja, não é necessário que você escreva todo o escopo do projeto, o próprio comando traz a estrutura pronta para você desenvolvê-la.

O Jekyll foi primeiramente desenvolvido para computadores MAC, em que a instalação e utilização é simples e direta. As últimas versões já estão disponíveis para Windows, mas requerem uma dose de boa vontade para deixar tudo funcionando como deve. 

Não sou expert em Jekyll, mas devido à falta de informações e tutoriais nesta área específica, resolvi deixar minha contribuição para quem tem se batido com o Jekyll para Windows, e contar para vocês como consegui fazê-lo funcionar.

<hr/>

### **Criando seu projeto com o Jekyll no Windows (Win 7)**

<br>

Programas e gems necessários para a instalação: 
- [Ruby (1)][ruby] 
- [Ruby DevKit][ruby]
- [RubyGems][rubygems]
- [GitHub - Windows (2)][git-windows]
- [Git - PowerShells (2)][git-power]
- [GitHub Pages (2)][gem-gh-pages]
- [Sass (3)][sass]
- [Bundler][bundler]
- [Jekyll][jekyll-install]

Recomendados: 
- [Rails][rails] 
- Python / Pip / Redcarpet / Easy-Install / Pygments ou (4)
- Kramdown / Rouge (4)

Outros:
- [Windows Directory Monitor][wdm]
- [RDiscount][rdisc] 

#### (1) Atenção:

Ruby: no próprio site do Ruby, existe a informação de que a versão Ruby para winx64 ainda está em fase inicial e pode não funcionar perfeitamente. Por isso, apesar de ter winx64, preferi optar pela versão para winx32.

#### (2) Jekyll e GitHub

Git e GitHub Pages: necessários somente para quem pretende hospedar o Jekyll no GitHub.

#### (3) Sass

O Sass é uma ferramenta fantástica de web design. Não é obrigatória para rodar o Jekyll, mas altamente recomendada. Em breve escreveremos um artigo sobre o Sass e adicionaremos o link aqui. 

#### (4) Markdown

Você precisará instalar as gems necessárias para que consiga utilizar os arquivos em markdown. Não sabe exatamente qual vai usar? Instale todas... 
O Python é um programa com instalador. Todos os demais são "gems".

<br>

#### **<mkp-blue>Passo-a-passo para a instalação</mkp-blue>**

O passo-a-passo para a instalação dos programas e gems mencionados acima via de regra é longo e cansativo, uma vez que pode gerar um monte de erros. Por esta razão, recomendo que siga este camarada [Yi Zeng][how-to-jekyll], pois o tutorial dele inclui os possíveis erros que podem ocorrer e informa como resolvê-los. Em breve farei a tradução do tutorial dele em um novo artigo deste blog e incluirei o link aqui. Caso você não seja um programador e consiga instalar tudo rapidamente e sem gerar erros, parabéns, você é um vencedor! :smiley: 

<br>

<hr/>  


### **<a name="new-project"></a>Criando seu primeiro Blog com Jekyll**

<br>

Agora que você já conseguiu instalar o Jekyll, vamos criar seu primeiro site.

Abra seu prompt de comando, vá até o diretório onde quer criar seu novo projeto e digite:

{% highlight PowerShell %}
jekyll new meuprojeto
# cria uma nova pasta com o nome do seu projeto.
{% endhighlight %}

{% highlight PowerShell %}
cd meuprojeto
# entra na pasta do seu projeto.
{% endhighlight %}

{% highlight PowerShell %}
jekyll serve --watch # veja abaixo
{% endhighlight %}

_Com o comando_ `serve`, _o Jekyll compilará os arquivos para formar sua estrutura em html e abrirá um servidor local que permite que você veja o site no seu navegador de internet._

_Com o comando_ `--watch`, _o Jekyll acomanhará as mudanças que você fará nos arquivos e repassá para o servidor local o arquivo html compilado. Basta atualizar a página do seu navegador para acompanhar suas alterações._

Se der tudo certo até aqui, você verá uma notificação no seu prompt informando que o Jekyll está rodando neste endereço: `server address: http://127.0.0.1:4000`. A parte à esqueda da pontuação `:` corresponde ao seu ip local ou localhost. A parte da direita te informa qual é a porta que o localhost está usando. Para ver seu novo site, vá até seu navagedor e digite `localhost:4000` ou o endereço informado pelo prompt de comando, caso seja diferente deste. Ao fazer uma mudança no seu arquivo, você terá que atualizar a página no navegador (F5) para vê-la.

<br>

#### **<mkp-blue>Parando a compilação</mkp-blue>**

Se por algum motivo você quiser parar a compilação do Jekyll, vá ao prompt de comando e aperte `Ctrl C` no seu teclado. Se quiser alterar o arquivo `_config.yml`, sobre o qual falaremos logo [abaixo](#config), você terá que parar o Jekyll e reiniciá-lo, caso contrário as suas configurações não serão atualizadas. Para reiniciá-lo rapidamente, aperte a seta para cima :arrow_up: do seu teclado que aparecerá seus últimos comandos. Encontre o `jekyll serve --watch` e aperte `enter` para reiniciar.

<br>
<hr/>


### **Hospedando gratuitamente com o GitHub Pages**

<br>

Agora que temos um projeto, e partido do pressuporto que você queira hospedá-lo no [GitHub Pages][github-pages], temos que fazer com que o Jekyll converse com o GitHub. Partimos do princípio que você já tenha um gh-pages pronto para receber seu blog. Para fazer o setup do GitHub Pages, precisaremos escrever um novo artigo, em breve você encontrará aqui um um link para ele. Siga-nos no [Twitter]() para ver nossos artigos em primeira mão!

<br>

#### <a name="config"></a><mkp-blue>Configuração do</mkp-blue> **<mkp-blue>_config.yml</mkp-blue>**

Na pasta raiz do seu projeto, encontre o arquivo de configuração `_config.yml`. Este é o arquivo chave do seu projeto. Nele vão todas as configurações do website, por exemplo: título, autor, email do autor, facebook do autor e todas as outras variáveis que você aprenderá a definir conforme for lendo sobre o assunto. 

Para publicar no GitHub Pages, você precisa definir algumas variáveis importantíssimas neste arquivo, como markdown, highlighter e baseurl. Para efeitos de GitHub, o que é fundamental é que você avise ao git onde fica sua pasta que hospedará seu site (baseurl). Portanto, informe o seguinte:
{% highlight html %}
baseurl: http://usuario.github.io/seurepositorio
{% endhighlight %}

Esta pasta deverá ser a mesma pasta que você configurou no seu gh-pages, conforme documentado nas instruções do [Jekyll](http://jekyllrb.com/docs/github-pages/) para `baseurl`.

Isso significa que seu site ou blog morará dentro do branch gh-pages, dentro do seu repositório `seuprojeto` e que o index será acessado via `http://usuario.github.io/seurepositorio`.

Caso você utilize o Jekyll no seu próprio domínio, o `baseurl` deverá estar de acordo com sua pasta raiz:

{% highlight html %}
baseurl: http://www.seudominio.com
{% endhighlight %}

Note que há um espaço entre os dois pontos `:` e a url. Mantenha desta forma. Bagunçar com os espaços nos seus arquivos `.yml` pode gerar erros na compilação que você ficará louco até encontrar. Portanto, recomendo que não deixe de respeitar os espaços e a pontuação nos seus arquivos Yaml!

<br>

#### <mkp-blue>Gerando o</mkp-blue> **<mkp-blue>Gemfile</mkp-blue>**

Segundo as [instruções do GitHub](https://help.github.com/articles/using-jekyll-with-pages/), será necessário gerar um "Gemfile" no seu diretório do gh-pages:

1. Abra seu editor de html e crie um novo documento na pasta raíz do seu projeto. Este arquivo deverá se chamar "Gemfile". Não dê a ele nenhuma extensão.
2. Escreva dentro dele: `gem 'github-pages'`  (obs: há outras opções para o GemFile, mas esta foi a melhor que encontrei até agora.) 
3. Com o prompt de comando **aberto na pasta raíz do seu projeto**, escreva: `bundle install`. Pronto. Assim o seu Gemfile vai ganhar uma nova cara. Se o novo Gemfile não tiver substituído o que você criou, você deverá apagar o antigo e deixar o novo criado pelo bundler.
4. Agora você precisa dar o seguinte comando: `bundle exec jekyll serve --watch --baseurl ""`.  Isso permitirá que você rode o site no seu localhost novamente, mas sem alterar a definição do `baseurl` que tínhamos feito anteriormente.

Se aparecer alguma mensagem de erro, você poderá fazer o update de todos os gems:

{% highlight ruby %}
gem update
{% endhighlight %}
{% highlight ruby %}
bundle update
{% endhighlight %}
{% highlight ruby %}
bundle update github-pages
{% endhighlight %}
{% highlight ruby %}
gem update github-pages
{% endhighlight %}

Depois de fazer todos os updates, insira novamente o comando `bundle exec jekyll serve --watch --baseurl ""`. Deve funcionar. Caso não funcione, recomendo que volte ao artigo do [Yi Zeng][how-to-jekyll] para tentar encontrar o erro e corrigi-lo.

Pronto! Seu website deverá estar pronto para que você insira seu conteúdo!  :clap:   :clap:

<br>

#### **<mkp-blue>Posts</mkp-blue>**

Este artigo já está muito longo, por isso não será detalhado aqui como funciona a estrutura de pastas do projeto. Apenas para oferecer uma pequena introdução, fique atento ao seguinte: a primeira parte de todos os arquivos traz o cabeçalho de configuração do arquivo. Esta parte fica sempre no topo, separada do corpo pelos três traços, conforme abaixo:

{% highlight text %}
---
Configurações do post
---

Texto post
{% endhighlight %}

No cabeçalho de configuração, você poderá listar tudo que faz parte do post, como: layout, título, descrição, autor, categorias, tags, e tudo que você desejar inserir como padrão.

Para exemplificar, veja abaixo como ficou o cabeçalho deste post:

{% highlight text %}
---
layout: post
title: Criando blogs com Jekyll no Windows
categories: [Jekyll, Github, Blog, Tutoriais]
tags: [jekyll, git, blog]
description: Como criar blogs com Jekyll no Windows e publicar com o GitHub Pages.
author: Marcia Ramos
---

# **Jekyll**

Jekyll é um programa.....

{% endhighlight %}

Estas informações poderão ser recuperadas por todo o site, utilizando tags, objetos e filtros da **[Liquid Templating Language](https://docs.shopify.com/themes/liquid-documentation/basics)**. Por exemplo, para recuperar o título da página, você poderá utilizar o seguinte objeto:

{% highlight ruby %} 
{% raw %}{{ post.title }}{% endraw %} 
# ou
{% raw %}{{ page.title }}{% endraw %} 
{% endhighlight %}

Estes são apenas exemplos simples. Aprofundaremos os detalhes da escrita em Liquid futuramente, em outros artigos. 

O único arquivo que não trará o cabeçalho se configuração será o seu `default.html` da pasta `_includes`. Este arquivo será o padrão para seu html. Nele serão inseridas as tags `<html>`, `<head>` e o `<body>` de todas as páginas, que terão seus conteúdos inseridos dinamicamente através da chamada `{% raw %}{{ content }}{% endraw %}`. Este tipo de objeto faz parte da estrutura Liquid, que deixaremos para discutir em outros artigos. Para ter um panorama introdutório a este assunto, veja nosso artigo ["O que é Jekyll - e para que ele serve"]({{ site.baseurl }}{% post_url 2015-08-17-jekyll-for-beginners-introduction %}). 

<br>

#### **<mkp-blue>Estilizando seu projeto</mkp-blue>**

O projeto padrão do Jekyll (obtido com o comando `jekyll new meuprojeto` explicado [acima](#new-project)) já traz um design interessante. Muitas pessoas não perdem muito tempo estilizando suas páginas, usam o próprio projeto padrão e se aprofundam apenas em seus conteúdos. De qualquer forma, para saber o que é o que, você pode usar o `Inspecionar Elemento` do seu navegador para interagir com o css e personalizá-lo. Se você não está familiarizado com esta ferramenta, poderá ver este [artigo](http://www.gerenciandoblog.com.br/2013/10/como-usar-inspecionar-elemento-google-chrome.html), no qual o autor descreve detalhadamente como utilizá-la. Nesse artigo, o rapaz explica como o  "Inpecionar elemento" funciona no Google Chrome, mas no Mozilla Firefox você poderá acessá-la da mesma forma.


<br>

#### **<mkp-blue>Markdown</mkp-blue>**

**Markdown:** para ter acesso a uma lista prática de markdowns do Jekyll / GitHub, veja o nosso artigo [Jekyll e GitHub Markdown]({{ site.baseurl }}{% post_url 2015-08-02-jekyll-github-markdown %}).

<br>

<hr/>

### **Prós & Contras**

<br>

Infelizmente, para quem está acostumado com a liguagem html/css sem markdowns, o Jekyll pode exigir um certo tempo para aprendizagem, mas todo desenvolvedor web poderá entender rapidamente e aprender a curtir! Há desenvolvedores que utilizam outros geradores de sites estáticos (Static Site Generators - SSGs), em razão das limitações impostas pelo Jekyll. Neste [link](https://staticsitegenerators.net/), você poderá encontrar uma lista de todos os SSGs que estão rolando por aí. De longe, o Jekyll é o mais utilizado. 

Para quem precisa de websites mais elaborados com páginas de login, com CMS, com formulários de cadastro, ou mesmo sites que precisem de atualizações constantes, não costuma-se recomendar nem o Jekyll e nem o GitHub Pages. Eles não têm este propósito e nem permitem estas funcionalidades. Ou melhor, há usuários avançados que fazem verdadeiros milagres com o Jekyll, mas se você ainda é um iniciante em Jekyll, tente primeiro entender todas as funções básicas para depois explorar as avançadas. 

De qualquer forma, dependendo da complexidade que você queira atingir, não é possível fugir da programação baseada em linguagem de servidor, como o **php** faz muito bem. E neste caso, você não poderia utilizar o GitHub pages, que não suporta php.

<br>

#### **<mkp-blue>Outras fontes de informação</mkp-blue>**


Para quem entende Inglês, sugiro que siga os tutoriais em vídeo da série Jekyll do [Thomas Bradley][jekyll-youtube1]. Ficará mais fácil compreender como utilizar a estrutura de pastas, as ferramentas e os arquivos em  markdown `.md` do Jekyll.


Recomendo também a leitura do artigo (em Inglês) [The joy and pain of using Jekyll][pain-jekyll], que explica melhor quais são as maiores vantagens e desvantagens de usar o Jekyll.

Há uma outra fonte de prós e contras do Jekyll com o Travis Nielson, em que ele argumenta com seu amigo Jon, ambos designers. O título do vídeo é ["Jon doesn't like Jekyll"][devtips-not-jekyll].

Você poderá acessar a documentação do Jekyll no [Jekyll docs][jekyll]. Se você precisar reportar bugs e novas implementações, poderá fazê-lo no [Jekyll’s GitHub repo][jekyll-gh]. Se você tiver dúvidas, eles recomendam que os procure no [Jekyll’s Help repo][jekyll-help].

Ficaremos muito felizes se puder deixar seu comentário com sugestões e dicas que ajudem a comunidade web!


[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
[github-pages]: http://pages.github.com
[gem-gh-pages]: https://github.com/github/pages-gem
[pain-jekyll]: http://cristianobetta.com/blog/2013/08/21/the-joy-and-pain-of-using-jekyll/
[how-to-jekyll]: http://yizeng.me/2013/05/10/setup-jekyll-on-windows/
[jekyll-youtube1]: https://www.youtube.com/playlist?list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-
[devtips-jekyll]: https://www.youtube.com/watch?v=iWowJBRMtpc
[devtips-not-jekyll]: https://www.youtube.com/watch?v=u22CLlw4_hg
[ruby]: http://rubyinstaller.org/downloads/
[rails]: http://guides.rubyonrails.org/getting_started.html
[rubygems]: https://rubygems.org/
[sass]: http://sass-lang.com/install
[git-windows]: https://windows.github.com/
[bundler]: http://bundler.io/
[gh-pages]: https://help.github.com/articles/using-jekyll-with-pages/
[jekyll-install]: http://jekyllrb.com/docs/installation/
[jkl-install-win]: http://jekyll-windows.juthilo.com/
[git-power]: https://git-scm.com/book/be/v2/Git-in-Other-Environments-Git-in-Powershell
[wdm]: https://rubygems.org/gems/wdm/versions/0.1.0
[rdisc]: https://rubygems.org/gems/rdiscount/versions/2.1.8