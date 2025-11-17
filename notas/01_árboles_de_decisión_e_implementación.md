
Los árboles de decisión sirven tanto para regresión como para clasificación. Este puede tener muchos niveles en los que se pueden splitear los cortes.

## Elementos del árbol de decisión

El árbol consta de nodos y de hojas (leafs). Las hojas son los valores predichos. Los nodos evaluán los valores de $X_j$. 

![Screenshot_20251116_161854_Chrome](https://github.com/user-attachments/assets/4116dfcd-7e7c-4cb4-ad17-13d4a93254e5)

Las hojas se seleccionan a través de un mecanismo de votación. Los atributos pueden ser categóricos o bien continuos. Los nodos son los atributos. Sin un hoja es suficiente pura, es un resultado. 

¿Como particionamos una hoja o nodo? Como sabemos cada uno de los puntos del nodo? Como elegimos la variable y el punto de separación? 
Un árbol completo no es una buena forma de modelo. Es cada hoja, una observación y va a dar un buen ajuste. El problema como siempre es que es buena para la información de training, pero no tiene poder de predicción (overfitting). En un training dataset se va a ver 100% accurate, pero va a ser muy malo prediciendo. Cuando detenemos entonces el crecimiento del árbol? Esto esta muy relacionado con la medida del split, por lo que una forma de hacer la decisión y determinar cuál es el nodo a ser spliteado debe ser determinado de una forma estadística, a través de su  "impureza"

### Como separar

* Necesitamos una medida de impureza del noda que ayude a decidir como hacer una separación ("split") o qué nodo separar.
* La medida debe ser el máximo cuando el node el está igualmente dividido sobre todas las clases. --> Tenemos que encontrar un máximo de impureza.
* La impureza debe ser cero si el nodo es de una clase.

Una impureza muy grande implica que no es un buen lugar para hacer una separación.

## Ejemplo de construcción del árbol

![Screenshot_20251116_175625_Chrome](https://github.com/user-attachments/assets/0b9ac51c-8626-4e6f-a5a2-31173073d36a)

Tenemos que seleccionar la variable y punto de separación. La medida más importante es "impureza" a través de la medida de Gini. Muestra como cada variable se separa a través de Gini. En el ejemplo, el primer punto da .48. Todas las observaciones tiene que separarse en este segmento. En el punto de Gini 0 significa "muy puro", por lo que nos detenemos y es suficientemente puro y no hace falta continuar el árbol. El punto 0.44 del segundo nivel no es un nivel de impureza es demasiado alto.

## Medidas de impureza

$$ GINI(t) = 1 - \sum_{j} \left[ p(j \mid t) \right]^2 $$

Aquí cero es lo más puro. El valor $p(j \mid t)$ es la frecuencia relativa de la clase j al nodo t. Un valor muy alto implica que hay espacio para seguir particionando.

$$ Entropia(t) = - \sum_{j} p(j \mid t)\,\log\, p(j \mid t) $$

Este es similar al anterior con la diferencia que agrega la función Log. Es una alternativa al Gini, pero en términos generales deberían llevar al mismo resultado.

### Ejemplo

![Screenshot_20251116_181201_Chrome](https://github.com/user-attachments/assets/8c306ad6-00a8-42d7-b1c2-0bf1de5f9175)

Una vez que se splitean los nodos, podemos usar un promedio ponderado para enteder la impureza de la partición, como se muestra en el siguiente ejemplo.

![Screenshot_20251116_181201_Chrome](https://github.com/user-attachments/assets/2d14aa83-8c37-4bec-9447-a2e28a671bb2)

### Decisión Tree Regressor vs Decisión Tree Classifier

En python, existen las funciones de DecisionTreeRegressor y DecisionTreeClassifier.

* DecisionTreeClassifier: Se puede utilizar para problemas del tipo 0,1 o bien para problemas multiclase. El término de error suele ser Gini o bien Entropía (a ser minimizados) La función **predict()** se utilizará para predecir un núimero entero o **predict_proba()** para predecir probabilidad.

* DecisionTreeRegressor: Se puede también utilizar para problema 0,1. El término de error suele ser el mse (a minimizar). El predict() method se utilizará para predecir una variable continua.

Cada uno dependerá de la variable target a predecir.

### Medida de performance del modelo

![Screenshot_20251116_183155_Chrome](https://github.com/user-attachments/assets/623251c8-39aa-4f97-ad15-5ad280aecc4b)

De acuerdo a los modelos de clasificación o regresión nos daran las medidas. No aplica solo para árboles de decisión. 

![Screenshot_20251116_183604_Chrome](https://github.com/user-attachments/assets/35a96505-d4ca-4a03-b662-ea4f59f2e67e)


### Formulas en python

Dentro de la librería sklearn podemos encontrar

from sklear.tree import DecisionTreeClassifier, DecisionTreeRegressor


