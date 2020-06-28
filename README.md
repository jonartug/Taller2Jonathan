Taller#2 
Estudiante Jonnattan Gutiérrez Aguero
Arquitectura
Se trata de realizar un ejercicio utilizando el diseño de patrones MVC, por lo que se aplicaron los componentes necesarios solicitados
Modelo
Se declaran las clases principales en las que denomine:
Banda: con los datos del genero y nombre de músicos.
Musico: En esta se declaran los datos de los instrumentos y los nombres de los mismos.
Festival: Se declaran los nombres y las fechas de los festivales.
Vista
En la vista se declaran todos los métodos de bienvenida, impresiones de las listas y mensajes, además los mensajes de finalización.
Controlador
En este modulo se encuentran las librerías que son las que van a vincular el controlador con la vista y el modelo. Dentro de este modulo se declaran las listas, se declaran los métodos de agregar valores a las mistas.
Se declaran los métodos para llamar a los mensajes declarados en la vista y solicitud de impresiones de mensajes emergentes mostrados en consola.
Para este módulo se utiliza un ciclo while en el que se empieza con el análisis y validaciones de los datos por medio de un menú el cual permite que el usuario manipule el programa de manera sencilla y guiada.
Las validaciones se efectúan por medio de un try, except y para la obtención de datos varios un Split.
Dentro de este módulo  se utilizan las funciones para ingresar los datos a las listas y actualizar la información  y luego imprime la información validada.
Se muestran los datos para continuación o finalización del menú
Funcionalidad
El usuario podrá elegir entre las opciones del menú 
Mostrar lista, salir o agregar datos, cumple con el objetivo del programa el cual solicita la información y la almacena,  y muestra la informacion solicitada.
Permite que el usuario agrege mas datos o salga del sistema.
Alcance
El programa cumple con lo solicitado solo que al no tener bases de datos no muestra la información ingresada si lo corre de nuevo.
Entre las limitaciones esta la realización de las dependencias entre clases ya que no logre como integrarlas unas a otras y que las imprimiera completas

Dependencias 
Los componentes del controlador si manipulan la vista y el modelo como lo es requerido en el proyecto, pero aun me falta entender un poco más la implementación de las clases que se manipulen entre sí.
