---
title: "Desactualizar (downgrade) R en Ubuntu"
date: 2021-06-05T12:14:34+06:00
description: "Instalar una version anterior de R"
author: "calcita"
type: "post"
---

Se me actualizó R a la versión 4.1 con otras actualizaciones de Ubuntu y no me percaté hasta que intenté usar ggplot2 y se rompió. En varios grupos de R a otras personas le estaba lo mismo ya que la versión estable de Rstudio aún no es compatible 100% con la versión 4.1 de R.

---
# Downgrade R

Para volver a la versión anterior de R, adapté la sugerencia de este [post](https://stackoverflow.com/questions/32984676/how-to-downgrade-r-version-3-2-2-to-version-3-1-1-on-ubuntu). Para pasar de R 4.1 a R 4.0.5, los pasos que seguí fueron los siguientes:

1- Desinstalo la versión que tenía instalada de R.

    sudo apt-get remove r-base-core
    sudo apt-get autoremove 

2- Busco el nombre de la versión a instalar.

    apt-cache showpkg r-base

Allí me salen todas las versiones de R 4.* disponibles. 

<!-- ![](img/versiones_disponibles.png) -->

3- Instalo la versión inmediatamente anterior a 4.1, la 4.0.5 de marzo de 2021. 

    sudo apt-get install r-base-core=4.0.5-1.2004.0


Así quedó instalado R, podés comprobarlo escribiendo R en la terminal de Ubuntu o abriendo RStudio. 

En windows esto es más sencillo porque Rstudio te permite en la pestaña 'Tools' elegir cuál versión usar, pero esto no aparece en Linux.

Si querés actualizar R pero aún no tenés instalada ninguna versión 4.*, leé la siguiente sección de este post.

# Actualizar R de 3.* a 4.0.* o instalar desde cero la 4.0.*

Si querés actualizar R pero no a la última versión (en este caso es la 4.1.*) por los problemas que da ggplot en RStudio, podés seguir los siguientes pasos. Si ya tenés instalada una versión de R comenzá desde el paso 0, si no tenés ninguna, comenzá desde el paso 1.

0- Supongamos que tenés la version 3.6.3 y querés actualizar a 4.0.5. Para no tener problemas con versiones de paquetes primero te aconsejo desinstalar R. La primera línea desinstala R y la segunda elimina paquetes ya no necesarios.

    sudo apt-get remove r-base-core
    sudo apt-get autoremove 
    
Para instalar una versión 4.* necesitamos actualizar el repositorio desde donde instalar R. Seguimos las instrucciones del [CRAN](https://cran.r-project.org/bin/linux/ubuntu/) pero solo los primeros 3 pasos.

1 - actualizo indices

    sudo apt update -qq
    
2- instalo dos paquetes necesarios

    sudo apt install --no-install-recommends software-properties-common dirmngr

3- importo la clave del repo (by Michael Rutter)

    sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9

4- Agrego el repo de CRAN para R 4.0 según la versión de Ubuntu que estoy usando ('focal', 'groovy', o 'bionic'). En mi caso tengo Ubuntu 20.4 así que debo elegir 'focal'.

    sudo add-apt-repository "deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/"
    
5 - En este punto si no definimos qué versión queremos instalar, se instalará la úlitma. Por lo tanto, debemos buscar el nombre de la versión a instalar:

    apt-cache showpkg r-base

6 - Instalo la versión inmediatamente anterior a 4.1, en este caso es la 4.0.5

    sudo apt-get install r-base-core=4.0.5-1.2004.0
    
Ojo que en las actualizaciones de software de Ubuntu te va a ofrecer actualizar R, decile que no hasta tanto no se actualice RStudio para solucionar los problemas mencionados.




<!-- Adicionalmente podemos instalar paquetes de la terminal -->

<!--     sudo add-apt-repository ppa:c2d4u.team/c2d4u4.0+ -->
<!--     sudo apt update -->
<!--     sudo apt install r-cran-rgl r-cran-rjags r-cran-snow r-cran-ggplot2 r-cran-igraph r-cran-lme4 r-cran-rjava r-cran-devtools r-cran-roxygen2 r-cran-rjava     -->


<!-- Ver  -->
<!-- https://rtask.thinkr.fr/installation-of-r-4-0-on-ubuntu-20-04-lts-and-tips-for-spatial-packages/ -->