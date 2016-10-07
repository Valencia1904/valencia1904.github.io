---
layout: index

title: Creando una pagina en GitHubPage
tagline: Valencia1904.github.io
---

# Creandonos una GitHubPage

Vamos a ver los pasos necesarios para crear una página estática con GitHubPage.

### Crear un repositorio
Primero nos crearemos un repositorio GitHub con nuestro nombre de usuario GitHub.

![captura 1](images/githubpage/1.png)

### Añadir estilo

En settings buscamos el apartado de GitHub Pages.

Le damos a "Launch automatic page generator" 

![captura 2](images/githubpage/2.png)

![Captura 3](images/githubpage/3.png)

Selecciona el estilo de tu gusto.

![Captura 4](images/githubpage/4.png)

Veremos el repositio con el siguiente contenido:
Los elementos necesarios para la hoja de estilo.
y un index.html de ejemplo.

![Captura 5](images/githubpage/5.png)

Clonaremos nuestro repositorio en nuestra maquina.

> git clone git@github.com:Valencia1904/Valencia190.github.io.git

En vuestro caso devereis copiar vuestra direccion git del repositorio.

![captura 6](images/githubpage/6.png)

#### Creación de estructura.

Nos creamos la carpeta _layouts.

Movemos el fichero index.html a la carpeta _layouts.

Por seguridad copiamos nuestro index.html como old.index.html.

Y lo modificamos.

Al principio sería algo así.

```

<!DOCTYPE html>
<html lang="en-us">
  <head>
    <meta charset="UTF-8">
    <title>Valencia1904.GitHub.io by Valencia1904</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" type="text/css" href="stylesheets/normalize.css" media="screen">
    <link href='https://fonts.googleapis.com/css?family=Open+Sans:400,700' rel='stylesheet' type='text/css'>
    <link rel="stylesheet" type="text/css" href="stylesheets/stylesheet.css" media="screen">
    <link rel="stylesheet" type="text/css" href="stylesheets/github-light.css" media="screen">
  </head>
  <body>
    <section class="page-header">
      <h1 class="project-name">Valencia1904.GitHub.io</h1>
      <h2 class="project-tagline"></h2>
    </section>

    <section class="main-content">
      <h3>
 <a id="welcome-to-github-pages" class="anchor" href="#welcome-to-github-pages" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Welcome to GitHub Pages.</h3>

 <p>This automatic page generator is the easiest way to create beautiful pages for all of your projects. Author your page content here <a href="https://guides.github.com/features/mastering-markdown/">using GitHub Flavored Markdown</a>, select a template crafted by a designer, and publish. After your page is generated, you can check out the new <code>gh-pages</code> branch locally. If you’re using GitHub Desktop, simply sync your repository and you’ll see the new branch.</p>

 <h3>
 <a id="designer-templates" class="anchor" href="#designer-templates" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Designer Templates</h3>

 <p>We’ve crafted some handsome templates for you to use. Go ahead and click 'Continue to layouts' to browse through them. You can easily go back to edit your page before publishing. After publishing your page, you can revisit the page generator and switch to another theme. Your Page content will be preserved.</p>

 <h3>
 <a id="creating-pages-manually" class="anchor" href="#creating-pages-manually" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Creating pages manually</h3>

 <p>If you prefer to not use the automatic generator, push a branch named <code>gh-pages</code> to your repository to create a page manually. In addition to supporting regular HTML content, GitHub Pages support Jekyll, a simple, blog aware static site generator. Jekyll makes it easy to create site-wide headers and footers without having to copy them across every page. It also offers intelligent blog support and other advanced templating features.</p>

 <h3>
<a id="authors-and-contributors" class="anchor" href="#authors-and-contributors" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Authors and Contributors</h3>

 <p>You can @mention a GitHub username to generate a link to their profile. The resulting <code>&lt;a&gt;</code> element will link to the contributor’s GitHub Profile. For example: In 2007, Chris Wanstrath (<a href="https://github.com/defunkt" class="user-mention">@defunkt</a>), PJ Hyett (<a href="https://github.com/pjhyett" class="user-mention">@pjhyett</a>), and Tom Preston-Werner (<a href="https://github.com/mojombo" class="user-mention">@mojombo</a>) founded GitHub.</p>

 <h3>
 <a id="support-or-contact" class="anchor" href="#support-or-contact" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Support or Contact</h3>

 <p>Having trouble with Pages? Check out our <a href="https://help.github.com/pages">documentation</a> or <a href="https://github.com/contact">contact support</a> and we’ll help you sort it out.</p>

      <footer class="site-footer">

        <span class="site-footer-credits">This page was generated by <a href="https://pages.github.com">GitHub Pages</a> using the <a href="https://github.com/jasonlong/cayman-theme">Cayman theme</a> by <a href="https://twitter.com/jasonlong">Jason Long</a>.</span>
      </footer>

    </section>

  
   </body>
 </html>

```
Tendriamos que añadir la etiqueta ``{content}`` donde ira el contenido de la pagina index.md con formato Markdown.

Podriamos tambien añadir mas etiquetas en mi caso ``{page.tittle}`` lo añadimos tambien.

**Las etiquetas serian con doble llave {{ abrir y doble llave cerrar }} pero para que Markdown no haga cosas estrañas lo tengo que poner con una sola llave.**

Veamos como quedaria nuestro index.html.

```

<!DOCTYPE html>
<html lang="en-us">
  <head>
    <meta charset="UTF-8">
    <title> {page.tittle} </title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" type="text/css" href="stylesheets/normalize.css" media="screen">
    <link href='https://fonts.googleapis.com/css?family=Open+Sans:400,700' rel='stylesheet' type='text/css'>
    <link rel="stylesheet" type="text/css" href="stylesheets/stylesheet.css" media="screen">
    <link rel="stylesheet" type="text/css" href="stylesheets/github-light.css" media="screen">
  </head>
  <body>
    <section class="page-header">
      <h1 class="project-name"> {page.title} </h1>
      <h2 class="project-tagline"></h2>
    </section>

    <section class="main-content">

     {content}

    </section>

  
  </body>
</html>

```
#### Creación de ficheros .md

En el directorio raiz creamos el fichero index.md sera la página de inicio de nuestra página.

Veamos el contenido de mi fichero index.md.

```

---
layout: index

title: Alejandro Valencia Valles	
tagline: Valencia1904.github.io
---
# Bienvenidos

![Imagen de Bugbunny](images/bugs-bunny-en-sus-primeros-ac3b1os.jpg)

[Curriculum](about)

[Creando una pagina en GitHubPage](githubpage)

```

