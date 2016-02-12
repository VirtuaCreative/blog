---
layout: post
fb_type: article
fb_section: Tutorials - Jekyll
title: Jekyll e GitHub Markdown
fb_title: Jekyll e GitHub Markdown
categories: [jekyll, Github, Tutoriais, Blog]
tags: [git, jekyll, markdown, kramdown, emoji]
meta_keywords: git, jekyll, markdown, kramdown, emoji
description: Lista prática de markdowns do Jekyll para o GitHub.
image: https://goo.gl/CbwGMU
image_schema: 'https://c2.staticflickr.com/4/3826/20355844915_657dc373d8_b.jpg'
imageUrl: https://www.flickr.com/photos/virtuacreative/20355844915
author: Marcia Ramos
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
author_fb: marciaramosmdr
author_twitter: xmdramos
authorEmail: virtua.creative@gmail.com
comments: true
date: 2015-08-02 17:47:29 UTC
date_update: 2016-02-12 15:26:59 UTC
# language: [pt_BR]
---

# **Markdown**

Para facilitar a escrita com o **Jekyll**, este artigo apresenta uma lista de _markups_ em markdown [Kramdown](http://kramdown.gettalong.org/syntax.html) de arquivos com as extensões `.md` ou `.markdown`. 

Eu mesma uso o conteúdo deste artigo como guia quando não lembro de algum markup, por isso resolvi publicá-lo e deixá-lo à mão para a comunidade web também. 

Este artigo parte do princípio que você já tem o Jekyll instalado e usa o GitHub Pages para publicar seu site ou seu blog. Se você precisa de mais informações sobre isso, veja o artigo [Criando Blogs com Jekyll no Windows]({{ site.baseurl }}{% post_url 2015-07-30-jekyll-github-blog %}).

[Veja abaixo](#config) as configurações aplicadas ao `_config.yml`.


<br>  

---------------------

## **<mkp-blue>Markups Básicos</mkp-blue>**

 <br>   

#### **Títulos**

{% highlight html %}
# Texto = <h1>Texto</h1>
## Texto = <h2>Texto</h2>
### Texto = <h3>Texto</h3>
{% endhighlight %}

 <br>   

#### **Enfases**

_Itálico_ e __negrito__: <br/>
*Itálico e **negrito-itálico**:*
{% highlight markdown %}
*Texto em Itálico*
_Texto em itálico_

**Texto em negrito**
__Texto em negrito__

*Texto em itálico e em **negrito-itálico**!*

#### **Título em negrito**
{% endhighlight %}

<br>  

#### **Listas**

Ordenadas:

1. Item 1
2. Item 2
    2.1. Sub-item 2.1
    2.2. Sub-item 2.2

{% highlight markdown %}
1. Item 1
2. Item 2
    2.1. Sub-item 2.1
    2.2. Sub-item 2.2
{% endhighlight %}

Não-ordenadas:

- Item 1
- Item 2
    - Sub-item 2.1
    - Sub-item 2.2

{% highlight markdown %}
- Item 1
- Item 2
    - Sub-item 2.1
    - Sub-item 2.2
{% endhighlight %}

 <br>   

#### **Imagens**

![Virtua Creative Logo](http://www.gravatar.com/avatar/6fa7e8a0b8a820fa63c7cfd1833b1be4 "VirtuaCreative")

{% highlight markdown %}
![Texto ALT](url "Título")
{% endhighlight %}

_Alt_ e _Título_ não são obrigatórios.

 <br>  

#### **Links**

[Virtua Creative Technology](http://virtuacreative.com.br)

{% highlight markdown %}
[Texto impresso](url)
{% endhighlight %}

  <br>  

#### **Âncoras**

Digâmos que você usar a palavra a seguir como âncora. 

Olá. Eu sou uma <a name="ancora"></a> âncora!

O texto ficará assim:
{% highlight markdown %}
Olá. Eu sou uma <a name="ancora"></a> âncora!
{% endhighlight %}

E para recuperar a âncora, você poderá denotá-la como um link comum:

Quero citar minha [âncora](#ancora).

Seu texto estará escrito assim:
{% highlight markdown %}
Quero citar minha [âncora](#ancora).
{% endhighlight %}

 <br>   

#### **Tabelas**

As tabela são criadas com hifens e barras verticais. O cabeçalho é separado do restante da tabela por traços e as colunas são separadas por barras. O código a seguir...


{% highlight markdown %}
Cabeçalho Um	 | Cabeçalho Dois
---------------	 | --------------
Célula Um    	 | Célula Dois
Célula Três  	 | Célula Quatro
{% endhighlight %}

...produzirá esta tabela...

Cabeçalho Um 	| Cabeçalho Dois
----------------|-----------------
Célula Um    	| Célula Dois
Célula Três  	| Célula Quatro

...que foi estilizada no <a name="table-css"></a>css:

{% highlight css %}
.article_body table thead tr th {
	min-width: 150px;
	padding: 20px 10px 20px 5px;
	border-bottom: 1px solid lightgray;
	border-top: 1px solid lightgray;
} 

.article_body table tbody tr td {
	min-width: 150px;
	padding: 10px 5px 10px 5px;
	border-bottom: 1px solid lightgray;
} 

.article_body table {
	margin-bottom: 30px;
	margin-top: 30px;
} 
{% endhighlight %}

Você poderá utilizar o "Inspecionar elemento" do seu navegador para ver exatamente a qual classe a tabela pertence. No caso acima, pertence à classe `.article_body`. Você poderá omitir a classe e aplicar o estilo somente ao elemento `table`, e assim afetará todas as tabelas do seu site.

Você poderá aplicar o markdown para negrito e itálico normalmente no conteúdo da tabela. Para alinhar o texto (à esquerda, à direita e cetralizar), usa-se `:` entres as barras horizontais:

Este código...

{% highlight text %}

| Coluna Um | Coluna Dois | Coluna Três |
| :-------- | :--------: | --------: |
| Célula 1 - _Esquerda_ | Célula 2 - _Centro_ | Célula 3 - _Direita_ | 	
| Célula Quatro | Célula Cinco | Célula Seis |

{% endhighlight %}

...produzirá esta tabela:

| Coluna Um | Coluna Dois | Coluna Três |
| :-------- | :--------: | --------: |
| Célula 1 - _Esquerda_ | Célula 2 - _Centro_ | Célula 3 - _Direita_ | 	
| Célula Quatro | Célula Cinco | Célula Seis |

Conforme acima, a "coluna um" aparecerá com o texto alinhado à esquerda; a "coluna dois", centralizada; e a "coluna três", à direita. Note que o as barras verticais não precisam estar simetricamente dispostas. O estilo aplicado à tabela é o mesmo definido no [CSS](#table-css) anteriormente

<br>

#### **Códigos**

As formas de exibir códigos em markdown mais utilizadas são:

**<mkp-blue>1. Código Inline</mkp-blue>**

Este é um `código inline`.

{% highlight html %}
Este é um `código inline`
{% endhighlight %}

**<mkp-blue>2. Blocos de Código</mkp-blue>**

**<mkp-blue>2.1. Utilizando </mkp-blue>** _**<mkp-blue>"Fenced Code Blocks"</mkp-blue>**_ **<mkp-blue>ou</mkp-blue>** _**<mkp-blue>"Backticks"</mkp-blue>**_

Código em blocos, com a linguagem definida:

{% highlight html %}{% raw %}```html{% endraw %} 
Este é um código html em bloco em markdown puro.
<h1>Hello world!</h1>
{% raw %}```{% endraw %}{% endhighlight %}

**<mkp-blue>2.2. Utilizando </mkp-blue>**_**<mkp-blue>Liquid</mkp-blue>**_ **<mkp-blue>tags</mkp-blue>**

Definindo apenas a liguagem:

{% highlight html %}{% raw %}{% highlight html %}{% endraw %} 
Este é um código html em bloco via liquid tags!
{% raw %}{% endhighlight %}{% endraw %}{% endhighlight %}

Inserindo número das linhas ao código em bloco:

{% highlight html linenos %}{% raw %}{% highlight html linenos %}{% endraw %} 
Este é um código html em bloco com linhas numeradas!
<h1>Hello world!</h1>
{% raw %}{% endhighlight %}{% endraw %}{% endhighlight %}

Aqui o interessante é que você pode colorir os números no seu css, como você notou no bloco acima. Para fazer isso, vá até o seu css e atribua uma cor para a classe `linenos` que será compilado a uma `<pre>` tag:

Como o markdown é transformado em html:
{% highlight html %}
<pre class="lineno">1 2 3</pre>
{% endhighlight %}

atribua a classe no seu `style.css`:
{% highlight css %}
.lineno {
	color: red;
}
{% endhighlight %}

**<mkp-blue>3. Códicos via</mkp-blue>** _**<mkp-blue>Indentation</mkp-blue>**_

Adicione 4 espaços em branco antes de qualquer texto que este aparecerá em bloco de código, como a seguir:

    hello world!


<br>   

--------------
 
## **<mkp-blue>Markups Avançados</mkp-blue>**

<br>
 
#### <a name="arroba"></a>**Links para Usuários**

Se você achou que este artigo foi útil, poderá dar uma :star: para @virtuacreative !

O link para o perfil de Virtua Creative no Github na frase acima foi adicionado com um simples arroba na frente do meu nome de usuário.

O único detalhe é que você precisa "ativar" a menção de usuários nos seus artigos adicionado uma linha `gems` ao seu `_config.yml`:

{% highlight yml %}

gems:
  - jekyll-mentions

{% endhighlight %}

Neste caso, o padrão será para citação de usuários do GitHub.

<br>

Caso prefira, poderá definir o a menção de usuários de outras redes sociais, desta forma:

{% highlight yml %}
gems:
  - jekyll-mentions

jekyll-mentions:
  base_url: https://twitter.com
{% endhighlight %}

**Visualização Local**

Para poder visualizar as menções no seu localhost, será necessário instalar uma `gem` do Ruby. Antes disso, verifique e sua versão do GitHub Pages está atualizada.

{% highlight ruby linenos %}

gem update github-pages
#ou
bundle update github-pages
#depois:
gem install github-markup
#depois:
gem install jekyll-mentions
{% endhighlight %}

_Observações:_

- Linha 1 ou 3: ambos funcionam; apenas depende da forma que você utilizou para instalar a gem do github-pages. 

- Linha 5: instala o GFM - habilita o mesmo markdown que usamos diretamente nos arquivos `.md` dos repositórios do git.

- Linha 7: habilita a visualização dos links usados com o arroba no seu localhost.

Este blog usa o kramdown como markdown, se você estiver usando outros, não saberia dizer até que ponto esta lista funcionaria.

Para habilitar o GFM, é necessário que o inclua no seu `_config.yml`, desta forma:

{% highlight yml linenos %}
markdown: kramdown

kramdown:
  input: GFM
{% endhighlight %}

_Observações:_
A linha um define o markdown que você está usando. A linha 4 insere um input no kramdown.
<br>

#### **Carinhas (Emoticons)**

É bacana poder usar o markdown para descontrair o texto com os emoticons que conhecemos :smiley: !

Você poderá acessar do seu :computer: toda a coleção de carinhas!

<br>

Sintaxe:

Veja como escrever esta frase: 

"Vamos ilustrar com um gravatinha :bowtie: e com uma setinha :arrow_left:" 

{% highlight markdown %}
Vamos ilustrar com um gravatinha : bowtie :  e com uma setinha : arrow_left : 
{% endhighlight %}

Veja o link [Emoji - Lista de Emoticons](http://www.emoji-cheat-sheet.com/) para a lista completa de emoticons. Clicando sobre eles, você estará copiando o código, portanto basta colar no seu texto.

Seguindo a mesma lógica dos [links para usuários](#arroba), você precisará habilitar o uso do Emoji no seu site, adicionando ao `_config.yml`:

{% highlight yml %}
gems:
  - jemoji
{% endhighlight %}

Se você usar tanto o Emoji quanto o Mentions, como é o caso deste blog, simplesmente coloque um sobre o outro nos `gems` do seu `_config.yml`:

{% highlight yml %}

gems:
  - jekyll-mentions
  - jemoji

{% endhighlight %}

Ainda seguindo a lógica dos [links para usuários](#arroba), você precisará adicionar uma [gem](https://github.com/jekyll/jemoji) no seu PC para visualizar os emoticons localmente:

{% highlight ruby %}

gem install jemoji

{% endhighlight %}

<br>

<a name="config"></a>

## **`_config.yml`**

Para simplificar seu entendimento, vou mostrar abaixo como ficou o meu `_config.yml` para usar todos os _markups_ de __markdown__ citados neste artigo:

{% highlight yml %}
# demais configurações...

highlighter: rouge
markdown: kramdown
kramdown:
  input: GFM

gems:
  - jemoji
  - jekyll-mentions

# demais configurações...
{% endhighlight %}

<br>

**Pronto!**

É isso gente, para checar as informações acima, veja abaixo a lista de referências utilizadas para elaborar o artigo.

Se gostou do artigo, por favor deixe a gente saber disso nos comentários abaixo! :clap: :grimacing: :clap: 

Deixe seu comentário se puder complementar, dar mais algumas dicas, sugestões e deixar sua contribuição para a comundade!

Obrigada!

<br>


#### **Referências**

<br>

- [Referência completa](http://daringfireball.net/projects/markdown/basics) sobre markdown
- [Referência completa para Kramdown](kramdown.gettalong.org/syntax.html)
- [Referência básica](https://help.github.com/articles/markdown-basics/) para markdown
- [Referência do GFM](https://help.github.com/articles/github-flavored-markdown/)
- [Emoji - Lista de Emoticons](http://www.emoji-cheat-sheet.com/)
- [Instalação local do Markup do GitHub](https://github.com/github/markup)
- [Instalação/Update local do GitHub Pages](https://github.com/github/pages-gem)
- [Instalação local do Emoji - Emoticons](https://github.com/jekyll/jemoji)
- [Instalação local do Jekyll Mentions](https://github.com/jekyll/jekyll-mentions)
- [Kramdown + GFM - Jekyll Docs](http://jekyllrb.com/docs/configuration/#kramdown)
