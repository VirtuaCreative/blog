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
image_schema: 'https://c1.staticflickr.com/1/311/20329582166_7a11e1a308_b.jpg'
imageUrl: https://www.flickr.com/photos/virtuacreative/20329582166
author: Marcia Ramos
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
author_fb: marciaramosmdr
author_twitter: xmdramos
authorEmail: virtua.creative@gmail.com
comments: true
date: 2015-07-30 22:05:45 UTC
date_update: 2016-02-22 17:51:11 UTC
# language: [pt_BR]
---

# **Jekyll**

[Jekyll](http://jekyllrb.com/) é um programa escrito em [Ruby](https://www.ruby-lang.org/pt/) que permite a criação dinâmica de websites e blogs utilizando apenas `html`, `css` e `javascript`. Entenda o que é o Jekyll neste artigo: "**[O que é e para que serve o Jekyll]({{ site.baseurl }}{% post_url 2015-08-17-jekyll-for-beginners-introduction %})**", no qual explicamos detalhadamente como ele funciona.

<br>

#### **<mkp-blue>Vantagens de utilizar o Jekyll</mkp-blue>**

Não há necessidade da criação de uma base de dados, o que o torna absolutamente seguro. Ele dinamiza o código html, assim como as extensões baseadas em liguagem de servidor (como php, por exemplo), mas sem a necessidade da leitura do próprio servidor.

O mais interessante é que o Jekyll é suportado pelo [GitHub Pages][github-pages], permitindo assim que websites e blogs escritos em Jekyll sejam hospedados gratuitamente no GitHub.

Ao criar um novo website com o comando  `jekyll new nome-do-blog`, uma pasta `nome-do-blog` é automaticamente formulada pelo Jekyll, trazendo a estrutura básica para desenvolvimento do site, incluindo a programação da formulação de blogs. Ou seja, não é necessário que você escreva todo o escopo do projeto, o próprio comando traz a estrutura pronta para você desenvolvê-la.

O Jekyll foi primeiramente desenvolvido para computadores MAC, em que a instalação e utilização é simples e direta. As últimas versões já estão disponíveis para Windows, mas requerem um pouco mais de esforço para deixar tudo funcionando como deve. 

Devido à falta de informações e tutoriais nesta área específica, resolvi deixar minha contribuição para quem tem se batido com o Jekyll para Windows, e contar para vocês como consegui fazê-lo funcionar.

<hr/>

### **Criando seu projeto com o Jekyll no Windows (Win 7)**

<br>

Programas e gems necessários para a instalação (veja abaixo as notas referentes às marcações **(1)**, **(2)**, **(3)**, **(4)**, e **(*)**): 

- [Ruby (1)][ruby]* - _instalador_
- [Ruby DevKit][ruby]* - _instalador_
- [RubyGems][rubygems]* - _pack_
- [GitHub Desktop (2)][git-windows] - _Windows App_
- [Git (2)][git-power] - _incluso no GitHub Desktop_
- [GitHub Pages (2)][gem-gh-pages] - `gem install github-pages`
- [Sass (3)][sass] - `gem install sass`
- [Bundler][bundler]* - `gem install bundler`
- [Jekyll][jekyll-install]* - `gem install jekyll`
- [Kramdown](https://rubygems.org/gems/kramdown)* / [Rouge](https://rubygems.org/gems/rouge/versions/1.10.1)* (4) - `gem install kramdown` e `gem install rouge`

Recomendados: 
- [Rails][rails] - _[instalador](http://installrails.com/)_

<small>Updates: Upgrade de Jekyll 2 para Jekyll 3 - não mais recomendados para Jekyll 3.x:</small> 
<div style="text-decoration: line-through; color: #999; font-style: italic;"><small>- Python / Pip / Redcarpet / Easy-Install / Pygments ou (4)</small> </div>
<p> </p>

Outros:
- [Windows Directory Monitor][wdm] - _para usuários do Windows_
- [RDiscount][rdisc] - _dependência para algumas `gems`_
<p> </p>

#### * Fundamental:

A instalação destes programas é fundamental para um funcionamento perfeito do Jekyll.

#### (1) Atenção:

Ruby: no próprio site do Ruby, existe a informação de que a versão Ruby para winx64 ainda está em fase inicial e pode não funcionar perfeitamente. Por isso, apesar de ter winx64, preferi optar pela versão para winx32.

#### (2) Jekyll e GitHub

Git e GitHub Pages: gems necessárias somente para quem pretende hospedar o Jekyll no GitHub Pages.

#### (3) Sass

O Sass é uma ferramenta fantástica de web design. Não é obrigatória para rodar o Jekyll, mas altamente recomendada. Em breve escreveremos um artigo sobre o Sass e adicionaremos o link aqui. 

#### (4) Markdown / Highlighter

<small>Updates: Upgrade de Jekyll 2 para Jekyll 3 </small>

A versão 2 do Jekyll possuía como padrão:

```yml
markdown: redcarpet
highlighter: pygments
```

Já a nova versão **Jekyll 3.x** possui como padrão:

```yml
markdown: kramdown
highlighter: rouge
```

Portanto, prefira a segunda opção. Desta forma, você evitará a instalação do Python, do Redcarpets, do Pygments e todas suas dependências.


<div style="text-decoration: line-through; color: #999; font-style: italic;">

Você precisará instalar as gems necessárias para que consiga utilizar os arquivos em markdown. Não sabe exatamente qual vai usar? Instale todas... 
O Python é um programa com instalador. Todos os demais são "gems".

</div>

<br>

#### **<mkp-blue>Passo-a-passo para a instalação</mkp-blue>**

O passo-a-passo para a instalação dos programas e gems mencionados acima via de regra é longo e pode gerar erros. Por esta razão, recomendo que siga este camarada [Yi Zeng][how-to-jekyll], pois o tutorial dele inclui os possíveis erros que podem ocorrer e informa como resolvê-los. Em breve farei a tradução do tutorial dele em um novo artigo deste blog e incluirei o link aqui. Caso você não seja um programador e consiga instalar tudo rapidamente e sem gerar erros, parabéns, você é um vencedor! :smiley: 

**UPDATE** - Jekyll 2 para Jekyll 3: O processo de instalação do Jekyll melhorou significativamente depois da alteração de `markdown` e `highlighter` de `redcarpet` para `kramdown` e de `pygments` para `rouge`, respectivamente. Esta alteração nos padrões reduziu significativamente o número de dependências das `gems` instaladas e a ausência do `Python`, um programa voltado a programadores, mas não utilizado por todos os desenvolvedores e designers web.

<br>

<hr/>  


### **<a name="new-project"></a>Criando seu primeiro Blog com Jekyll**

<br>

Agora que você já conseguiu instalar o Jekyll, vamos criar seu primeiro site.

Abra seu prompt de comando, vá até o diretório onde quer criar seu novo projeto e digite:

{% highlight powershell %}
jekyll new meuprojeto
# cria uma nova pasta com o nome do seu projeto.
{% endhighlight %}

{% highlight powershell %}
cd meuprojeto
# entra na pasta do seu projeto.
{% endhighlight %}

{% highlight powershell %}
jekyll serve --watch # veja abaixo
{% endhighlight %}

_Com o comando_ `serve`, _o Jekyll compilará os arquivos para formar sua estrutura em html e abrirá um servidor local que permite que você veja o site no seu navegador de internet._

_Com o comando_ `--watch`, _o Jekyll acomanhará as mudanças que você fará nos arquivos e repassá para o servidor local o arquivo html compilado. Basta atualizar a página do seu navegador para acompanhar suas alterações._

Se der tudo certo até aqui, você verá uma notificação no seu prompt informando que o Jekyll está rodando neste endereço: `server address: http://127.0.0.1:4000`. A parte à esqueda da pontuação `:` corresponde ao seu ip local ou localhost. A parte da direita te informa qual é a porta que o localhost está usando. Para ver seu novo site, vá até seu navagedor e digite `localhost:4000` ou o endereço informado pelo prompt de comando, caso seja diferente deste. Ao fazer uma mudança no seu arquivo, você terá que atualizar a página no navegador (F5) para vê-la.

<br>

#### **<mkp-blue>Parando a compilação</mkp-blue>**

Se por algum motivo você quiser parar a compilação do Jekyll, vá ao prompt de comando e aperte `Ctrl C` no seu teclado. Se quiser alterar o arquivo `_config.yml`, sobre o qual falaremos logo [abaixo](#config), você terá que parar o Jekyll e reiniciá-lo, caso contrário as suas configurações não serão atualizadas. Para reiniciá-lo rapidamente, aperte a seta para cima :arrow_up: do seu teclado que aparecerá seus últimos comandos. Encontre o `jekyll serve --watch` e aperte `enter` para reiniciar.

<br>

<a name="gemfile"></a>

#### **<mkp-blue>Executando o Jekyll sem erros</mkp-blue>**

A forma mais garantida de usar o Jekyll localmente no seu PC (ou Mac) sem gerar erros é fazendo a instalação e a construção do site com o `bundler`:

1. Adicione à raiz do seu projeto um arquivo chamado `Gemfile` (sem **nenhuma** extensão).
2. Neste arquivo, adicione um dos dois blocos abaixo:

    a) caso você não pretenda hospedar seu site no GitHub Pages, adicione ao `Gemfile`:
        
        source 'https://rubygems.org'
        gem 'jekyll'
        gem 'kramdown'
        gem 'rouge'
        
    b) caso você pretenda hospedar seu site no GitHub Pages, adicione:
        
        source 'https://rubygems.org'
        gem 'github-pages'
        
	c) Salve o `Gemfile`.

3. Abra o seu terminal na pasta do seu projeto e execute o comando `bundle install`. O Bundler criará um arquivo chamado `Gemfile.lock` na raíz do seu projeto. Deixe-o lá.
4. Execute o Jekyll com o comando `bundle exec jekyll serve`

Desta forma, via `bundler`, você estará garantindo que as `gems` necessárias para construir seu site localmente estão instaladas, assim como todas as suas dependências. 

_Nota: há outras `gems` que poderão ser inseridas conforme sua necessidade._

<br>
<hr/>


### **Hospedando gratuitamente com o GitHub Pages**

<br>

Agora que temos um projeto, e partido do pressuposto que você queira hospedá-lo no [GitHub Pages][github-pages], temos que fazer com que o Jekyll "converse" com o GitHub. Partimos do princípio que você já tenha um repositório pronto para receber seu blog. Para fazer o setup do GitHub Pages, veja o artigo [Como publicar seu website no GitHub][]. Siga-nos no [Twitter]() para ver nossos artigos em primeira mão!

<br>

#### <a name="config"></a><mkp-blue>Configuração do</mkp-blue> **<mkp-blue>_config.yml</mkp-blue>**

Na pasta raiz do seu projeto, encontre o arquivo de configuração `_config.yml`. Este é o arquivo chave do seu projeto. Nele vão todas as configurações do website, por exemplo: título, autor, email do autor, facebook do autor e todas as outras variáveis que você aprenderá a definir conforme for lendo sobre o assunto. 

Para publicar no GitHub Pages, você precisa definir algumas variáveis importantíssimas neste arquivo, como markdown, highlighter e baseurl. Para efeitos de GitHub, o que é fundamental é que você avise ao git onde fica sua "pasta" que hospedará seu site (baseurl). Portanto, informe o seguinte:

**Caso comum** a todos os websites hospedados no GitHub:
{% highlight yml %}
highlighter: rouge
markdown: kramdown
kramdown:
  input: GFM
{% endhighlight %}

**Caso 1**: Website de usuário ou organização:
{% highlight yml %}
baseurl: http://usuario.github.io
{% endhighlight %}

**Caso 2**: Website de projetos
{% highlight yml %}
baseurl: http://usuario.github.io/seurepositorio
{% endhighlight %}

O nome desta "pasta" deverá ser o mesmo nome do seu repositório, conforme documentado nas instruções do [Jekyll](http://jekyllrb.com/docs/github-pages/) para `baseurl`.

Caso seja um website de projeto, isso significa que seu site ou blog morará dentro do branch `gh-pages`, dentro do seu repositório `seuprojeto` e que o index será acessado via `http://usuario.github.io/seurepositorio`. Caso seja um website de usuário/organização, o repositório deverá ser nomeado `usuario.github.io` e o seu blog morará no branch `master` e sua home page (index.html) será acessada via `http://usuario.github.io`. Você poderá ainda redirecionar seu website para um domínio próprio, como `suaempresa.com.br`.

Caso você utilize o Jekyll no seu próprio domínio, o `baseurl` deverá estar de acordo com sua pasta raiz:

{% highlight yml %}
baseurl: http://www.seudominio.com
{% endhighlight %}

Note que há apenas um espaço entre os dois pontos `:` e a url. Mantenha desta forma. Bagunçar com os espaços nos seus arquivos `.yml` pode gerar erros na compilação que você ficará louco até encontrar. Portanto, recomendo que não deixe de respeitar os espaços e a pontuação nos seus arquivos Yaml!

<br>

#### <mkp-blue>Gerando o</mkp-blue> **<mkp-blue>Gemfile</mkp-blue>**

Segundo as [instruções do GitHub](https://help.github.com/articles/using-jekyll-with-pages/), será necessário gerar um "Gemfile" no seu repositório. Siga os passos [descritos anteriormente](#gemfile) para gerar seu `Gemfile` para o GitHub Pages.

Lembre-se: caso necessário, inclua outras `gems` ao seu `Gemfile`.

Agora você poderá executar o seguinte comando: `bundle exec jekyll serve --safe --watch --baseurl ""`.  Isso permitirá que você rode o site no seu localhost novamente, mas sem alterar a definição do `baseurl` que tínhamos feito anteriormente. A _flag_ `--safe` é necessária para que você monte seu website localmente exatamente como o GitHub montará. **UPDATE**: O novo Jekyll 3.x/GitHub Pages possui um **BUG** no modo seguro. Portanto, [execute sem a _flag_ `--safe` por enquanto](https://talk.jekyllrb.com/t/jekyll-3-x-with-github-pages/1832/11#ember2271), até que o problema seja resolvido: `bundle exec jekyll serve --watch --baseurl ""`.

Se aparecer alguma mensagem de erro, você poderá fazer o update de todas as `gems`:

{% highlight powershell %}
gem update # caso não use o bundler - todas as "gems" instaladas serão atualizadas
{% endhighlight %}
{% highlight powershell %}
bundle update # caso use o bundler - todas as "gems" instaladas serão atualizadas
{% endhighlight %}
{% highlight powershell %}
bundle update github-pages # o bundler fará somente o update da gem "github-pages"
{% endhighlight %}
{% highlight powershell %}
gem update github-pages # fará somente o update da gem "github-pages" sem o bundler
{% endhighlight %}

Caso haja algum erro ao montar o site, em qualquer momento do seu desenvolvimento,  você poderá executar o comando `jekyll --trace` para mais informações sobre o erro.

Depois de fazer todos os updates, insira novamente o comando `bundle exec jekyll serve --watch --baseurl ""`. Deve funcionar. Caso não funcione, recomendo que volte ao artigo do [Yi Zeng][how-to-jekyll] para tentar encontrar o erro e corrigi-lo.

Pronto! Seu website deverá estar pronto para que você insira seu conteúdo!  :clap:   :clap:

<br>

#### **<mkp-blue>Posts</mkp-blue>**

Este artigo já está muito longo, por isso não será detalhado aqui como funciona a estrutura de pastas do projeto. Apenas para oferecer uma pequena introdução, fique atento ao seguinte: a primeira parte de todos os arquivos traz o cabeçalho de configuração do arquivo (originalmente chamada `Yaml frontmatter`). Esta parte fica sempre no topo, separada do corpo pelos três traços, conforme abaixo:

{% highlight markdown %}
---
Configurações do post
---

Texto post
{% endhighlight %}

No cabeçalho de configuração, você poderá listar tudo que faz parte do post, como: layout, título, descrição, autor, categorias, tags, e tudo que você desejar inserir como padrão.

Para exemplificar, veja abaixo como ficou parte do cabeçalho deste artigo:

{% highlight markdown %}
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

{% highlight liquid %}{% raw %}{{ post.title }}{% endraw %} 
# ou
{% raw %}{{ page.title }}{% endraw %} 
{% endhighlight %}

Estes são apenas exemplos simples. Aprofundaremos os detalhes da escrita em Liquid futuramente, em outros artigos. 

Os únicos arquivos que não trarão o cabeçalho se configuração serão os arquivos da pasta `_includes`. Estes arquivos terão seus conteúdos inseridos dinamicamente através da chamada `{% raw %}{{ content }}{% endraw %}` ou `{% raw %}{% include %}{% endraw %}`. Este tipo de objeto faz parte da estrutura Liquid, que deixaremos para discutir em outros artigos. Para ter um panorama introdutório a este assunto, veja nosso artigo ["O que é Jekyll - e para que ele serve"]({{ site.baseurl }}{% post_url 2015-08-17-jekyll-for-beginners-introduction %}). 

<br>

#### **<mkp-blue>Estilizando seu projeto</mkp-blue>**

O projeto padrão do Jekyll (obtido com o comando `jekyll new meuprojeto` explicado [acima](#new-project)) já traz um design interessante. Muitas pessoas não perdem muito tempo estilizando suas páginas, usam o próprio projeto padrão e se aprofundam apenas em seus conteúdos. De qualquer forma, para saber o que é o que, você pode usar o `Inspecionar Elemento` do seu navegador para interagir com o css e personalizá-lo. Se você não está familiarizado com esta ferramenta, poderá ver este [artigo](http://www.gerenciandoblog.com.br/2013/10/como-usar-inspecionar-elemento-google-chrome.html), no qual o autor descreve detalhadamente como utilizá-la. Nesse artigo, o rapaz explica como o  "Inpecionar elemento" funciona no Google Chrome, mas no Mozilla Firefox você poderá acessá-la da mesma forma. Há ainda diversos temas gratuitos disponíveis no site [Jekyll Themes](http://jekyllthemes.io/).


<br>

#### **<mkp-blue>Markdown</mkp-blue>**

**Markdown:** para ter acesso a uma lista prática de markdowns do Jekyll / GitHub, veja o nosso artigo [Jekyll e GitHub Markdown]({{ site.baseurl }}{% post_url 2015-08-02-jekyll-github-markdown %}).

<br>

<hr/>

### **+ Mais**

<br>

#### **<mkp-blue>Fontes de informação</mkp-blue>**


Para quem entende Inglês, sugiro que siga os tutoriais em vídeo da série Jekyll do [Thomas Bradley][jekyll-youtube1]. Ficará mais fácil compreender como utilizar a estrutura de pastas, as ferramentas e os arquivos em  markdown `.md` do Jekyll.

Recomendo também a leitura do artigo (em Inglês) [The joy and pain of using Jekyll][pain-jekyll], que explica melhor quais são as maiores vantagens e desvantagens de usar o Jekyll.

Há uma outra fonte de prós e contras do Jekyll com o Travis Nielson, em que ele argumenta com seu amigo Jon, ambos designers. O título do vídeo é ["Jon doesn't like Jekyll"][devtips-not-jekyll].

Você poderá acessar a documentação do Jekyll no [Jekyll docs][jekyll]. Se você precisar reportar bugs e novas implementações, poderá fazê-lo no [Jekyll’s GitHub repo][jekyll-gh]. Se você tiver dúvidas, eles recomendam que os procure no [Jekyll Talk][jekyll-help].

Ficaremos muito felizes se puder deixar seu comentário com sugestões e dicas que ajudem a comunidade web!


<br>



#### **<mkp-blue>Atualização (<em>upgrade</em>) do Jekyll 2.x para 3.x</mkp-blue>**

Tivemos que alterar algumas coisas neste artigo para que sigamos compatíveis com a nova versão do Jekyll, que está inclusive sendo [utilizada pelo GitHub Pages](https://github.com/blog/2100-github-pages-now-faster-and-simpler-with-jekyll-3-0) desde 1º de fevereiro de 2016.

Algumas alterações foram significativas, mas nosso Blog sobreviveu intacto, portanto, considere-se encorajado a alterar seu projeto também. :smiley:

A documentação oficial completa fazendo referência a todas as alterações necessárias para adequar seu projeto ao Jekyll v3.x poderá ser encontrada na página destinada a esta orientação no site oficial do Jekyll: [Upgrading from 2.x to 3.x](http://jekyllrb.com/docs/upgrading/2-to-3/).

A lista de `gems` utilizadas oficialmente pelo GitHub Pages pode ser encontrada [aqui](https://pages.github.com/versions/).

<br>

#### **<mkp-blue>Prós &amp; Contras</mkp-blue>**

Infelizmente, para quem está acostumado apenas com a liguagem html/css sem markdown/liquid, o Jekyll pode exigir um certo tempo para aprendizagem, mas todo desenvolvedor web poderá entender rapidamente e aprender a curtir! E, de fato, depois que aprendemos, não apenas passa a ser uma ferramenta de desenvolvimento web **excelente** como **fácil de usar**. 

Há desenvolvedores que utilizam outros geradores de sites estáticos (Static Site Generators - SSGs), em razão das limitações impostas pelo Jekyll. Neste [link](https://staticsitegenerators.net/), você poderá encontrar uma lista de todos os SSGs que estão rolando por aí. De longe, o Jekyll é o mais utilizado. 

Para quem precisa de websites mais elaborados com páginas de login, com CMS, com formulários de cadastro, ou mesmo sites que precisem de atualizações constantes, não costuma-se recomendar nem o Jekyll e nem o GitHub Pages. Eles não têm este propósito e nem permitem estas funcionalidades. Ou melhor, há usuários avançados que fazem verdadeiros milagres com o Jekyll, mas se você ainda é um iniciante em Jekyll, tente primeiro entender todas as funções básicas para depois explorar as avançadas. 

De qualquer forma, dependendo da complexidade que você queira atingir, não é possível fugir da programação baseada em linguagem de servidor, como o **php** faz muito bem. E neste caso, você não poderia utilizar o GitHub Pages, que não suporta php.

<br>

---------------

### **Artigos Relacionados**

<br>

<ul>
{% for art in site.data.artigos.jekyll %}
  <li>
    <a href="{{ art.url }}">&#8674; {{ art.title }}</a>
  </li>
{% endfor %}
{% for art in site.data.artigos.github %}
  <li>
    <a href="{{ art.url }}">&#8674; {{ art.title }}</a>
  </li>
{% endfor %}					 
{% for art in site.data.artigos.markdown %}
  <li>
    <a href="{{ art.url }}">&#8674; {{ art.title }}</a>
  </li>
{% endfor %}
</ul>

<br>

<hr>


[jekyll]:      http://jekyllrb.com 
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://talk.jekyllrb.com
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
[git-windows]: https://desktop.github.com/
[bundler]: http://bundler.io/
[gh-pages]: https://help.github.com/articles/using-jekyll-with-pages/
[jekyll-install]: http://jekyllrb.com/docs/installation/
[jkl-install-win]: http://jekyll-windows.juthilo.com/
[git-power]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git#Installing-on-Windows
[wdm]: https://rubygems.org/gems/wdm/versions/0.1.0
[rdisc]: https://rubygems.org/gems/rdiscount/versions/2.1.8
[Como publicar seu website no GitHub]: {{ site.data.url.virtua.blog }}hospedar-website-gratis-com-github.html