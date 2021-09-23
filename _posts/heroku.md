---
title: "Heroku"
excerpt_separator: "<!--more-->"
tags: [python, pycharm, jupyter, package]

#subtitle: Exercícios e Referências
#layout: post
#image: /img/posts/jupyter_icon.png
#bigimg: /img/posts/jupyter_big.png
#gh-repo: michelmetran/package_jupyter
#gh-badge: [follow, star, watch, fork]
#comments: true

---

# Heroku

O [**Heroku**](https://heroku.com/) é a maneira que optei para escrever os códigos na linguagem *python*, visto que além de rodar os códigos, é possível:
1. Documentar os *scripts*, escrevendo o significado e objetivo de cada conjunto de comandos;
2. Atualizar os meus repositórios na plataforma **GitHub**;
3. Trabalhar com uma diversidade de opções de exportação do arquivo em formatos diversos, adaptados até mesmo para as simples leitura, como PDFs e Markdowns.

Com tais caraterísticas, notei que é possível publicar *posts* diretamente do *Jupyter Notebook*. Aqui pretendo apresentar um pouco das funções que tenho explorado para aperfeiçoar e facilitar minhas publicações no meu site pessoal: https://michelmetran.github.io. E, pesquisando pela internet, descobri que não sou o único a [*Exploring Jupyer Notebook to write a Blog*](https://medium.com/gopypi/exploring-jupyer-notebook-to-write-a-blog-1e7eaa913274), tem muito material a ser explorado...

<div class="alert alert-warning">
<b>OBSERVAÇÃO</b><br/>
    Esse <i>post</i> tem a finalidade de mostrar os comandos básicos e me deixar com uma "cola" rápida para meu uso cotidiano.<br/>
    Todas os códigos são exemplificativos e podem/devem ser alterados, indicando o nome dos arquivos e diretórios corretamente.
</div>

<div class="alert alert-info">
<b>INFORMAÇÃO</b><br/>
    <ol>
    <li>É possível acessar esse <i>post</i> em formato <a href="https://rawcdn.githack.com/michelmetran/package_juypter/master/docs/juypter.html" target="_blank"><i><b>html</b></i></a>, que possibilita ter uma visualização rápida do código;</li>
    <li>Diretamente por meio do <a href="https://github.com/michelmetran/package_juypter" target="_blank"><b>repositório</b></a>, onde está disponível este arquivo <i><b>.ipynb</b></i>, que permite fazer edições no código;</li>
    <li>Ou ainda, de maneira interativa, usando o <a href="https://mybinder.org/v2/gh/michelmetran/package_juypter/master" target="_blank"><i><b>MyBinder</b></i></a>, que possibilita rodar e editar o código sem a necessidade de instalar nada.</li>
    </ol>
</div>

<br>

# Instalação

Inicialmente é necessário instalar o Heroku, caso ainda não tenha instalado. No Ubuntu, basta inseriro o código abaixo no terminal.

```bash
sudo snap install --classic heroku
```

<br>

# Login

```bash
heroku login
```

<br>

# Create Repository

```bash
heroku create opencantareira
heroku create opentesouro
heroku create openfocos
```

<br>

# Commit Changes

```bash
git init
git add . -A
git commit -m 'first commit'

git init && git add . -A && git commit -m 'first commit'

git add . -A && git commit -m 'first commit'
```

<br>

# Vincular *Remote*

```bash
heroku git:remote -a opencantareira
heroku git:remote -a opentesouro
heroku git:remote -a divisoes-administrativas
```

<br>

# Collect Static

```bash
# To disable collect static
heroku config:set DISABLE_COLLECTSTATIC=1

# To enable collect static
heroku config:set DISABLE_COLLECTSTATIC=0
```

<br>

# *Push*

```bash
git push heroku master
```

<br>

# *Install Add-ons*

```bash
heroku addons:create scheduler:standard

heroku addons:open scheduler

heroku addons:docs scheduler
```

https://www.udemy.com/course/simple-blogging-analytics-dashboard-in-python/learn/lecture/12233318#overview

https://towardsdatascience.com/scheduled-web-scraping-with-django-and-heroku-e832e1363c7a

https://www.ifc.org/wps/wcm/connect/topics_ext_content/ifc_external_corporate_site/sustainability-at-ifc/company-resources/tools+for+clients

<br>

# Python Version


https://devcenter.heroku.com/articles/python-runtimes

<br>

# *Locale*

Para ver quais são os *locales* disponpíveis no Heroku, basta dar o comando:

```bash
heroku run "locale -a"
```

<br>

Para adicionar o *buildpack* no projeto do Heroku

```bash
heroku buildpacks:add https://github.com/heroku/heroku-buildpack-locale
```

<br>

Depois basta criar um arquivo chamado **```.locales```** na raiz do projeto e inserir, unicamente, o texto abaixo:

```
pt_BR.UTF-8
```

<br>

**Referências**

- [**StackOverflow**: Unsupported locale setting only at Heroku](https://stackoverflow.com/questions/53009538/unsupported-locale-setting-only-at-heroku)

- [**Gist**: Adriano Margarin](https://gist.github.com/adrianomargarin/d02ff0c457a73615671d7455bb14cae2)

- [**GitHub**: Heroku](https://github.com/heroku/heroku-buildpack-locale)

<br>

# Encoding

[Encoding error in Django on Heroku](https://stackoverflow.com/questions/23025001/encoding-error-in-django-on-heroku)

<br>

# Enviroments

https://stackoverflow.com/questions/47446480/how-to-use-google-api-credentials-json-on-heroku

```
heroku buildpacks:set https://github.com/buyersight/heroku-google-application-credentials-buildpack.git -a openfocos
heroku buildpacks:add https://github.com/elishaterada/heroku-google-application-credentials-buildpack
heroku buildpacks:add https://github.com/gerywahyunugraha/heroku-google-application-credentials-buildpack
```

Se der ruim, basta ver se no consle o conteudo do arquivo

```bash
more google-credentials.json
```



## Shell and Create User

É possível abrir um shell do python de forma remota.
Com isso é possível criar usuários!

```bash
heroku run python manage.py createsuperuser --email michelmetran@gmail.com --username michelmetran -a openescola
heroku run python manage.py createsuperuser --email admin@gmail.com --username admin -a openescola
```

<br>

# Keep Wake

https://cron-job.org/en/members/jobs/


```python
n_horas_free_mes = 1000
n_dias_mes = 31
n_apps = 5

n_horas_free_dia = n_horas_free_mes/n_dias_mes
n_horas_free_dia

n_horas_free_app = n_horas_free_dia/n_apps
n_horas_free_app
```




    6.451612903225806
