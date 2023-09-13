# Machine Learning - Implementación de un modelo sin el uso de Framework

Implementación de una técnica de aprendizaje máquina sin el uso de un framework. El objetivo es programar uno de los algoritmos vistos en el módulo (o que tu profesor de módulo autorice) sin usar ninguna biblioteca o framework de aprendizaje máquina, ni de estadística avanzada. Lo que se busca es implementar manualmente el algoritmo, no que importar un algoritmo ya implementado. 

## Introducción

Para este entregable se buscó analizar una base de datos de Vinos `wine.data/` (anexado en esta carpeta) en la cual se registran múltiples caracterísiticas químicas de diferentes vinos. En este caso, se propone la siguiente hipósteis:

  * ¿El componente "_malAcid_" tiene un impacto en e color del vino?

Debido a que esta pregunta nos lleva a intuir que la relación entre ambas variables debe ser significativa, es decir el comportamiento de una tienen que tener un impacto en el comportamiento de la otra, lo que nos lleva a pensar que esta problemática se puede resolver con un modelo de regresión y no de categorización. 

En este bloque se exploraron diferentes modelos de regresión, entre ellos el de Regresión Lineal, el cual consiste según la documentación de _Scikit Learn_ en un modelo lineal con coeficientes w = (w1, …, wp) para minimizar la suma residual de los cuadrados entre los objetivos observados en el conjunto de datos y los objetivos predichos por la aproximación lineal. Se tomará entonces este modelo para verificar la relación entre ambas varibales, si es que encuentra un modelo que se ajuste al comportamiento de los datos entonces se deduce que ambas varibales tienen una relación lineal.

## Desarrollo
El desarrollo se dividió en dos partes, el procesamiento de los datos y la aplicación del modelo.

### Exploramiento y procesamiento de los datos

En esta etapa se exploró la base de datos, se buscó identificar la cantidad de muestras a analizar, cuantas categorías vienen incluidas, si existían valores nulos o atípicos, etc. 

El dataset `wine.data/` (anexado en esta carpeta) consta de una tabla que describe 13 categorías para un total de 178 muestras.


![](https://github.com/FCANOF/PortafolioImplementacion_TE3006_101_FridaCanoFalcon_A01752953/blob/main/final/M2_ML/Ev_01/wine_info.jpg)


En seguida se extrajeron en dos dataframes diferentes los datos de  _Proanthocyanis_ --> _x_data_ y los de _color_ --> _y_data_.

Se graficó el comportamiento de los datos:

 ![](https://github.com/FCANOF/PortafolioImplementacion_TE3006_101_FridaCanoFalcon_A01752953/blob/main/final/M2_ML/Ev_01/colorVsmalAcid.png)

Dando un ojo a la gráfica se ve una dispersión muy variada, por lo que podemos llegar a decir que se ve dificil una relacón entre las variables. Sin embargo se busca comprobarla matemáticamente.

### Aplicaicón del modelo


En cada iteración debemos calcular el valor de la derivada de la función de costo, que se obtiene a partir de los datos estimados, $h_\theta(x_i)$, y reales, $y_i$:

$\frac{∂J_{θ}}{∂θ_0} = \frac{1}{n}\sum_{i=1}^{n}(h_θ(x_i)-y_i)$

$\frac{∂J_{θ}}{∂θ_1} = \frac{1}{n}\sum_{i=1}^{n}(h_θ(x_i)-y_i)x_i$

Se realizaron distintas pruebas para aproximar la ecuación de regresión lineal que mejor se ajuste a la distribución de datos, modificando las variables de forma arbitraria:

*   Θ (theta 0 y 1)
*   α (alpha)
*   Número de iteraciones

En la última prueba obtuvimos que los mejores valores para estas variables son:

*  $\theta{_0} = 1$
*  $\theta{_1} = 1$
*  $\alpha = 0.45$
*  $it = 20$

### Conclusiones

Después de varios intentos e iteraciones se ve que esta variable _malAcid_ no tiene relación lineal directa con la variable de _color_ del vino. ESin emabrgo existen modelos que gracias a su naturaleza pueden ayudar a aproximar mejor el comprtamiento de las variables para así determinar lla relación entre ellas.

## Archivos para revisión
En seguida se presentan los archivos a revisar: 

* README.md : Explicación del contenido de la carpeta.  
* ML_RegresionLineal.ipynb : Código de implementación, se analizó una base de datos con el fin de generar una hipotseis de predicción y utilizar un modelo de predicción, en este caso regresión lineal.  
* wine.data: base de datos de vinos.
* wine.names: metadata de la base de datos.
  
