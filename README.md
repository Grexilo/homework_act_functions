# Comparación Entre Las Funciones De Activación ReLU y Leaky ReLU
### Tarea Introducción al Deep Learning

El objetivo principal de esta tarea consiste en comprobar la siguiente declaración:

**Leaky variants always outperformed the strict ReLU activation function Setting a = 0.2 (huge leak) seemed to result performance than a = 0.01**

## Dataset

Se escoje como dataset [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html), que corresponde a 60000 imagenes RGB de 32 x 32.
Para este caso, cada imagen sera reorganizada como un vector de tamaño 32*32*3, esto con el fin de organizar los 3 canales de
las imagenes uno tras otro, este dataset corresponde a 10 clases de imagenes clasificadas de la siguiente manera.

| Label | Description |
|-------|-------------|
| 0     | Airplane    |
| 1     | Automobile  |
| 2     | Bird        |
| 3     | Cat         |
| 4     | Deer        |
| 5     | Dog         |
| 6     | Frog        |
| 7     | Horse       |
| 8     | Ship        |
| 9     | Truck       |

De este dataset se toman 50000 imagenes para el entranamiento y validación para los modelos y 10000 imagenes pare realizar la
evaluación de la imagenes.


## Modelos

Para probar la declaración, es necesario realizar el entreamiento de un modelo variando sus funciones de activación, para este caso
se escogio una arquitectura con una capa de entreada de 3072, que corresponde a como se organizaron los datos, dos capas ocualtas,
cada una con 128 neuronas y una capa de salida de 10 neuronas, que corresponden a las 10 clases existentes en el dataset.

![Arquitectura de red](/imagenes/arc.png)

Para la inicialización de los pesos de cada capa, se implemento la inicialización por defecto de Keras, este [link](https://keras.io/api/layers/initializers/)
podemos revisar la documentación sobre la inicialización de pesos. Desde la documentación podemos observar que por defecto
los pesos se inicialización con la funcion **Glorot Normal**; es este [video](https://www.youtube.com/watch?v=ScWTYHQra5E&t=334s)
puedes revisar una explicación de como funciona esta función.

## Recomendaciones para trabajos Futuros

- Se puede jugar con otra arquitectura de red que sea mas adecuada para el problema

- La forma de presentar los datos a la red, podria realizarse primero una conversion de cada imagen a escala de grises y luego de esto si ser presentada como un vetor normalizado, esto con el fin de reducir la cantidad de neuroas en la capa de entrada.

- Hacer uso de tecnias de regularización que permitan mejorar los resultados obtenidos.
