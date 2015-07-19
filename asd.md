<span id="h.lfxccegk9mek" class="anchor"></span>Documentos de
Arquitectura Software (DAS)

Arquitectura Cliente Servidor 1.0

Table of Contents

**<span style="font-variant:small-caps;">1.</span>** **<span
style="font-variant:small-caps;">INTRODUCTION </span>**

> <span style="font-variant:small-caps;">1.1</span> <span
> style="font-variant:small-caps;">Purpose </span>
>
> <span style="font-variant:small-caps;">1.2</span> <span
> style="font-variant:small-caps;">Scope </span>
>
> <span style="font-variant:small-caps;">1.3</span> <span
> style="font-variant:small-caps;">Definitions, Acronyms and
> Abbreviations </span>
>
> <span style="font-variant:small-caps;">1.4</span> <span
> style="font-variant:small-caps;">References </span>
>
> <span style="font-variant:small-caps;">1.5</span> <span
> style="font-variant:small-caps;">Overview </span>

**<span style="font-variant:small-caps;">2.</span>** **<span
style="font-variant:small-caps;">ARCHITECTURAL REPRESENTATION </span>**

<span id="h.gjdgxs" class="anchor"></span>**<span
style="font-variant:small-caps;">3.</span>** **<span
style="font-variant:small-caps;">ARCHITECTURAL GOALS AND CONSTRAINTS
</span>**

> <span style="font-variant:small-caps;">3.1</span> <span
> style="font-variant:small-caps;">Technical Platform </span>
>
> [<span style="font-variant:small-caps;">3.2</span>](#h.lnxbz9)[
> ](#h.lnxbz9)[<span
> style="font-variant:small-caps;">Transaction</span>](#h.lnxbz9)[
> ](#h.lnxbz9)[](#h.lnxbz9)
>
> <span style="font-variant:small-caps;">3.3</span> <span
> style="font-variant:small-caps;">Security </span>
>
> <span style="font-variant:small-caps;">3.4</span> <span
> style="font-variant:small-caps;">Persistence </span>
>
> <span style="font-variant:small-caps;">3.5</span> <span
> style="font-variant:small-caps;">Reliability/Availability (failover)
> </span>
>
> <span style="font-variant:small-caps;">3.6</span> <span
> style="font-variant:small-caps;">Performance </span>
>
> <span style="font-variant:small-caps;">3.7</span> <span
> style="font-variant:small-caps;">Internationalization (i18n) </span>

**<span style="font-variant:small-caps;">4.</span>** **<span
style="font-variant:small-caps;">USE-CASE VIEW </span>**

> [<span style="font-variant:small-caps;">4.1</span>](#h.1y810tw)[
> ](#h.1y810tw)[<span style="font-variant:small-caps;">Ordering
> Menus</span>](#h.1y810tw)[ ](#h.1y810tw)[](#h.1y810tw)
>
> <span style="font-variant:small-caps;">4.2</span> <span
> style="font-variant:small-caps;">Use-Case Realizations </span>

**<span style="font-variant:small-caps;">5.</span>** **<span
style="font-variant:small-caps;">LOGICAL VIEW </span>**

> <span style="font-variant:small-caps;">5.1</span> <span
> style="font-variant:small-caps;">Overview </span>
>
> <span style="font-variant:small-caps;">5.2</span> <span
> style="font-variant:small-caps;">Architecturally Significant Design
> Packages </span>

**<span style="font-variant:small-caps;">6.</span>** **<span
style="font-variant:small-caps;">PROCESS VIEW </span>**

**<span style="font-variant:small-caps;">7.</span>** **<span
style="font-variant:small-caps;">DEPLOYMENT VIEW </span>**

**<span style="font-variant:small-caps;">8.</span>** **<span
style="font-variant:small-caps;">IMPLEMENTATION VIEW </span>**

> <span style="font-variant:small-caps;">8.1</span> <span
> style="font-variant:small-caps;">Overview </span>
>
> <span style="font-variant:small-caps;">8.2</span> <span
> style="font-variant:small-caps;">Layers </span>

**<span style="font-variant:small-caps;">9.</span>** **<span
style="font-variant:small-caps;">DATA VIEW </span>**

[**<span style="font-variant:small-caps;">10.</span>**](#h.3o7alnk)[
](#h.3o7alnk)[**<span style="font-variant:small-caps;">SIZE AND
PERFORMANCE</span>**](#h.3o7alnk)[ ](#h.3o7alnk)[](#h.3o7alnk)

**<span style="font-variant:small-caps;">11.</span>** **<span
style="font-variant:small-caps;">QUALITY </span>**

1.  **Introducción\
    **Este documento contiene información de la arquitectura de un
    programa con la arquitectura “Cliente Servidor”.

2.  Como se indica en el artículo complementario , un arquitecto de
    software normalmente realiza actividades importantes con el fin de
    definir una arquitectura global , y cada vez que una actividad se
    completa , una sección específica de la DAS se enriquece en
    consecuencia.

  ------------------------------------------------------------- -------------------------------------------
  **Actividades Arquitectonicas**                               **Documento de Arquitectura de Software**
  Paso 1 -Identificar y priorizar casos de uso significativos   Sección 4
  Paso 2 -Definir la arquitectura candidata                     Sección 3, 5.1, 10, 11
  Paso 3 - Definir el modelo de despliegue inicial              Sección 7
  Paso 4 - Identificar las abstracciones clave                  Sección 9
  Paso 5 - Crear un modelo de análisis                          Sección 5
  Paso 6 - Crear el Modelo de Diseño                            Sección 5
  Paso 7 - Documentar mecanismos de concurrencia                Sección 6, 7
  Paso 8 - Crear el modelo de Implementación                    Sección 8
  ------------------------------------------------------------- -------------------------------------------

<span id="h.1fob9te" class="anchor"></span>

Propósito
---------

El Documento de Arquitectura de Software ( DAS ) proporciona una visión
arquitectónica integral del programa “Cliente Servidor”. Presenta una
serie de puntos de vista de la arquitectura para representar diferentes
aspectos del sistema. Se tiene la intención de captar y transmitir las
decisiones arquitectónicas significativas que se hayan introducido en el
sistema.\
\
Con el fin de representar el software con la mayor precisión posible, la
estructura de este documento se basa en el modelo de vistas
arquitectónicas"4 + 1 ".

> ![](./media/image1.png)

El Modelo " 4 + 1 " permite a las diversas partes interesadas encontrar
lo que necesitan en la arquitectura de software .

> <span id="h.2et92p0" class="anchor"></span>

Alcance.
--------

<span id="h.ikcoyflh32zk" class="anchor"></span>\
Lo que se pretende realizar con esta aplicación se detalla en los
siguientes puntos

<span id="h.5y478xsb36ea" class="anchor"></span>

-   <span id="h.koyl2txl397j" class="anchor"></span>Se pretende crear un
    sitio web para la publicación e información de un congreso a los
    usuarios, la información contenida en el sitio será actualizable.

-   <span id="h.cv253yaayb3b" class="anchor"></span>Permitir a los
    usuarios llenar y guardar la información de un formulario que
    contiene sus datos personales, además de un aporte personal del
    usuario acerca del resumen del congreso.

-   <span id="h.ju509cd1itkj" class="anchor"></span>Permitir tener un
    administrador que ingrese con un usuario y contraseña.

-   <span id="h.cgypfpj69mvk" class="anchor"></span>Permitir que el
    administrador pueda generar reportes de los aportes hechos por los
    usuarios

-   <span id="h.tyjcwt" class="anchor"></span>permitir que el
    administrador pueda actualizar la información tanto del sitio como
    sus propios datos.

<span id="h.3dy6vkm" class="anchor"></span>

Definiciones, Siglas y abreviaturas
-----------------------------------

**UML:** Unified Modeling Language

**DAS:** Docuementación de la Arquitecura del software.

<span id="h.1t3h5sf" class="anchor"></span>

Referencias
-----------

> [KRU41]: La vista del modelo arquitectónico de software " 4 + 1 ",
> Philippe Kruchten , noviembre de 1995,

*http://www3.software.ibm.com/ibmdl/pub/software/rational/web/whitepapers/2003/Pbk4p1.pdf*[](http://www3.software.ibm.com/ibmdl/pub/software/rational/web/whitepapers/2003/Pbk4p1.pdf)<span
id="h.2s8eyo1" class="anchor"></span>

Revisión
--------

> Con el fin de documentar plenamente todos los aspectos de la
> arquitectura , el Documento de Arquitectura de Software contiene las
> siguientes subsecciones.\
> Sección 2 : describe el uso de cada vista.\
> Sección 3 : describe las limitaciones arquitectónicas del sistema.\
> Sección 4 : describe los requisitos funcionales con un impacto
> significativo en la arquitectura.\
> Sección 5 : describe lo más importante en la realización de casos de
> uso . Contendrá el Modelo de Análisis y el Modelo de Diseño.\
> Sección 6 : describe aspectos de concurrencia de diseño.\
> Sección 7 : describe cómo se implementará el sistema. Contendrá el
> Modelo de Despliegue.\
> Sección 8 : describe las capas y subsistemas de la aplicación.\
> Sección 9 : describe cualquier elemento significativamente
> persistente. Contendrá el modelo de datos.\
> Sección 10 : describe los problemas de rendimiento y limitaciones.\
> Sección 11 : describe los aspectos relacionados con la calidad de
> servicio atributos ( QoS).

<span id="h.17dp8vu" class="anchor"></span>

Representación arquitectónica 
==============================

> En este documento se detalla la arquitectura utilizando las vistas
> definidas en el modelo de " 4 + 1 " [ KRU41 ] , pero utilizando la
> convención de nomenclatura RUP . Las vistas que se utilizan para
> documentar la aplicación “Cliente Servidor”. son:
>
> **Vista Lógica.**
>
> **Descripción:** En esta vista representa lo que el sistema debe
> hacer, y las funciones y servicios que ofrece, a los usuarios finales.
>
> ***Audiencia:*** Diseñadores.
>
> ***Área:*** Requisitos funcionales: describe modelo de objetos de
> diseño. También se describen las realizaciones más importantes de
> casos de uso.
>
> ***Artefactos relacionados**:* Modelo de Diseño.
>
> **Vista de Procesos**
>
> **Descripción:** En esta vista se muestran los procesos que hay en el
> sistema y la forma en la que se comunican estos procesos;
>
> ***Audiencia***: Integradores.
>
> ***Área***: Requisitos no funcionales: describe concurrencia y
> sincronización aspectos del diseño.
>
> ***Artefactos relacionados***: (No hay artefacto en detalle).
>
> **Vista de implementación**
>
> **Descripción:** Se indica todos los componentes físicos del sistema
> así como las conexiones Hadware.
>
> ***Audiencia***: Programadores.
>
> ***Área***: Componentes de Software: describe las capas y subsistemas
> de la aplicación.
>
> ***Artefactos relacionados***: Modelo de componentes.
>
> **Vista de Despliegue**
>
> **Descripción:** En **e**sta vista se indica el sistema desde la
> perspectiva de un programador y se ocupa de la gestión del software.
>
> ***Audiencia***: Gestores de despliegue.
>
> ***Área***: Topology: describes the mapping of the software onto the
> hardware and shows the system's distributed aspects.
>
> ***Artefactos relacionados***: Modelo de componentes.
>
> **Vista Escenarios**
>
> ***Audiencia***: Todos los interesados del sistema, Incluidos los
> usuarios finales.
>
> ***Área***: Describe el conjunto de escenarios y / o casos de uso que
> representan algunas funciones importantes, en el sistema.
>
> ***Artefactos relacionados***: Modelo de casos de uso.

<span id="h.3rdcrjn" class="anchor"></span>

Objetivos de arquitectura y limitaciones.
=========================================

> En esta sección se describen los requisitos de software y los
> objetivos que tienen algún impacto significativo en la arquitectura.
>
> <span id="h.26in1rg" class="anchor"></span>

Plataforma Técnica.
-------------------

> El programa “Cliente Servidor” se desplegará en un servidor Apache,
> con un base de datos MySql, lenguaje de programacion por lado del
> servidor PHP, Lenguaje javascript, una libreria para generacion de
> reportes PhpExcel.

<span id="h.lnxbz9" class="anchor"></span>

Transacción
-----------

> El programa “Cliente Servidor” es transaccional, el aprovechamiento de
> las capacidades de la plataforma técnica. Apache.

<span id="h.35nkun2" class="anchor"></span>

Seguridad
---------

> La aplicación debe implementar conductas básicas de seguridad:
>
> Integridad de los datos : Los datos enviados a través de la red no
> puede ser modificado por un nivel

<span id="h.44sinio" class="anchor"></span>

Fiabilidad / disponibilidad ( failover )
----------------------------------------

> <span id="h.2jxsxqh" class="anchor"></span>La aplicación estará
> disponible las 24 horas del día, siempre y cuando exista un congreso
> en curso, de otra manera no estará disponible.

Rendimiento
-----------

El proceso de Envió de formularios debe tener menos de 5 segundos.

El proceso de generación de reportes deber tener menos de 1 minuto.

<span id="h.3j2qqm3" class="anchor"></span>

Vista De Escenarios
===================

**Lista de casos de Uso**

-   Gestionar Información: El “Administrador” podrá administra la
    información del sitio.

-   Presenta Información: Al “Usuario” se le presentara información del
    sitio.

-   Gestionar Participación: EL “Administrador” gestionara las
    participaciones que tendrá cada uno de los usuarios.

-   Registra Participación: El “Usuario” podrá realizar distintas
    participaciones.

-   Gestionar Usuarios: El “Administrador” tendrá la opción de gestionar
    a los usuarios.

-   Ingresar al Sistema: El “Usuario” ingresara al sistema con su
    usuario y contraseña para poder visualizar la información del mismo.

-   Actualizar Datos: El “Usuario” podrá actualizar sus datos
    personales.

-   Generar Reportes: El “Administrador” generar los reportes de las
    participaciones de los usuario.

![](./media/image2.png)

<span id="h.4i7ojhp" class="anchor"></span>

4.1. Actores
------------

-   <span id="h.5570hcm7mg9m" class="anchor"></span>Administrador: Se
    encarga de generar reportes, así como gestionar información en la
    base de datos

-   Usuario: Este podrá gestionar a los clientes y envían el formulario.

<span id="h.2xcytpi" class="anchor"></span>

<span id="h.dbnqth85nk37" class="anchor"></span>**5. Vista Lógica**

> En esta vista se representa la funcionalidad que el sistema
> proporcionara a los usuarios finales. Es decir, se ha de representar
> lo que el sistema debe hacer, y las funciones y servicios que ofrece

-   **Diagrama de Clases:**

> ![](./media/image3.png)
>
> <span id="h.8819cjmuj1hc" class="anchor"></span>

6.  **Vista de Procesos**

En esta vista se muestran los procesos que hay en el sistema y la forma
en la que se comunican estos procesos, es decir, se representa desde la
perspectiva de un integrador de sistemas, el flujo de trabajo paso a
paso de negocio y operacionales de los componentes que conforman el
sistema.

-   **Diagrama de Actividades **

> ![](./media/image4.png)

<span id="h.qsh70q" class="anchor"></span>

7. Vista de Despliegue 
=======================

En esta vista se muestra el sistema desde la perspectiva de un
programador y se ocupa de la gestión del software; o en otras palabras,
se va a mostrar cómo está dividido el sistema software en componentes y
las dependencias que hay entre esos componentes.![](./media/image5.png)

-   Una maquina cliente podrá enviar un mensaje al servidor.

-   El servidor receptará y procesara el mensaje.

<span id="h.3as4poj" class="anchor"></span>

Vista de Implementación
=======================

> En esta vista se muestra desde la perspectiva de *un ingeniero de
> sistemas* todos los componentes físicos del sistema así como las
> conexiones físicas entre esos componentes que conforman la solución
> (incluyendo los servicios).

-   **Diagrama de Despliegue:**

> ![](./media/image6.png)
>
> <span id="h.1pxezwc" class="anchor"></span>La vista de implementación
> representa la composición física de la aplicación en términos de
> subsistemas de aplicación, y Elementos de Implementación (directorios
> y archivos , incluyendo el código fuente , los datos y los archivos
> ejecutables ) .<span id="h.90s9vyjodamf" class="anchor"><span
> id="h.7qqvt0y0vtvm" class="anchor"><span id="h.3o7alnk"
> class="anchor"></span></span></span>

Tamaño y rendimiento
====================

Rendimiento:

-   Tiempo de recepción del mensaje por parte del servidor: menos de 10
    segundos.

<span id="h.23ckvvd" class="anchor"></span>

Calidad. 
=========

Los siguientes objetivos de calidad han sido identificados:

**Escalabilidad**:

-   Descripción: la reacción del sistema cuando el usuario exige aumento
    de requerimientos.

**Portabilidad**:

-   Descripción: Capacidad para ser reutilizado en otro entorno

-   Solución: El sistema que sea totalmente compatible con Los
    estándares definidos.
