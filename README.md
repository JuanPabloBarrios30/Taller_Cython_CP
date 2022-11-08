<p align = center  
<br>
<img src="https://res-5.cloudinary.com/crunchbase-production/image/upload/c_lpad,h_256,w_256,f_auto,q_auto:eco/v1455514364/pim02bzqvgz0hibsra41.png" align="center"><br><FONT FACE="times new roman" SIZE=6>
<b>Práctica en Cython</b>
<br>
<i><b>Autor:</b></i> Juan Pablo Barrios Suarez - 8º semestre
<br>
<i><b>Asignatura:</b></i> Computación Paralela y Distribuída
<br>
<i><b>Docente:</b></i> John Corredor
<br>
<i><b>Fecha: </b>1/11/2022
<br>
<b>Ciencias de la computación e inteligencia artificial</b></i>
<br>
</FONT>
</p>

**En este repositorio se encuentran los ficheros correspondientes a la solución del problema planteado acerca de las orbitas de los planetas.**

# **Introducción**

Para esta práctica se considera pertinente hablar sobre el lenguaje de programación _Cython_. Este es un lenguaje de programación diseñado para usar la sintaxis de Python y a su vez que pueda implementar métodos y estrategias de programación utilizadas en _C_ y _C++_, por lo que un código realizado en este lenguaje contaría con beneficios de rendimiento como se observan en _C_ y _C++_. 

En otros términos, un programa escrito en este lenguaje contendría la sintaxis de _Python_, solo que, con ciertas correcciones en las declaraciones de variables y funciones, y sería compilado a código de _C_ o _C++_ 

# **Objetivo**

Analizar los resultados obtenidos de la ejecución de un programa construido en _Cython_ y _Python_, comparando el rendimiento que ofrece cada uno de los lenguajes de programación mencionados previamente, del cual se espera que _Cython_ ofrezca una mejora en los tiempos de ejecucion debido a la combinación de _Python_ con _C/C++_.

##**Ejercicio:** Medida de rendimiento en Python/Cython para el problema de Planeta en Orbita
Esta práctica consta de la construcción de cinco ficheros de extensión _.pyx_, _.py_ y un archivo de automatización _MakeFile_. A partir de estos ficheros se busca realizar una comparativa del rendimiento que puede ofrecer la ejecución de este programa en el lenguaje de programación _Python_, y como se puede obtener una mejora en el rendimiento al ser implementado en el lenguaje de programación _Cython_. Al final, lo que se obtendra en cada ejecución tanto para _Python_ como para _Cython_, es un fichero _.csv_ que contiene los tiempos de ejecución para los dos lenguajes realizados en una misma iteración. Con base en esos resultados, se realizará una comparativa del programa implementado en ambos lenguajes.

Los archivos que se encuentran dentro del repositorio en GitHub ([Click aqui para acceder](https://github.com/JuanPabloBarrios30/Taller_Cython_CP.git)) son los siguientes: 
>### **orbita_py.py**
>En este programa encontrará la solución propuesta dentro del lenguaje de programación python.

>### **orbita_cy.pyx**
>En este programa encontrará la solución propuesta dentro del lenguaje de programación cython. A nivel de comparación podrá observar que será la misma solución escrita en python, con una pequeña diferencia en la sintáxis.

>### **setup.py**
>El setup es un programa que permite realizar la compilación del archivo `.pyx` a código C. Se divide el setup del código principal para trabajar bajo las buenas prácticas que se aplican con la compilación por separado.

>### **principal.py**
>Este programa realiza la ejecución de los dos programas que contienen la solución. Para esto, este programa escrito en Python implementará ambos programas como bibliotecas y de este modo accede a sus métodos. Posteriormente, toma el tiempo de ejecución para ambos programas por separado, y termina contrastando los rendimientos obtenidos por ambos programas.

>### **Makefile**
>Este programa automatiza el proceso de compilación y creación del recurso compartido del archivo `.pyx`.

# **Resultados**

Para presentar los resultados obtenidos en las pruebas de ejecución, es necesario hacer uso de los módulos de _Pandas_ y _Matplotlib_, ya que estos permitiran visualizar los datos de manera más sencilla. Para poder visualizarlos, **se recomienda acceder al fichero _.ipynb_ donde se encuentra todo un análisis exhaustivo de los datos obtenidos. Tambien puede acceder a través de este enlace: ([Click aqui](https://colab.research.google.com/drive/1dqoI5yg25dkzGZWJ4lr14S99A1Stt615?usp=sharing))**

# **Conclusiones**

## De la práctica, se puede concluir lo siguiente:
> 1. El lenguaje de programación _Cython_, a pesar de ser similar a _Python_, puede llegar a ofrecer un mejor rendimiento con respecto a la ejecución de determinado programa debido a que este permite la utilización de módulos y variables del lenguaje de programación _C_.

> 2. Se crea un repositorio que contiene los ficheros necesarios para que cualquier usuario que desee replicar esta práctica pueda hacerlo de manera rápida y sencilla. De igual forma, en el repositorio se encuentran las instrucciones necesarias para conseguir la ejecución del programa

> 3. Del gráfico de barras se pudo observar que hay una mejora considerable en los tiempos de ejecución en el lenguaje de programación _Cython_ con respecto a _Python_. En _Python_ se obtuvo un promedio de $1.93$s, mientras que en _Cython_ se obtuvo un promedio de $0.11$s, lo cual indica que Cython es aproximadamente $17$ veces mejor que Python para la ejecución de este programa

> 4. Del gráfico de lineas en el que se comparó _Python_ con respecto a _Cython_, se puede observar que la escala en la que se encuentran los tiempos de ambos programas, genera que la curva de _Cython_ se vea como una línea recta, mientras que en la de _Python_ si se pueden observar unas pequeñas fluctuaciones en los tiempos. Es por ello que se realiza la gráfica individual para cada lenguaje, lo cual permite apreciar de mejor manera los tiempos de ejecucíon. Para _Python_ se puede observar una fluctuación mayor en los tiempos, oscilando entre $1.88$s y $2.00$, mientras que en _Cython_ se ve un comportamiento extraño, ya que en cierto tramo de la curva se comporta de manera constante, sin embargo sigue fluctuando a medida que avanzan las iteraciones. Esto se debe a que el nodo computacional no se aisló al momento de realizar las pruebas, por lo que los datos pudieron haberse contaminado.

> 5. Con base en lo mencionado anteriormente, se recomienda que si se quiere replicar este experimento, en lo posible se aísle el nodo computacional que vaya a realizar la correspondiente ejecución, con el fin de obtener una mejor calidad en los resultados y asi poder realizar un análisis más completo, que muestre el comportamiento real de los dos lenguajes.

> 6. Por último, se recomienda que, como se está trabajando con _Cython_, y este a su vez tiene acceso a los módulos y variables del lenguaje de programación _C_, a través de la instrucción `nogil` se pueda dar ese acceso al uso de _OpenMP_ para introducir el paralelismo y poder obtener una mejora en los tiempos de ejecución.

# **Ejecucíón** 

- Para poder ejecutar la aplicación, deben ejecutarse los siguientes comandos:

```
python setup.py build_ext --inplace
```
- Finalmente, se ejecuta el módulo principal:
```
python principal.py
```
