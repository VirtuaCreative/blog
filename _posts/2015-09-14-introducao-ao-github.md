---
layout: post
fb_type: article
title: O que é GitHub - e porque utilizá-lo
fb_title: O que é GitHub - e porque utilizá-lo
categories: [github, github pages, hospedagem gratuita]
tags: [github, hospedagem gratuita, tutoriais github]
meta_keywords: github, hospedagem gratuita, tutoriais github, hospedar site no github, repositórios, o que é github, adicionar arquivo github, criar pasta github, entendendo o github
description: Entenda o que é o GitHub - e como você poderá aproveitá-lo
published: True
imageUrl: https://goo.gl/pqENyT
image: http://goo.gl/MqEtlk
image_schema: 'http://c1.staticflickr.com//1//695//20806891933_94f7b97aae_h.jpg'
author: Marcia Ramos
author_twitter: xmdramos
authorUrl: https://plus.google.com/+MarciaDiasRamosMD/
author_fb: marciaramosmdr
fb_section: Tutorials - GitHub
comments: true
date: 2015-09-14 23:41:41 UTC
date_update: 2016-01-09 00:23:31 UTC
# language: [en_US, en_UK]
---

# **O que é GitHub**

O **[GitHub][]** é uma rede social para programadores e desenvolvedores web, criada com o objetivo primário de compartilhar códigos, programas e plug-ins entre pessoas da área. Além do compartilhamento, ele pode ser usado para:

- :point_right:  permitir acesso a múltiplos desenvolvedores em empresas de tecnologia, dando a possibilidade de vários programadores trabalharem no mesmo arquivo, a partir de qualquer computador conectado à internet;
- :point_right:  hospedar websites gratuitamente;
- :point_right:  fazer backup de seus websites e arquivos.

### **<mkp-blue>Como funciona</mkp-blue>**

O Github funciona a partir de **repositórios**, que funcionam como pastas criadas para armazenar seus arquivos. Dentro destas pastas, você poderá criar novas pastas, contendo vários tipos de arquivos: html, css, javascript, documentos de texto, php, pdf, imagens, gráficos, json, markdown, entre outros.

A partir dos repositórios, o GitHub oferece a possibilidade de fazer o download de conteúdos e de contribuir para o desenvolvimento de arquivos.

### **<mkp-blue>Privacidade</mkp-blue>**

A versão gratuita do GitHub oferece todas as possibilidades mencionadas acima, mas todos os repositórios serão públicos e acessíveis a qualquer pessoa com conexão à internet. Caso você queira limitar acesso somente a você mesmo ou a determinados usuários, será necessário criar um repositório privado - para tal, é necessário fazer o upgrade para uma [conta paga][paid].

Ao utilizar o GitHub para fazer backup de seus arquivos, recomendamos que seja utilizada a conta paga. Desta forma, seus arquivos estarão protegidos em seus repositórios privados.

### **<mkp-blue>Cotas</mkp-blue>**

O GitHub não impõe um limite para uso da capacidade de arquivamento, como você poderá constatar [neste link][quota]. Isso mesmo, não há limites para upload de arquivos! Mas lembre-se, os repositórios de conta gratuita são públicos e podem ser acessados por qualquer pessoa. Se você deseja utilizá-lo com arquivos privados, você precisará registrar-se para uma conta paga.

Com a [partir de US$ 7,00][paid] (valor válido na data de publicação deste artigo), você poderá ter acesso a repositórios privados, permitindo assim com que você use o GitHub para guardar seus arquivos com privacidade e segurança.

<br>

#### **Limites de tamanho de arquivo**

Você poderá fazer uploads de arquivos de até 100 MB sem precisar nenhuma configuração extra. Caso seu arquivo seja maior que 100 MB, você poderá instalar uma [extensão para lidar com grandes arquivos][large]. Chama-se [Git Large Storage Extension][glfe], e poderá ser instalada e utilizada inclusive com a versão gratuita do GitHub.

<br>

#### **Limite de tamanho de repositório**

O [GitHub recomenda][limits] que um repositório não ultrapasse o limite de 1 GB, mas você poderá utilizar o [Git Large Storage Extension][glfe] para estender esta capacidade, embora o GitHub ainda não tenha expressamente especificado qual será o limite de armazenamento. 

<br>

---------------------------------

# **Hospedagem gratuita de websites com o GitHub**

<br>

Uma das possibilidades mais interessantes do GitHub para não-programadores é a capacidade de hospedar websites inteiros gratuitamente. Isso mesmo! Hospedagem grátis!

<br>

### **<mkp-blue>Como funciona a hospedagem gratuita do GitHub</mkp-blue>**

Para hospedar seu website, você precisará criar uma conta no GitHub e criar um repositório. Há certas especificações e passos a serem seguidos, e você poderá encontrá-los no artigo **[Como hospedar um website gratuitamente no GitHub]({{ site.baseurl }}/hospedar-website-gratis-com-github.html)**.

Seu website poderá ser acessado através de um subdomínio do GitHub `suaempresa.github.io` ou através do seu próprio domínio, `www.suaempresa.com`. Veja exemplos: [http://virtuacreative.github.io](http://virtuacreative.github.io) e [https://jekyllrb.com/](https://jekyllrb.com/)

<br>

### **<mkp-blue>Limitações</mkp-blue>**

<br>

#### **Cotas**

Embora não haja limite de arquivos armazenados, **o GitHub recomenda que os repositórios não ultrapassem o limite de 1 GB**. Dificilmente este limite será excedido em um website comum. Porém, caso seu website ultrapasse esse limite, o que você poderá fazer para contornar este problema de forma simples, é criar outro repositório para armazenamento de mais arquivos, e adicionar links diretos entre ambos. 

Para ver um exemplo prático, veja que nosso website [http://virtuacreative.github.io](http://virtuacreative.github.io), que "mora" no repositório `virtuacreative.github.io` dá acesso ao nosso website [Virtua Creative & GitHub][] `http://virtuacreative.github.io/git/`, que "mora" no repositório `git` e a este [Blog][] `http://virtuacreative.github.io/blog/`, que "mora" no repositório `blog`. Ambos têm links um para o outro. Não é o caso, mas cada um deles poderia suportar até 1GB de armazenamento cada, totalizando 3GB para um único subdomínio `virtuacreative.github.io`

<br>

#### **Extensões**

O GitHub suporta apenas **websites estáticos** construídos em linguagem de _web browsers_ (navegadores) e não em linguagem de servidor. Portanto, o seu website deverá ser publicado em **html**, **css** e **js**. Arquivos em php não são permitidos pelo GitHub para hospedagem, e nem o uso de base de dados - em MySQL por exemplo. 

Para desenvolvedores web que utilizam o `php` para criar websites dinâmicos, há uma ferramenta extremamente útil que poderá simular os `php includes`: o **Jekyll** - criador de websites estáticos a partir de escrita dinâmica. Para saber mais, recomendamos a leitura dos nossos artigos: "[O que é o Jekyll - e para que ele serve]({{ site.baseurl }}/jekyll-for-beginners-introduction.html)" e "[Criando blogs com Jekyll no Windows]({{ site.baseurl }}/jekyll-github-blog.html)".  

<br>

#### **Privacidade**

Todo repositório criado com a intenção de hospedar um website **deverá** ser um **repositório público**. Portanto, mesmo que você tenha uma conta paga, que lhe permita criar repositórios privados, todo website hospedado com o GitHub deverá ser público e seu código estará visível a qualquer pessoa conectada à internet. Então, caso você pretenda utilizar conteúdos sensíveis no seu site, não recomendamos o uso do GitHub para hospedá-lo.

<br>

### **<mkp-blue>Primeiros Passos</mkp-blue>**

<br>

#### **Criando uma conta**

Criar uma conta no GitHub é tão simples como fazê-lo no Facebook, Twitter ou qualquer outro website. Basta acessar o [GitHub][], criar um nome de usuário, entrar com seu email e com uma senha e pronto! Sua conta terá sido criada.

Lembre-se de criar um nome de usuário que corresponda ao que você ou sua empresa representa, uma vez que todo o acesso público será dado via nome de usuário. Por exemplo, se seu nome é João Pedro Silva, evite criar um usuário de nome `joao12345`; tente algo que faça referência a você, como `joaopedro` ou algo parecido. 

O GitHub dá a possibilidade de você transformar sua conta pessoal numa conta de organização (empresa). Com esta conta, você poderá dar acesso à conta a várias pessoas que trabalham para você, com permissões diferentes. Se este for seu caso, pense nesta opção. Entretanto, caso você seja o único a utilizar a conta, pense em mantê-la como conta pessoal (por mais que seu nome de usuário refira-se à sua empresa), principalmente caso você queira fazer o upgrade à conta paga. Os [valores pagos][paid] para conta organização são maiores que os para contas pessoais.

<br>

#### **Criando um repositório**

Criar um repositório também é bastante simples: após acessar sua conta, clique em **"New Repository"**, escolha um nome, adicione uma descrição (caso queira), escolha se deverá ser público ou privado, e caso deseje, escolha campos alternativos: 

- a. adicione um `gitignore` (um documento que dará o comando para ignorar arquivos - mais comumente utilizado ao criar um repositório para hospedar um website);
- b. adicione uma licença para garantir seus direitos autorais.

<br>

<a name="add-files"></a>

#### **Adicionando arquivos**

Existem algumas formas de inserir arquivos ao seu repositório:

1. **do seu computador**: faça o download do [GitHub Desktop][desk] e trabalhe de um aplicativo diretamente do seu desktop (seja ele Windows, Mac ou Linux) - é o método mais imediato e fácil de começar a usar. Veja a documentação [aqui][desk-docs];

2. **da linha de comando**, através do seu prompt (veja uma série de linhas de comando básicas neste [link][prompt]);

3. **do site do GitHub**: acesse sua conta, clique no seu repositório. Na barra superior você verá o nome do seu repositório seguido de uma barra `/` e um sinal `+`, conforme a imagem abaixo (Obs: nesta imagem, o nome do repositório utilizado para este exemplo é `git`). Clique no sinal `+`.
	![1][]

	3.1. Em seguida, você verá na mesma área uma caixa de texto precedida pelo nome do seu repositório e a barra `/`. Nesta caixa, escreva o **nome do arquivo e sua extensão** (por exemplo, `index.html` ou `informacoes.md` ou `style.css` ou qualquer outra possibilidade que tenha em mente). 
	![2][]

	3.2. Caso queira **criar uma nova pasta**, escreva na mesma caixa de texto referida acima o nome da sua pasta seguido de `/` que o GitHub automaticamente criará a pasta para você. Neste exemplo, escrevemos `NOVA-PASTA/`. Em seguida, escreva o nome do arquivo na nova caixa de texto que surgirá. 
	![3][]

	Note que, para que uma pasta exista, é necessário que haja pelo menos um arquivo dentro dela. **Não é possível criar uma pasta vazia**.

	3.3. Escreva seu novo arquivo  - ou copie e cole seu texto -  e o salve conforme explicado no item abaixo.

	3.4. Para **salvar seu aquivo**, você precisará fazer um `commit`, preenchendo os seguintes campos: 
	![4][]

	Escreva na primeira caixa o que você está inserindo, por exemplo: "adicionando info.md". Na segunda caixa de texto, poderá escrever uma descrição longa relativa à ação. Por exemplo: "adicionando novo arquivo de informações para usuários da Língua Portuguesa". Clique em `Commit New File` e pronto! Seu arquivo terá sido criado.

	Note que a cada alteração de qualquer arquivo você vai precisar fazer um `commit`, independente de qual plataforma você estiver utilizando (prompt, GitHub Desktop ou web). É bastante útil detalhar as informações de alteração de arquivos a cada _commit_, principalmente se você estiver trabalhando em grupo. Desta forma, cada um dos seus colegas saberá exatamente o que foi alterado no arquivo a cada passo. Mesmo se estiver trabalhando sozinho, é uma forma de "comentar" cada alteração em seus arquivos, evitando assim que você se perca em seu próprio fluxo de _updates_.

	Note também que, via de regra, todo repositório começa com um arquivo chamado `README.md`. Neste arquivo você deve escrever do que se trata o repositório. Não é obrigatória a presença deste arquivo, mas esta prática é comum à maioria dos usuários do GitHub. Arquivos com a extensão `.md` ou `.markdown` são escrito em Markdown, uma linguagem amplamente utilizada no GitHub para publicação de arquivos de texto. Por exemplo, neste link você poderá ver o repositório do Jekyll e como ele utiliza o arquivo `README` para explicar do que se trata:  [Jekyll no GitHub](https://github.com/jekyll/jekyll). Veja nosso artigo ["Jekyll e GitHub Markdown"]({{ site.baseurl }}/jekyll-github-markdown.html) para saber como escrever em Markdown.

<br>

#### **Acesso público ao repositório e seus arquivos**

Todo repositório público poderá ser acessado via url escrita neste formato: `github.com/nome-do-usuario/nome-do-repositorio`. Por sua vez, quando o repositório for criado para hospedar um website, ele poderá ser acessado de duas formas: 

1. no formato mencionado anteriormente - levará aos arquivos do website;
2. no formato `nome-do-usuario.github.io` - levará ao website do usuário ou organização;
3. no formato `nome-do-usuario.github.io/nome-do-repositorio/` - levará ao website do projeto.

Entenda a diferença entre os tipos de website (usuário/organização e projeto) no artigo **[Como hospedar um website gratuitamente no GitHub]({{ site.baseurl }}/hospedar-website-gratis-com-github.html)**. Siga-nos no [Twitter][] para receber a chamada em primeira mão!

<br>

#### **Considerações finais**

Este artigo descreveu brevemente uma introdução ao uso do GitHub. Outras funcionalidades podem ser atingidas, como, por exemplo, o trabalho com diferentes tipos de `branches` - são tipos de conteúdos dentro dos repositórios, ou ainda, o comando `fork`, que permite a criação de um projeto sobre outro já existente, ou ainda a função `contribute` que permite que várias pessoas trabalhem no mesmo repositório, entre outras funcionalidades avançadas que não convém serem detalhadas em artigos introdutórios como este.

Nosso artigo **[Como hospedar um website gratuitamente no GitHub]({{ site.baseurl }}/hospedar-website-gratis-com-github.html)** cobre os aspectos do uso do GitHub para hospedagem de websites, caso seu interesse no GitHub seja este. Por isso este tema não foi detalhado no presente artigo.

Esperamos que este artigo tenha sido útil para você, no sentido de dar uma visão geral sobre o uso do GitHub e das funcionalidades que ele oferece.

Para enriquecer o assunto, sinta-se convidado para deixar seu comentário abaixo! Obrigada e até o próximo artigo! :smiley:

<br>

_Siga Virtua Creative no **[Twitter][]** para receber nossos artigos em primeira mão!_


<!-- Referências -->


[GitHub]: https://github.com/
[gh-pages]: https://pages.github.com/
[quota]: https://help.github.com/articles/what-is-my-disk-quota/
[large]: https://help.github.com/articles/working-with-large-files/
[limits]: https://help.github.com/articles/what-is-my-disk-quota/#file-and-repository-size-limitations
[glfe]: https://git-lfs.github.com/
[paid]: https://github.com/pricing
[desk]: https://desktop.github.com/
[desk-docs]: https://help.github.com/desktop/guides/getting-started/
[1]: http://virtuacreative.github.io/git/img/git_new_file.PNG
[2]: http://virtuacreative.github.io/git/img/git_new_file1.PNG
[3]: http://virtuacreative.github.io/git/img/git_new_folder_file.PNG
[4]: http://virtuacreative.github.io/git/img/git_new_commit.png
[prompt]: https://github.com/fernandomayer/git-rautu/blob/master/1_comandos-basicos.md
[Twitter]: {{ site.data.url.virtua.twitter }}
[Virtua Creative & GitHub]: {{ site.data.url.virtua.git }}
[Blog]: {{ site.data.url.virtua.blog }}