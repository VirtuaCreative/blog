---
layout: post
fb_type: article
title: Como hospedar um website gratuitamente no GitHub
fb_title: Como hospedar um website gratuitamente no GitHub
categories: [github, Github Pages, tutoriais, hospedagem gratuita]
tags: [github, hospedagem gratuita, tutoriais github, github pages, git]
meta_keywords: github, hospedagem gratuita, tutoriais github, hospedar site no github, hospedar site gratis
description: Aprenda a publicar seu website gratuitamente com o GitHub
published: True
imageUrl: https://goo.gl/DDWMXz
image: http://goo.gl/YqKqpe
author: Marcia Ramos
author_twitter: xmdramos
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
author_fb: marciaramosmdr
fb_section: Tutoriais - GitHub
comments: true
date: 2015-10-01 00:19:58 UTC
date_update: 2015-10-07 23:49:46 UTC
# language: [en_US, en_UK]
copy: true
---

# **GitHub**

Para saber o que é o **[GitHub][]** e quais são as melhores formas de aproveitá-lo, por favor leia o artigo **[O que é o GitHub - e porque utilizá-lo](http://virtuacreative.github.io/blog/introducao-ao-github.html)**, em que cobrimos os seguintes tópicos:

1. **O que é GitHub**: Como funciona / Privacidade / Cotas
2. **Hospedagem gratuita de websites com o GitHub**: Como funciona / Limitações / Extensões / Privacidade
3. **Primeiros Passos**: Criando uma conta / Criando um repositório / Adicionando arquivos / Acesso público

<br>

No presente artigo explicaremos como **hospedar gratuitamente seu website com o GitHub**, incluindo um passo-a-passo e **tutoriais em vídeo** que facilitarão o processo.

<br>

## **Como utilizar o GitHub para hospedar seu website**

<br>

### **<mkp-blue>Condições</mkp-blue>**

Para publicar seu website com o GitHub, você precisa estar ciente das seguintes condições:

1. **Primeiro**: seu código-fonte será público, ou seja, qualquer pessoa conectada à internet poderá acessá-lo.
2. **Segundo**: o GitHub suporta apenas **websites estáticos** construídos em linguagem de _web browsers_ (navegadores) e não em linguagem de servidor. Portanto, o seu website deverá ser publicado em **html**, **css** e **js**. Arquivos em php não são permitidos pelo GitHub para hospedagem, e nem o uso de base de dados - em MySQL por exemplo.
3. **Terceiro**: Você poderá utilizar os subdomínios so GitHub (sempre `nome-do-usuario.github.io`) ou seu próprio domínio (`suaempresa.com`).

Todo o processo de hospedagem oferecido pelo GitHub acontece via GitHub Pages, que será explicado em seguida.

<br>

## **Entendendo o GitHub Pages**

O [GitHub Pages][] é a ferramenta do GitHub utilizada para hospedar websites. Você poderá ter dois tipos de websites:

1. **Website do Usuário ou Organização**
2. **Website de Projetos**

Ambos hospedam os websites com as mesmas condições e características expostas no tópico anterior, mas eles diferem no método que você utilizará para colocá-los no ar.

<br>

### **<mkp-blue>Website do Usuário ou Organização</mkp-blue>**

Estes websites são construídos nos _branches_ `master` de um repositório que tenha exatamente este nome: `nome-do-usuario.github.io`, onde `nome-do-usuario`, é claro, é o seu nome de usuário. Nem uma letra nem símbolo poderá ser alterada, de outra forma não funcionará.

Ao criar um repositório com este nome, ele estará **automaticamente programado** para ser utilizado para hospedar um website, que será acessado através da URL `http://nome-do-usuario.github.io`. Ou seja, basta inserir o conteúdo do seu website neste repositório que, quando esta URL for acessada, você verá seu website no ar. 

De fato, não há difença nenhuma entre websites de usuários e de organizações. A única coisa que difere é o tipo de conta que você tem no GitHub: contas pessoais ("usuário") e contas empresariais ("organização"). As contas têm inúmeras diferenças entre si, mas **os websites são criados exatamente da mesma forma**, a partir do mesmo método descrito acima. Para mais detalhes sobre estas contas, veja nosso artigo anterior ["O que é o GitHub - e porque utilizá-lo"](http://virtuacreative.github.io/blog/introducao-ao-github.html). 

<br>

<a name="projetos"></a>

### **<mkp-blue>Website de Projetos</mkp-blue>**

Websites de projetos estão sujeitos às mesmas **três condições** descritas acima, e têm o desempenho idêntico aos websites de usuários ou organizações. O que é diferente é o método para colocá-los no ar:

1. Você poderá dar o nome que quiser ao repositório.
2. Você não poderá utilizar um _branch_ `master` - deverá criar um _branch_ chamado `gh-pages`, que será a raiz do seu website, para onde você fará o upload do conteúdo (index.html, arquivos e pastas).
3. Por padrão, seu website será acessado via `http://nome-do-usuario.github.io/nome-do-repositorio`, e não mais apenas `http://nome-do-usuario.github.io` como nos websites de usuário/organização. Mas você poderá também utilizar seu próprio domínio como endereço do website do seu projeto.

<br>

### **<mkp-blue>Vantagens</mkp-blue>** 

O maior ganho que temos é a possibilidade de utilizar uma conta do GitHub apenas para hospedar múltiplos websites. Isso mesmo, podemos criar quantos websites quisermos, pois o GitHub não impõe limite de cotas de utilização, conforme explicado detalhadamente no artigo anterior **[O que é o GitHub - e porque utilizá-lo](http://virtuacreative.github.io/blog/introducao-ao-github.html)**. Mas atenção! Você poderá publicar apenas UM website de usuário, mas poderá criar quantos websites de projetos precisar.

Então caso você precise de um website para sua empresa, com o domínio `suaempresa.com` e precise de um outro website para você mesmo, com um segundo domínio `voce.com`, é possível fazer isso com apenas uma conta do GitHub e **sem gastar um centavo** em hospedagem! Basta alocar cada um deles em um repositório diferente e pronto! :smiley:

<br>

### **<mkp-blue>Domínios próprios</mkp-blue>**

Você poderá utilizar seu próprio domínio que o GitHub fará o redirecionamento automático, tanto em websites de usuários/empresas quanto em websites de projetos. Mas este é um passo posterior que não será coberto pelo presente artigo. Mais tarde publicaremos um artigo explicando este processo, quando o fizermos vamos inserir o link aqui para você. De qualquer forma, você poderá acessar às informações diretamente no [GitHub Help Guide][here].

<br>

### **<mkp-blue>Links entre websites</mkp-blue>**

Os seus websites poderão estar "linkados" entre si, mas somente se você quiser que estejam. Para tal, basta inserir o link onde você desejar, seja em tags no conteúdo, seja em tags no menu. Basta copiar a URL e colar como valor para o parâmetro `href` do seu link. 

<br>

### **<mkp-blue>Exemplos Práticos</mkp-blue>**

Se não ficou muito claro, vamos exemplificar com os websites de Virtua Creative:

**Temos nosso website do usuário:**

Nosso usuário do GitHub, @virtuacreative, tem como **website de usuário** a seguinte URL: [http://virtuacreative.github.io](http://virtuacreative.github.io), que "mora" no repositório especialmente nomeado como `virtuacreative.github.io`.

**Temos dois websites de projetos:**

1. [Virtua Creative Blog](http://virtuacreative.github.io/blog/), acessado via `http://virtuacreative.github.io/blog`, que "mora" no repositório chamado `blog`;
2. [Virtua Creative & GitHub](http://virtuacreative.github.io/git/), acessado via `http://virtuacreative.github.io/git`, que mora no repositório chamado `git`.

As estruturas dos websites não precisam ser as mesmas, e no exemplo dado, de fato **não são**!

<br>

### **<mkp-blue>Integração com Redes Sociais e outros serviços</mkp-blue>**

Como a maior parte das empresas que fornecem serviços variados para serem integrados aos websites de terceiros normalmente fornecem um **bloco de código** pronto e escrito em **javascript** para inserirmos no `<body>` ou na `<head>` dos nossos arquivos, não há a menor dificuldade em utilizá-los. Proceda normalmente sua integração com o Google Analytics, Facebook, Twitter, Gravatar, etc.

<br>

-------------------

## **Como criar seu Website de Usuário/Organização no GitHub**

O vídeo a seguir mostra como fazer o processo inteiro. Caso prefira, logo abaixo descreveremos o passo-a-passo do processo.

<br>

<div class="iframe_container"><iframe width="853" height="480" src="http://www.youtube.com/embed/A4-yOP6JDA8" frameborder="0" allowfullscreen="allowfullscreen"> </iframe></div>

<br>

### **<mkp-blue>Passo-a-Passo</mkp-blue>**

1. Vá até o [GitHub][] e faça login na sua conta.
2. Crie um repositório de nome `nome-do-usuario.github.io` (note que, neste momento, você poderá tender a digitar apenas `.github.io`, uma vez que seu nome de usuário já aparece na tela. Não faça isso! Repita o nome do usuário, escrevendo exatamente como descrevemos.)
3. Defina-o como `Repositório Público`, de outra forma não poderá ser usado para hospedar nenhum website.
4. Defina as demais opções para seu repositório (criar automaticamente um README.md, adicionar um gitigonore e licensas para seu conteúdo). Nada disso precisa ser feito, fica a seu critério como utilizar as opções adicionais.
5. Depois de criado, o GitHub automaticamente redirecionará para a página do repositório. Nesta página, clique em `Settings` (barra lateral direita), que é a parte que define as configurações do repositório.
6. Se deu tudo certo até aqui, você verá o seguinte alerta: <strong>"Your site is published at http:// username.github.io"</strong>, mostrando o endereço de acesso do seu website de usuário/orgazinação.
  **6.1.** Neste momento, você poderá executar o comando <strong>"Launch automatic page generator"</strong>, que gerará uma Home Page para você. Ao clicar nesta opção, o GitHub o redirecionará para uma nova página, onde você poderá escolher um tema do GitHub e editar o conteúdo da sua Home Page. Ao clicar em "Publicar", seu website estará no ar. Mas digamos que você queira continuar o processo sem utilizar um dos _templates_ do GitHub, e vamos aos próximos itens.
7. Ignorando o sub-item 6.1., vamos voltar ao seu repositório e criar sua Home Page. Clique sobre o nome do repositório.
8. Clique no sinal de `+` para adicionar um arquivo. Escreva na caixa de texto `index.html`. Escreva o conteúdo na área de texto ou copie e cole de um arquivo que você já tenha pronto.
  **8.1.** Se você ainda não tem nada para colocar no arquivo, mas deseja testar o processo, copie e cole o [código abaixo](#bloco-html) na área de texto fornecida pelo GitHub. Depois você poderá voltar e editar o conteúdo como quiser.
9. Clique em `Commit New File` para salvá-lo. Pronto! Seu website já estará no ar!

<br>

<a name="bloco-html"></a>

**Bloco de código para o item 8.1.:**

<div name="clipboard-text" id="clipboard-text-UNIQUE_ID">

{% highlight html %}
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Meu novo website</title>
</head>
<body>
	<div>
		<h1>Olá Mundo!</h1>
	</div>
</body>
</html>
{% endhighlight %}

</div>

<button id="target-to-copy" data-clipboard-target="clipboard-text-UNIQUE_ID" class="target-to-copy copy btn btn-lg" title="Clique para copiar o texto acima e cole no seu documento."><i class="fa fa-files-o"></i>
&nbsp;&nbsp;Clique para copiar o código</button>

<br>

## **Passos Seguintes**

<br>

### **<mkp-blue>Criar pasta para seus arquivos CSS</mkp-blue>**

Você poderá utiliza a tag `<style>...</style>` na `<head>` dos seus arquivos `html`, mas provavelmente irá preferir criar arquivos separados para seus estilos CSS. Para fazer isso, por favor siga o [passo-a-passo](http://virtuacreative.github.io/blog/introducao-ao-github.html#add-files) explicado no artigo anterior a este. No vídeo postado acima também incluímos este processo.

<br>

### **<mkp-blue>Criar pasta para imagens no GitHub</mkp-blue>**

Para criar uma pasta e adicionar imagens a ela para que você possa inserí-las no seu website hospedado no GitHub, não é possível fazer via plataforma web. Será necessário ou fazer o processo via linha de comando ou via [GitHub Desktop][]. É um aplicativo gratuito que permite que você gerencie seus repositórios diretamente do seu computador, seja ele Windows, MAC ou Linux. Basta acessar o link e fazer o download, instalá-lo e fazer o login com sua conta do GitHub. Veja o **tutorial de como adicionar uma pasta para suas imagens no vídeo abaixo** ou siga o passo-a-passo seguinte, como preferir.

<br>

<div class="iframe_container"><iframe width="853" height="480" src="http://www.youtube.com/embed/nwJkFACNSG4" frameborder="0" allowfullscreen="allowfullscreen"> </iframe></div>

<br>

### **<mkp-blue>Passo-a-Passo</mkp-blue>**

1. Faça o download e instale o [GitHub Desktop][] e faça login na sua conta.
2. Clone seu repositório criado para websites e escolha uma pasta para alocar seus arquivos.
3. Vá até o diretório clonado e crie uma nova pasta. Digamos que sua pasta chame-se `img`
4. Adicione a esta pasta quantas imagens quiser. Digamos que uma das imagens chame-se "imagem.png"
5. Volte ao GitHub Desktop - você notará que ele detectou as alterações feitas na pasta clonada.
6. Adicione uma descrição e clique em "Commit changes" para que o GitHub processe as alterações.
7. Clique em "Sync" para fazer o upload para o GitHub.
8. Volte na plataforma web do [GitHub] e veja as alterações.
9. Abra uma nova aba no seu navegador e entre entre no seu website em  `http://nome-do-usuario.github.io`.
10. Acrescente o endereço da imagem: `http://nome-do-usuario.github.io/img/imagem.png` e aperte "enter" no seu teclado.
11. Certifique-se de que o endereço digitado está certo. Se estiver, a imagem abrirá conforme o esperado.
12. Copie o endereço completo da imagem `http://nome-do-usuario.github.io/img/imagem.png`
13. Volte ao GitHub e edite seu arquivo html. Insira nele o link para a imagem e estilize conforme desejar.
14. Salve seu aquivo fazendo um "Commit changes" e pronto! Lá estará sua imagem carregada no seu website!
15. Repita os passos 9 a 12 para copiar novos links para suas imagens e inserí-las nos seus arquivos html conforme desejar.

Caso precise, aqui está um exemplo de tag de imagem para ser inserida no `<body>` do seu arquivo `html`:

<div name="clipboard-text" id="clipboard-text-2">

{% highlight html %}

<img src="http://nome-do-usuario.github.io/img/imagem.png" alt="Exemplo de Imagem">

{% endhighlight %}

</div>

<button id="target-to-copy" data-clipboard-target="clipboard-text-2" class="target-to-copy copy btn btn-lg" title="Clique para copiar o texto acima e cole no seu documento."><i class="fa fa-files-o"></i>
&nbsp;&nbsp;Clique para copiar o código</button>

<br>

### **<mkp-blue>Criar websites de projetos no GitHub</mkp-blue>**

Caso você precise criar um [website de projeto](#projetos), conforme explicamos acima, por favor pedimos que volte mais tarde, pois estamos preparando um tutorial em vídeo para este passo. Quando estiver pronto, incluiremos o video aqui. Adicione nosso [Blog ao seu feed][news feed], siga-nos no [Twitter] e/ou inscreva-se no nosso [Canal do YouTube] para receber em primeira mão!  

<br>

### **<mkp-blue>Isso é tudo, pessoal!</mkp-blue>**

Esperamos ter sido úteis! Por favor, contribua para o assunto deixando seu comentário abaixo! Se você gostou do artigo, deixe-nos saber disso, pois nos estimulará a continuar escrevendo!

Se você tiver dúvidas ou sugestões, comente ou acesse nosso [formulário de contato](http://virtuacreative.github.io/git/contact.html).

Obrigada e até o próximo artigo!

<br>

---------------

### **Artigos relacionados**

[O que é GitHub - e porque utilizá-lo](http://virtuacreative.github.io/blog/introducao-ao-github.html)
[O que é Jekyll - e para que ele serve](http://virtuacreative.github.io/blog/jekyll-for-beginners-introduction.html)
[Criando blogs com Jekyll no Windows](http://virtuacreative.github.io/blog/jekyll-github-blog.html)
[Jekyll e GitHub Markdown](http://virtuacreative.github.io/blog/jekyll-github-markdown.html)

<br>

---------------

### **Referências**

[GitHub][]
[GitHub Desktop][]
[GitHub Pages][]
[User, Organization and Project Pages](https://help.github.com/articles/user-organization-and-project-pages/)



[Canal do YouTube]: http://www.youtube.com/c/VirtuaCreativeBrWebsites 
[Twitter]: https://twitter.com/virtuacreative
[Blog]: http://virtuacreative.github.io/blog/
[GitHub Desktop]: https://desktop.github.com/
[GitHub]: https://github.com
[GitHub Help Guide]: https://help.github.com/articles/user-organization-and-project-pages/
[news feed]: http://virtuacreative.github.io/blog/feed.xml
[GitHub Pages]: https://pages.github.com/
[here]: https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/