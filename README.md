# PGN
En el código HGESD-PGN está el algoritmo desarrollado para el análisis de los puntos de deforestación dados por el IDEAM. 
En este se presenta el modelo en desarrollo el cual: 
- Crea un sistema de organizaciónde la información en carpetas.
- Emplea el método de la silueta estable de kmeans++, este aún presenta procesos de aleatoriedad los cuales no siempre termina decantando por el mismo valor. ¿Será dejarlo una mayor cantidad de repeticiones?, ¿existe una manera más estable?
- Se determinan los clusters creando tablas de atributos con este valor.
- Determina los centroides. Es pertinente validar la estabilidad del proceso y la elección geográfica del mismo. También se ha de tener en cuenta que este punto es el que minimiza la distancia euclidea, en principio debería ser el mismo, aunque el algoritmo se presenta de manera aleatoria hasta encontrar un punto de equilibrio.
- Se trazan los polígonos mínimos que contiene a cada cluster.
- Se realizan histograma de longitud en la cual se ajuste a una curva de densidad de probabilidad normal. El error de este ajuste se repota, en su mayoría presentan valores aceptables, aún así existen algunos muy malos.
- De igual manera se trazan histogramas para los angulos en radianes para cada cluster.
Es importante denotar que la longitud de conteo se hace de manera programada para cada caso, ¿se toma la mejor?
- A partir del ajuste se determinan los radios de mayor probabilidad de conseguir deforestación.
- Como último se buscan los angulos preferentes y se trazan vectores de longitud \mu y centrado en el angulo para denotar tendencias de porsible preferencia.

Como observaciones: importante trabajar la estabilidad del código para que cada corrida sea estable; al generar el histograma de ángulos, existe la posibilida que haya más de uno, pero solo se traza un unico vetor, importante corregirlo. 

tomando el valor de sigma para cada ajuste se busca determinar una pseudoenergía para caracterizar "el peso" de cada uno, aún está siendo evaluado el valor de a el cual caracteriza el sistema: ¿fracción de alertas por cluster?, ¿relación entre areas? ¿alguna otra?
