---
title: Git con R. Control de versiones
author: ''
date: '2018-11-10'
slug: git-con-r-control-de-versiones
categories: []
tags: ["R", "git", "gitlab", ".Rproj"]
authors: []
---

Suele ser muy útil cuando trabajamos en un desarrollo que requiere permanente actualización del código o un trabajo colaborativo, utilizar un programa de control de versiones. En este caso, mostraré como el software [git](https://git-scm.com/) y la plataforma web [gitlab](https://gitlab.com/) permitirán conectarse con un proyecto de R de manera de permitir el control de versiones del proyecto.

![](/images/git.png) ![](/images/gitlab.png) ![](/images/rstudio.png)

### ¿Por qué usar un software de control de versiones?

* Permite compartir tus proyectos, facilitando el trabajo colaborativo
* Regresar a versiones previas, si encontrás errores o borrás accidentalmente algo.  
* _Ver_ los cambios entre diferentes versiones de tu código, análisis o texto.
* Permite reportar errores (bugs) o sugerir nuevos aportes (features) a proyectos.
* Compartir tus paquetes de R e instalar los que se encuentran en desarrollo con solo dos lineas de código: `install.packages("devtools"); devtools::install_github("username/packagename")`
* Saber cuál es la versión final de un archivo!

![](/images/porquegit.png)
[Tomado de swcarpentry](https://swcarpentry.github.io/git-novice/01-basics/)

### Software de control de versiones

* No es un repositorio para tus archivos
* Está pensado para archivos de texto plano
* Existen varios webservice amigables que permiten guardar proyectos en repositorios remotamente: [gitlab](https://about.gitlab.com/),  [gitHub](https://github.com/) o [bitbucket](https://bitbucket.org/).
* Para utilizarlo es necesario: instalar git en tu sistema operativo, crear una cuenta en gitlab y configurar RStudio.
* Recomiendo este el libro online [Happy with R](http://happygitwithr.com/) 

### Esquema de funcionamiento 

![](/images/remote.png)
[Tomado de Git-it](http://jlord.us/git-it/challenges/remote_control.html)
## Instalar git en Ubuntu y configurarlo

En la terminal escribir el siguiente código. Las líneas de configuración es necesario modificar "Your Name" por el nombre que usas o usarás en la cuenta de gitlab o github y "youremail@domain.com" por el mail que utilizás o usarás en tu cuenta de gitlab o github

    sudo apt-get install git
    git config --global user.name "Your Name"
    git config --global user.email "youremail@domain.com"

## Configurar RStudio para conectarlo a git

<iframe src="https://player.vimeo.com/video/292760320" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

## Crear proyecto en gitlab y asociarlo con RStudio

<iframe src="https://player.vimeo.com/video/292637965" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

## Repositorio local  y virtual: commit y push

<iframe src="https://player.vimeo.com/video/292640482" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

En todo este proceso solo usamos software libre y sin gastar dinero.

<iframe src="https://giphy.com/embed/9vdAz0UyHTqZq" width="480" height="283" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/mindblown-9vdAz0UyHTqZq"></a></p>