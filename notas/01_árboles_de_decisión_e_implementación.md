
Los árboles de decisión sirven tanto para regresión como para clasificación. Este puede tener muchos niveles en los que se pueden splitear los cortes.

## Elementos del árbol de decisión

El árbol consta de nodos y de hojas (leafs). Las hojas son los valores predichos. Los nodos evaluán los valores de $X_j$. 

![Screenshot_20251116_161854_Chrome](https://github.com/user-attachments/assets/4116dfcd-7e7c-4cb4-ad17-13d4a93254e5)

Las hojas se seleccionan a través de un mecanismo de votación. Los atributos pueden ser categóricos o bien continuos. Los nodos son los atributos. Sin un hja es suficiente pura, es un resultado. 

¿Como particionamos una hoja o nodo? Como sabemos cada uno de los puntos del nodo? Como elegimos la variable y el punto de separación? 
Un árbol completo no es una buena forma de modelo. Es cada hoja, una observación y va a dar un buen ajuste. El problema como siempre es que es buena para la información de training, pero no tiene poder de predicción (overfitting). En un training dataset se va a ver 100% accurate, pero va a ser muy malo prediciendo. Cuando detenemos entonces el crecimiento del árbol? Esto esta muy relacionado con la medida del split, por lo que una forma de hacer la decisión y determinar cuál es el nodo a ser spliteado debe ser determinado de una forma estadística, a través de su "pureza".
