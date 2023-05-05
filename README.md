# Esta es la documentación del Proyecto

Presentado por: MIGUEL ANGEL MORA ORTIZ
Formación: DESARROLLO DE VIDEOJUEGOS Y ENTORNOS INTERACTIVOS
SENA
Ibagué, Tolima
Colombia

A continuación encontraremos los apuntes personales que tomé del curso 'Curso de Programación de Videojuegos 2D con Unity'




Clase - 1

Introducción al curso, donde haremos uso de las herramientas de 2D en la plataforma de Unity. Haremos algunas mecánicas, tales cómo de disparo, enemigos, power ups.

Cuando abrimos el código C#, vemos que esté genera automaticamente línes de código. Dentro de estas son; Start y Update.

Para que algo suceda en nuestra Escena, debemos usar el metodo (print) en minusculas.



Clase - 2

Instalación de Unity, la debemos hacer desde el programa de Unity Hub.

Luego de instalar Unity Hub, debemos ir a la seccion de 'Install', para instalar el Editor de Unity, donde agregamos el Android Build Support y el Visual Studio Code, eliminamos la documentación y aceptamos los términos hasta terminar el proceso.




Clase - 3

Empezaremos un nuevo proyecto y configuraremos la interfaz y el editor para un optimo trabajo. 

Encontraremos en la interfaz las siguientes ventanas:
    Scene       = Acá estará el detrás de cámara de nuestro juego
    Game        = Lo que veremos cuando estemos jugando
    Jerarquía   = Se encuentran los elementos que están dentro del Juego
    Inspector   = Veremo los detalles y propiedades de cada elemento
    Project     = Estarán todos los assets/archivos dentro de nuestro proyecto


Configuramos la interfaz de Unity, de una manera más optima, para un uso más eficaz y fácil de usar





Clase  - 4

En esta clase descargamos e importamos los recursos que nos da el curso. Es muy fácil, solo descargarlos y abrirlos dentro de nuestro área de trabajo.




Clase - 5 (son solo los archivos de assets, que usaremos)





Clase - 6

En esta clase hacemos instalación de unos paquetes 2D, para el uso de esta misma herramienta. Sin embargo, las ultimas versiones del programa Unity ya trae este paquete por defecto.

Aun así si necesitamos descargar estos extras, nos dirigimos al navegador Web y buscamos "unity 2d extras"
Entramos al link oficial de Unity en Github y descargamos el zip
Debemos tener en cuenta que la versión que descarguemos sea compatible con la versión que tenemos de github

Descomprimimos los archivos y los arrastramos a Projects, sobre los Assets.



Clase - 7

Uso de tilemaps y palettes  

Tilemaps, es el uso que le damos a los Tiles, para crear un mapa en 2D. Los Tiles son sprites que podemos usar como paletas.

Las paletas las hacemos con los Tiles, seleccionando una desde la herramienta de Tile Palette y ubicandola en el Scene, haciendo así como una pintura con cada sprite que seleccionamos

Debemos crear en Jerarquía el GameObject Tilemap. Para que nos genere la rejilla en la escena, para trabajar adecuadamente.


Realizamos el reto, haciendo un mapa con los sprites ya puestos en escena.


Clase - 8


Solución del reto y vista del escenario



Clase - 9

Agregando nuestro primer Script

Agregaremos interacciones, generado desde código

Generamos un GameObject, que represente al Jugador.
Creamos una carpeta dentro de Assets, llamada Scripts y dentro de esta el archivo C#
Este archivo C#, lo anclamos al GameObject agregandola a la ventana del Inspector del corresponiendte GameObject

Si hacemos uso del Start, lo que hagamos se hará antes de los frames del juego. Suceden antes de. Se activan una sola vez.

Si usamos el Update, este se hará en bucle por cada frame que dure nuestro juego iniciado



Clase - 10

Movimiento del Jugador

float h; será nuestra variable para introducir el movimiento horizontal a nuestro personaje

    Input.GetAxis("Horizontal"); Esta línea extrae la información de nuestro teclado de manera horizontal, derecha o izquierda.

DeltaTime = El tiempo que hay entre un frame y otro

[SerializeField] con esto agregamos al Inspector, algo que queramos añadir desde el cógido, para configurarlo desde el mismo inspector y no volver al código


Clase - 11

Movimiento de Cámara 

Para esto debemos descargar otro Extra a nuestro Editor de Unity.

Cine Machine = Es un paquete especializado en el manejo de cámaras. PAra poder controlar el Main Camera

Luego creamos un Virtual Camera, que se agregará a la Jerarquía como un Game Object y este está ligado al Main Camera 

Luego de esto en el camera machine, en la sección de Follow, agregamos el GameObject que queramos que sea el objetivo que la cámara seguirá. Por consiguiente aquí agregamos el Object "Player"



Clase - 12

Disparando un proyectil 2D

Hicimos uso de nuevos metodos usados en pocas líneas de código para recrear una mira que se mueva segun el puntero del mouse. Usamos los siguientes metodos:
(aim.position) (ScreenToWorldPoint) (mousePosition) (facingDirection) 

También formalizamos un Vector2 Como si fuera un Vector3, tan solo cambiando la función y añadiendole a la variable (Vector3) para que esta sea leída como tal.

Además hicimos que la mira al rededor del personaje se mueva al rededor de un propio eje, quedando este eje fijo.





Clase - 13

Creación de un Proyectil

Acá creamos un GameObject, llamado Bullet. A este le hacemos un Código aparte. por lo que necesitamos crear otra línea de C#

A este GameObject igualmente le agregamos las caracteristicas realizadas en código para poderlo configurar como queramos desde el editor, sin tener que volver al código

Para configurar las balas que deseemos que sean disparadas, debemos crearlas como Prefabs 

Le agregamos en le código de Player la variable de la bala. Para luego poder agregarle el Prefab de la bala desde Project a la ventana de Inspector. No debemos hacerlo desde la ventana de Jerarquía, porque nos dará un error.

Acá usamos un nuevo método (Instantiate) sirve para generar un objeto (prefab) dependiendo los click que hagamos, esto acompañado de un (GetMouseButton)


Con esto ya nuestro jugador, genera balas cada vez que pulsamos o hacemos click y además respetando la rotación del mouse. Debemos corregir la cantidad de balas que dispara por cada click




Clase - 14

Manejando la cadencia de disparo

Mejoramos la cadencia de disparo, implementando ciertas variables. Usando nuevos metodos, tales como;
(gunLoaded) (fireRate) (IEnumerator) (yield) (return) (WaitForSeconds) 

Usando estos nuevos metodos, podemos configurar la cadencia de balas que nuestro jugador dispara por cada click.

Además la incluimos en el Inspector del Editor, para poder cambiarlo desde ahí




