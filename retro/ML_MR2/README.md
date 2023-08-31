# Machine Learning - Momento de retroalimentación 2
## Uso de framework o biblioteca de aprendizaje máquina para la implementación de una solución.
El objetivo es Programa uno de los algoritmos vistos en el módulo (o que tu profesor de módulo autorice) haciendo uso de una biblioteca o framework de aprendizaje máquina. Lo que se busca es que demuestres tu conocimiento sobre el framework y como configurar el algoritmo. 

Este desarrollo se implementó en el siguiente documento:

*   MR_M2_Framework.ipny

Para ese ejemplo se utilizó el **modelo de aprendizaje supervisado de árboles de decisión**, se eligió este modelo ya que en este caso se requiere de una clasificación, indicar si una persona requiere un marcapasos o no de acuero con las características de sus pulsos cardiácos. 

La base de datos utilizada fue otorgada para una actividad de estadística, se anexa en esta carpeta y se llama:

*   El marcapasos.csv

Esta base de datos contiene tres categorías con 102 muestras:

| Variable  | Tipo |
| ------------- | ------------- |
| Periodo entre pulsos  | Numérica  |
| Intensidad de pulso  | Númerica  |
| Uso de marcapasos  | Categórica  |

La tercera característica es la clase de salida que buscamos clasificar.

Para buscar la mejor predicción se modificaron los hiperparámetros del modelo, en este caso podemos modificar:

*   **max_depth** : El número máximo de niveles que queremos que tenga el árbol.
*   **min_samples_split** : El número mínimo de muestras necesarias para expandir un nodo.

Realizamos seis diferentes pruebas para poder comprobar cúal nos otorgó mejores resultados:

| Prueba  | max_depth | min_samples_split |
| ------------- | ------------- | ------------- | 
| 1 | 3 | 2 |
| 2 | 4 | 2 |
| 3 | 5 | 2 | 
| 4 | 3 | NA |
| 5 | 4 | NA |
| 6 | 5 | NA |

Para cada prueba se obtubieron los siguientes resultados:
| Prueba  | max_depth | min_samples_split | Accuracy | Precision | Recall | Fone |
| ------------- | ------------- | ------------- |  ------------- | ------------- | ------------- | ------------- | 
| 1 | 3 | 2 | 1.0 | 1.0 | 1.0 | 1.0 |
| 2 | 4 | 2 | 0.9523 | 0.9166 | 1.0 | 0.9565 |
| 3 | 5 | 2 | 1.0 | 1.0 | 1.0 | 1.0 | 
| 4 | 3 | NA | 1.0 | 1.0 | 1.0 | 1.0 |
| 5 | 4 | NA | 0.9523 | 0.9166 | 1.0 | 0.9565 |
| 6 | 5 | NA | 1.0 | 1.0 | 1.0 | 1.0 |

De igual manera para cada prueba se realizó una matriz de confusión para verificar las predicciones.

### Conclusiones
Los resultados de estas pruebas, al ser la mayoría mayores a 0.9 o ser exactamente 1, dan a suponer que existión un sobreajuste, lo cual nos puede decir que talvez este modelo no es el más adecuado para esta cantidad de muestras o que los volores para determinar si los datos pertenecen o no a una clase no dan mucha información.

