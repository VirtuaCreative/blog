---
layout: post
title: Criando blogs com Jekyll no Windows
categories: [Jekyll, Github, Blog, Tutoriais]
tags: [jekyll, git, blog]
description: Como criar blogs com Jekyll no Windows e publicar com o GitHub Pages.
image: https://c1.staticflickr.com/1/311/20329582166_7a11e1a308_b.jpg
imageUrl: https://www.flickr.com/photos/virtuacreative/20329582166
author: Marcia Ramos
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
authorEmail: virtua.creative@gmail.com
comments: true
---

## **Jekyll**

[Jekyll](http://jekyllrb.com/) é um programa que permite a criação de blogs utilizando apenas html, css e javascript. Não há necessidade da criação de uma base de dados, o que o torna absolutamente seguro. Ele dinamiza o código html, assim como as extensões baseadas em liguagem de servidor (como php, por exemplo), mas sem a necessidade da leitura do próprio servidor.

O mais interessante é que o Jekyll é suportado pelo [GitHub Pages][github-pages], permitindo assim que websites e blogs escritos em Jekyll sejam hospedados gratuitamente no GitHub.

Ao criar um novo website com o comando  `jekyll new nome-do-blog`, uma pasta `nome-do-blog` é automaticamente formulada pelo Jekyll, trazendo o layout básico para desenvolvimento do site, incluindo a programação da formulação de blogs.

O Jekyll foi desenvolvido para computadores MAC, em que a instalação e utilização é simples e direta. As últimas versões já estão disponíveis para Windows, mas requerem uma grande boa vontade para deixar tudo funcionando como deve. 

Não sou expert em Jekyll, mas devido à falta de informações e tutoriais nesta área específica, resolvi deixar minha contribuição para quem tem se batido com o Jekyll para Windows, e contar para vocês como consegui fazê-lo funcionar.

<hr/>

### Criando seu novo projeto com o Jekyll no Windows (Win 7)

<br>

Programas e gems necessários para a instalação: 
- Ruby* 
- Ruby DevKit 
- RubyGems
- Git
- GitHub Pages
- Sass 
- Bundler
- Jekyll

Recomendados: 
- Rails 
- Python / Pip / Redcarpet / Easy-Install / Pygments ou 
- Kramdown / Rouge 

Outros:
- Windows Directory Monitor 
- RDiscount 

##### *Ruby: no próprio site do Ruby, existe a informação de que a versão Ruby para winx64 ainda está em fase inicial e pode não funcionar perfeitamente. Por isso, apesar de ter winx64, preferi optar pela versão para winx32.

O passo-a-passo para a instalação dos programas e gems mencionados acima é longo e bem chatinho, uma vez que pode gerar um monte de erros. Por esta razão, recomendo que siga este camarada [Yi Zeng][how-to-jekyll], pois o tutorial dele inclui os possíveis erros que podem ocorrer e informa como resolvê-los. Em breve farei a tradução do tutorial dele em um novo artigo deste blog e incluirei o link aqui.

<hr/>


### Criando seu primeiro Blog com Jekyll

<br>

Agora que você já conseguiu instalar o Jekyll, vamos criar seu primeiro site:

Abra seu prompt de comando, vá até o diretório onde quer criar seu novo projeto e digite:

{% highlight PowerShell %}
jekyll new meuprojeto
#=> cria uma nova pasta com o nome do seu projeto.
{% endhighlight %}

{% highlight PowerShell %}
cd meuprojeto
#=> entra na pasta do seu projeto.
{% endhighlight %}

{% highlight PowerShell %}
jekyll serve --watch
#=> com o comando "serve", o Jekyll abrirá um servidor local que permite que você veja o site no seu navegador de internet.
#=> o comando "--watch" fará com que o Jekyll acomanhe as mudanças que você fará nos arquivos e repasse para o servidor local. Basta atualizar a página do seu navegador para vê-las.
{% endhighlight %}

Se der tudo certo até aqui, você verá uma notificação informando que o Jekyll está rodando neste endereço: `server address: http://0.0.0.0:4000`. A parte à esqueda da pontuação `:` corresponde ao seu ip local ou localhost. A parte da direita te informa qual é a porta que o localhost está usando. Para ver seu novo site, vá até seu navagedor e digite `localhost:4000` ou o endereço informado pelo sistema, caso seja diferente deste. Ao fazer uma mudança no seu arquivo, você terá que atualizar o navegador para vê-la.

<hr/>


### Um site Jekyll hospedado gratuitamente com o GitHub Pages

Agora temos que fazer com que o Jekyll converse com o GitHub. Partimos do princípio que você já tenha um gh-pages pronto para receber seu blog. Para fazer o setup do GitHub Pages, precisaremos escrever um novo artigo, em breve você encontrará aqui um um link para ele.

<br>

#### Configuração do **_config.yml**

1. Na pasta raiz do seu projeto, encontre o arquivo de configuração `_config.yml`. Você precisa definir algumas variáveis neste arquivo, como markdown, highlighter e baseurl. Para efeitos de GitHub, o que é fundamental é que você avise ao git onde fica sua pasta que hospedará seu site (baseurl). Portanto, informe o seguinte:
{% highlight ruby %}
baseurl: /seurepositorio
{% endhighlight %}

Esta pasta deverá ser a mesma pasta que você clonou do seu repositório git: `usuario.github.io/seurepositorio`

Isso significa que seu site ou blog morará dentro do branch gh-pages, dentro do seu repositório `seuprojeto` e que o index será acessado via `http://usuario.github.io/seurepositorio`.

<br>

#### Gerando o **Gemfile**

Será necessário gerar um "Gemfile" no seu diretório do gh-pages:

1. Abra seu editor de html e crie um novo documento na pasta raíz do seu projeto. Este arquivo deverá se chamar "Gemfile". Não dê a ele nenhuma extensão.
2. Escreva dentro dele: `gem 'github-pages'`
3. Com o prompt de comando aberto na pasta raíz do seu projeto, escreva: `bundle install`. Pronto. Assim o seu Gemfile vai ganhar uma nova cara. Se o novo Gemfile não tiver substituído o que você criou, você deverá apagar o antigo e deixar o novo criado pelo bundler.
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

<hr/>

#### **Mais informações**

Para quem entende Inglês, sugiro que siga os tutoriais em vídeo da série Jekyll do [Thomas Bradley][jekyll-youtube1]. Ficará mais fácil compreender como utilizar as ferramentas e os markdowns do Jekyll.

<hr/>

#### **Não tão simples assim...**

Infelizmente, para quem está acostumado com a liguagem html/css sem markdowns, o Jekyll pode exigir bem mais tempo para aprendizagem, mas você poderá checar uma lista de markdowns [aqui]({% post_url 2015-08-02-jekyll-github-markdown %}). Há desenvolvedores que utilizam outros geradores de sites estáticos (Static Site Generators - SSGs), em razão das limitações impostas pelo Jekyll.

Para quem precisa de websites mais elaborados com páginas de login, com CMS, com formulários de cadastro, ou mesmo sites que precisem de atualizações constantes, não recomendo nem o Jekyll e nem o GitHub Pages. Eles não têm este propósito e nem permitem estas funcionalidades. Para tais sites, é realmente necessária a interação dinâmica com o servidor, utilizando bases de dados e códigos em liguagem de servidor.   

Se você entende um pouco de Inglês, recomendo a leitura do artigo [The joy and pain of using Jekyll][pain-jekyll], que explica melhor quais são as maiores vantagens e desvantagens de usar o Jekyll.

Há uma outra fonte de prós e contras do Jekyll com o Travis Nielson, em que ele argumenta com seu amigo Jon, ambos designers. O título do vídeo é ["Jon doesn't like Jekyll"][devtips-not-jekyll].

Você poderá acessar a documentação do Jekyll no [Jekyll docs][jekyll]. Se você precisar reportar bugs e novas implementações, poderá fazê-lo no [Jekyll’s GitHub repo][jekyll-gh]. Se você tiver dúvidas, eles recomendam que os procure no [Jekyll’s Help repo][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
[github-pages]: http://pages.github.com
[pain-jekyll]: http://cristianobetta.com/blog/2013/08/21/the-joy-and-pain-of-using-jekyll/
[how-to-jekyll]: http://yizeng.me/2013/05/10/setup-jekyll-on-windows/
[jekyll-youtube1]: https://www.youtube.com/playlist?list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-
[devtips-jekyll]: https://www.youtube.com/watch?v=iWowJBRMtpc
[devtips-not-jekyll]: https://www.youtube.com/watch?v=u22CLlw4_hg
