# Práctica 12. Programación Gráfica Orientada a Objetos y guiada por eventos. El juego del Ahorcado.
### Factor de ponderación: 10 

### Examen de la asignatura
Tenga en cuenta que esta es la primera de las dos prácticas que componen el examen final de la asignatura.

### Objetivos
Los objetivos de esta tarea son poner en práctica:
* Integración continua para un proyecto de prácticas de la asignatura
* La arquitectura Modelo Vista Controlador
* Conceptos de Programación orientada a eventos en TypeScript.
* Conceptos de Programación Gráfica en TypeScript usando la API Canvas.
* Metodologías y conceptos de Programación Orientada a Objetos en TypeScript.
* Principios y Buenas prácticas de programación Orientada a Objetos.
* El uso del framework Bulma para dotar de estilo a una aplicación web simple.
* El uso de elementos HTML.

### Rúbrica de evaluacion de la práctica
** Revise cuidadosamente esta rúbrica puesto que será la que se utilice para la evaluación del examen de la asignatura**

Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* Se valorará la realización de las diferentes tareas que se proponen
* El comportamiento del programa debe ajustarse a lo descrito en este documento
* Capacidad de la programadora de introducir cambios en el programa desarrollado
* Se acredita conocimiento y puesta en práctica de principios y buenas prácticas de programación orientada a objetos
* Saber corregir bugs en sus programas utilizando el depurador de Visual Studio Code
* Deben usarse estructuras de datos adecuadas para representar los diferentes elementos que intervienen en el problema
* Ser capaz de desarrollar programas simples en TypeScript en el entorno Linux de la VM de la asignatura usando
  `ts-node`
* Conocer y ser capaz de trabajar con el Framework CSS
[Bulma](https://bulma.io/)
* Ser capaz de generar documentación para sus programas TS utilizando
  [TypeDoc](https://typedoc.org/)
  y de visualizar dicha documentación en un servidor web
* Acreditar que conoce las etiquetas de 
  [JSDoc](https://jsdoc.app/)
* El alumnado debe ser capaz de resolver problemas tanto en JS como en TS en la plataforma Exercism subiendo sus soluciones a la misma
* Ser capaz de desarrollar tests unitarios para sus programas utilizando
  [Jest](https://jestjs.io/)
* Acreditar su capacidad para configurar y utilizar 
  [ESLint](https://eslint.org/)
y que es capaz de trabajar con la misma en Visual Studio Code
* El alumnado ha de acreditar que es capaz de desarrollar programas de la plataforma Jutge
* Se comprobará que el código que el alumnado escribe se adhiere a las reglas de las Guías de Estilo de Google para 
[TypeScript](https://google.github.io/styleguide/tsguide.html)
y/o
[JavaScript](https://google.github.io/styleguide/jsguide.html)
* Todas las prácticas realizadas hasta la fecha, incluída la que se presenta para su evaluación, se encuentran alojadas en repositorios privados de GitHub.
* Acreditar que es capaz de editar ficheros de forma remota en su VM usando Visual Studio Code

### Indicaciones de caracter general
* La aplicación que desarrolle ha de ser orientada a objetos y conforme a la arquitectura MVC.
Ponga en práctica en su desarrollo los fundamentos, principios y buenas prácticas de la OOP así como los
conocimientos que haya adquirido en el uso de patrones de diseño.

* Aloje ficheros de configuración adecuados en el directorio raíz de su proyecto, de modo que se contemplen todas las dependencias del mismo.

* Utilice un fichero distinto para el código de cada una de las clases que intervienen en su programa.

* Encapsule las clases en módulos que exporten la correspondiete clase hacia otros programas clientes que pudieran utilizarla.

* Todo el código estará ubicado en el directorio `src/home-work` del proyecto. Use subdirectorios de éste si le resulta conveniente.

* Antes de comenzar a desarrollar su programa dedique el tiempo necesario a diseñar la estructura de clases que 
utilizará en su programa, así como las relaciones existentes entre las mismas. 
Utilice 
[LucidChart](https://www.lucidchart.com/pages/es)
o una aplicación similar para realizar un diagrama UML para esas clases, que ha de añadir a la página índice de esta práctica. Asegúrese de la corrección de su diagrama UML.

* Realice, como siempre, un diseño incremental del programa comprobando cada una de las funcionalidades que añade, siguiendo un
desarrollo TDD.

* Cuando finalice su desarrollo modifique el fichero `README.md` de su proyecto incluyendo la información habitual en cualquier proyecto público en GitHub. 
Incluya en ese fichero dos apartados, Building and Running the code y Live Demo. 
En el primero de ellos ha de explicar en detalle cómo a partir de clonar su repo público ha de compilarse, ejecutarse y desplegarse su aplicación, 
mientras que en el segundo ha de incluir un enlace (véase el apartado *Presentación de resultados de este documento*) a la URL pública donde deberá estar disponible su aplicación.

### Integración Continua
Estudie el trabajo expuesto en clase sobre
[Integración Continua](https://github.com/ULL-ESIT-PAI-2024-2025/2024-2025-pai-ci-2024-2025-pai-ci.git)
para recordar cómo utilizar GitHub Actions para configurar un flujo de trabajo para su proyecto.

Incluya en su proyecto un fichero de configuración del flujo que permita automatizar la ejecución de las
diferentes tareas del proyecto.

Incluya en su flujo de trabajo al menos las siguientes etapas:
* Análisis estático de su código utilizando ESLint. Utilice 
[typescript-eslint](https://typescript-eslint.io/)
para habilitar el análisis de código TypeScript en ESLint y configure el linter para que analice la
conformidad de su código con la Guía de Estilo de Google para TS.
* Generación de la documentación de su proyecto utilizando
[TypeDoc](https://typedoc.org/)
* Despliegue de su aplicación en una 
[GitHub Page](https://pages.github.com/) 
asociada con su repo de trabajo.

Si hay alguna otra tarea que resulte de interés para su desarrollo, inclúyala igualmente en el flujo.

### El juego del Ahorcado
En esta práctica se propone desarrollar una aplicación web SPA 
[(Single Page Application)](https://en.wikipedia.org/wiki/Single-page_application)
diseñada conforme al patrón Modelo Vista Controlador, que implemente el conocido juego del
[Ahorcado](https://es.wikipedia.org/wiki/Ahorcado_\(juego\))

El juego, conocido en inglés como *Hangman*, es un popular juego de adivinanza que se juega 
habitualmente con papel y lápiz, aunque también existen versiones digitales, como la que se propone realizar.

El objetivo del juego es adivinar una palabra secreta que el ordenador ha elegido, 
antes de que se complete un dibujo de un ahorcado.

El ordenador elige una palabra y la escribe en forma de casillas en blanco, donde cada casilla representa 
una letra de la palabra. 
Por ejemplo, si la palabra es "goat", se representaría como "_ _ _ _" donde cada guión corresponde con una casilla
en blanco.

El jugador intenta adivinar la palabra, letra por letra. 
Por cada letra que adivina, el ordenador debe revelar su posición en la palabra si es correcta. 
Si la letra no está en la palabra, se registra como un intento fallido.

Generalmente, se permite un número limitado de intentos fallidos. 
Cada intento fallido se representa con una parte del dibujo del ahorcado (cabeza, tronco, brazos, etc.). 
Si el dibujo se completa antes de que el jugador descubra la palabra, el juego termina y el ordenador gana.
El juego puede terminar de dos maneras:
Victoria del jugador: Si el jugador descubre todas las letras de la palabra antes de completar el dibujo del ahorcado.
Victoria del ordenador: Si el adivinador agota todos sus intentos sin adivinar la palabra.

### Interfaz gráfica del programa
La interfaz gráfica de la aplicación a diseñar imitará la de
[esta página](https://www.englishclub.com/esl-games/hangman/animals-easy.php),
una vez clicado el botón *START*, que se tomará como referencia.
Su aplicación no ha de contemplar el botón de arranque, sino que al inicializarse ha de mostrar ya el juego en
curso.

También el comportamiento lógico de su aplicación debe imitar a la de referencia.

Utilice libremente los elementos HTML que considere más adecuados para la interfaz gráfica de su aplicación y
dote de estilo a esos elementos utilizando Bulma.

Sobre un fondo de color gris se representarán las casillas vacías correspondiente a la palabra a adivinar así
como las casillas correspondientes a cada una de las letras del alfabeto.

Se representará gráficamente el patíbulo, la horca y el ahorcado, para lo cual se propone utilizar los ficheros
[Hangman-X.png](https://en.wikipedia.org/wiki/File:Hangman-6.png)
(cambie X por un valor entre 1 y 6) para obtener los 6 ficheros que corresponden con la secuencia del juego).
Si lo desea, puede Ud. utilizar otras imágenes diferentes de esta propuesta.

### Presentación de resultados
Configure una página GitHub asociada con su repositorio de trabajo que sirva de índice para estas otras
páginas de su proyecto:
* La aplicación *Hangman* que habrá desarrollado. Esa aplicación se configurará como una SPA.
* La documentación de la aplicación.
* El diagrama UML de las clases utilizadas en la aplicación.
* Una página que albergará el ejercicio que se le pedirá realizar en la sesión de evaluación de esta práctica.

Todas estas páginas deberán tener un estilo personalizado que imite el aspecto (tipografía, colores) de las *páginas ULL*.

## Referencias
* [Ahorcado](https://es.wikipedia.org/wiki/Ahorcado_\(juego\))
* [Bulma](https://bulma.io/)
* [TypeDoc](https://typedoc.org/)
* [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)
* [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
* [ESLint](https://eslint.org/)
* [JSDoc](https://jsdoc.app/)
* [PAI Code Examples](https://github.com/ULL-ESIT-PAI-2024-2025/PAI-class-code-examples)
