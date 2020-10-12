# Ejercicios Tema 1. Arquitecturas software para la nube

## Ejercicio 1. Buscar una aplicación de ejemplo, preferiblemente propia, y deducir qué patrón es el que usa. ¿Qué habría que hacer para evolucionar a un patrón tipo microservicios?

La primera aplicación que se me ocurre de ejemplo es la que desarrollé en mi TFG. Se trata de una aplicación que se encarga de resolver sistemas de ecuaciones lineales dispersos usando diferentes arquitecturas hardware paralelas (memoria compartida en CPU, memoria distribuida, GPU(CUDA)). El patrón usado en este programa es claramente monolítico, ya que todo se ejecuta en el mismo código.

Para lograr un patrón basado en microservicios lo que se podría hacer es crear un servicio independiente para cada tipo de arquitectura paralela en las que hacemos los cálculos.

## Ejercicio 2. En la aplicación que se ha usado como ejemplo en el ejercicio anterior, ¿podría usar diferentes lenguajes? ¿Qué almacenes de datos serían los más convenientes?

De hecho en esta aplicación se usan diferentes lenguajes, ya que se usa C++ para la ejecución secuencial del código y añadiendo las primitivas de OpenMP se desarrolla el código paralelo en CPU, entre otras cosas. Por otra parte, se usa CUDA para la programación en GPU de los algoritmos paralelos para esa arquitectura.

En cuanto a almacenes de datos, esta aplicación no necesita de almacenamiento de datos realmente, ya que recibe como parámetro las matrices a calcular y devuelve el resultado del cálculo y los tiempos de cómputo en las diferentes arquitecturas.