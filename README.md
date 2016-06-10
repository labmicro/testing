# README #

Este repositorio muestra un ejemplo simple de como implementar testing en C utilizando Ceedling como herramienta para la generación y compilación del proyecto. El mismo fue desarrollado para la materia de [**Desarrollo Integrado de Sistemas Embebidos**](http://www.microprocesadores.unt.edu.ar/sistemasembebidos/) que se dicta en la [**Especialización en Integración de Tecnologías Informáticas**](http://www.facet.unt.edu.ar/eiti/) en la [Facultad de Ciencias Exactas y Tecnología de la Universidad Nacional de Tucumán](http://www.facet.unt.edu.ar). 

### ¿Como se usa el repositorio? ###

En cada commit del repositorio se avanza un paso en el ejemplo de implementación. 

* En el primer paso se crean las estructuras del proyecto y se vincula el repositorio con un submódulo que contiene una version de ceedling lista para usar, con correcciones en el plugin que genera el informe de cobertura con gcov.
* En el segundo paso se agrega una función y se la prueba como haríamos habitualmente generando un main provisorio y llamándola desde el mismo. Para compilar el programa utilizamos el comando `make all`
* En el tercer paso se genera un programa de test equivalente a la prueba del paso anterior pero utilizando la herramienta ceedling. Para correr el test utilizamos el comando `rake test:all`. Para generar el informe de cobertura utilizamos el comando `rake gcov:all`
y después abrimos con un navegador el archivo `build/gcov/html/index.html`
* En el curato paso se agregan dos pruebas para mejorar la cobertura de los test y se encuentra un error en uno de los casos de la función suma.
* En el quinto caso se corrige el error de la función suma y se agrega un test para la función promedio. Este test muestra como se utiliza una función de mockup y la posibilidad de la misma devuelva datos mediante el uso de punteros. A partir de este test se encuentra un error en la función promedio originado en la falta de la inicialización de acumulador.
* En el ultimo paso se corrige el error de la función promedio y se agrega un test de modulo que prueba las funciones suma y promedio en forma conjunta. El informa de cobertura es ahora del 100% de las lineas de código y del 100% de las funciones.