# a03 Métodos de simulación

# a03-02 - Tema 2: Números aleatorios

# Generación de números aleatorios
Alumno pakistaní, que solo habla inglés
Problemas de horario con el de Visión

## Grupos de prácticas
Se pueden cambiar, 
Fechas de trabajo y test
Qué grupos presenten cada día

# Generación de números aleatorios
En las simulaciones habrá que identificar los factores 
Y ajustar la distribución de probabilidad

> Parámetros : variables aleatorias que pertenecen a alguna distribución  

## Generar valores en dos pasos:
1. Valores en una distribución en concreto: `Y~U[0,1]` Distribución uniforme entre 0 y 1. Todos los valores tienen la misma probabilidad

2. `X = f(Y)`
f = operaciones matemáticas que generan nuestra distribución.

> Todavía se estudian contrastes y generadores de números  

Hoy nos centraremos en la distribución uniforme.

## Breve introducción a la estadística 15 mins
- **Fenómeno aleatorio**: ocurren en la naturaleza y no se conoce con exactitud
	- Ejemplos
		- Juegos de azar: cara-cruz, cartas, poker, acertar la ruleta
	- ¿Cómo se estudian?
		- asignamos una `variable aleatoria`
			- Identificamos dos cosas
				- Conjunto de valores que puede tomar este fenómeno aleatorio
				- Probabilidades asociadas: probabilidad que puede tomar cada uno de esos valores
		- Ejemplo moneda:
			- `{cara, cruz}`
			- `{0.5, 0.5}`
		- Ejemplo Ruleta color:
			- {éxito, fracaso}
			- {0.5, 0.5}
		- Ejemplo Ruleta número:
			- {éxito, fracaso}
			- {1/nºvalores, 1-1/nºvalores} 
	- **Soporte: conjunto de valores que puede tomar**
		- Variables *Continuas*: Soporte continuo
		- Variables *Discretas*: Soporte discreto
	- 

> Soporte: conjunto de valores que puede tomar  

> No es cierto que infinito sean continuos.  
> Ejemplo: Edad -> Enteros no negativos. Es discreto e infinito  


### Probabilidad descriptiva
- Medidas 
	- centralización: media, mediana, moda. La media es la más usada.
	- dispersión: varianza , desviación típica. (son similares, porque una es el cuadrado de la otra), coeficiente de variación
	- forma: coeficiente de curtosis, apuntamiento, quartiles, percentiles

Usar una medida de centralización puede llevar a errores.
Por eso siempre debeos apoyarnos en una medida de dispersión.

Varianza grande == mayor dispersión

Estos 3 casos tienen la misma media, pero diferentes varianzas
——||||—— (varianza pequeña)
—|—|—|—| (varianza grande)
|||——||| (La media no está en la población)

Para distinguir situaciones atípicas, necesitamos un **histograma**. 

## Función de densidad
`f(X)`: densidad
`F(X)` : Distribución. 

F(a) = PProbabilidad de que mi variable sea <= a
`f(X) = P(x=a)`**MAL** , en soporte continuo, será siempre 0, porque teneos infinitos posibles valores
Es un ~= en vez de solo un =

Curva creciente


## Función de Densidad
**El área que deja una función de densidad debe ser la unidad =1**
`Gaus` : 


La relación entre 
F(a) = integral min

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Foto%2025%20sept%202019%20133656%203.jpg)


**Formación de masa**
P(X)
P(a) = P(x=a)

En caso discreto también se habla de
P(a) = P(X=a) si el soporte es finito
P(a) = P(x<=a)

La relación entre, ya no es de una integral, sino entre un 
F(a) = E(x<=a) P(X=x) **DISCRETO**
Integral **CONTINUO**

> OJO: mirar la Relación en la función de densidad y de probabilidad? en el caso discreto y en el caso continuo.  


# **MÉTODOS DE SIMULACIÓN** : Capítulo 2. Generación de números aleatorios
> En la práctica no necesitamos implementar los contrastes, solo utilizarlos   

Se estudian a nivel teóricos 
> todos los métodos son imperfectos  

Se siguen proponiendo generadores y contrastes
En la historia, han habido dos autores que tuvieron un rifirrafe en sus hipótesis propuestas de generadores sy contrastes, se tiraban el trabajo del uno al otro.

## Antes de los ordenadores ->  físicos
Tippet 1927 -> se utilizaban tablas del censo, 10.000 números
Royo y Ferrer -> 250M basados en lotería
Rand Corporation: 1 millón de números aleatorios basados en medición de ruido
> Con eventos físicos, no se puede repetir la secuencia y por tanto tampoco el experimento  

## Propiedades
	- Memoria: No nos interesa tener almacenados todos los números en memoria
	- Reproducibilidad: repetir experimento sin tener que guardar la secuencia.

Idea de von Neumann : Procedimientos algorítmicos de generación de números -> La idea (von Neumann) es producir números que parezcan aleatorios, empleando las operaciones aritméticas del ordenador: partiendo de una semilla inicial (*u**0*, *u**1*,…, *u**-p+1*), generar una sucesión mediante *u**i*= *d*(*u**i-1*,…, *u**i-p*), para cierta función *d*. 

> El periodo de los generadores surge de la naturaleza recursiva de las funciones. Dado un mismo parámetro de entrada en un momento dado, la secuencia será la misma.  

> La semilla marca el punto de start  
> El uso de semillas nos permite Mutabilidad y Reproducibilidad  

## ¿Cómo contrastamos y comprobamos que la secuencia es aleatoria?
- Kolmogorov (definición filosófica): Una sucesión de números es aleatoria si no puede producirse eficientemente mediante un programa más corto que la propia serie. 
- Definición estadística: Una sucesión de números aleatorios (*u**i*) es una sucesión de números en (0,1) con las propiedades de 
	- Propiedades estadísticas necesarias
		* **Uniformidad en (0,1)** y 
		* **Aleatoriedad o independencia estadística.**

Otras propiedades :
1. Rapidez
2. Poco consumo de memoria
3. Portabilidad
4. Sencillez de implementación
5. Reproducibilidad y mutabilidad (semilla)
6. Periodo suficientemente largo. No podemos generar secuencias infinitas, siempre habrá un periodo


# Contrastes empíricos
> Podríamos utilizar estos contrastes para estudiar cualquier distribución. Nosotros podemos centrarnos en Uniformidad  
## Bondad de ajuste o uniformidad
- Contraste `X2` (Chi cuadrado) - *Contraste de Pearson*:
	- De los más antiguos
		- Ventajas
			- Continuos y discrestas
		- Desventajas
			- No es muy potente: 
				- Si me rechaza, entonces no es
				- Si me lo acepta, no es 100% seguro. Hay que usar otro contraste.
- Kolmogorov-Smirnov
	- 

> Se suele usar una batería de contrastes para confirmar los distintos resultados.  

> Usaremos los paquetes estadísticos, no es necesario implementarlos nosotros  


### Contraste Chi**2: Pasos de contraste de hipótesis
- Se parte de una muestra 	x1 .. xn
- Hipótesis: Nuestra distribución es una en concreto: Fn(X) = F0(X)
	- Donde n es cada distribución : Normal(media, varianza, máxima verosimilitud ), Weibull, Uniforme , … etc
	- Seleccionas 15 y te dice cual sí es
- Cogemos el valor mínimo y máximo en la muestra
	- Para saber el recorrido de valores
- El contraste va a dividir K-Clases (mínimo 5). Recorridos de la misma longitud
- Frecuencias observadas: O1, O2
- Contrastamos con las frecuencias esperadas
	- P(xi € O3) = P(a<= xi <=b) = Integral(a,b) f(x)dx 
	- Es decir calcular la función de distribución
	- ![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/bear_sketch@3x%203.png)
- Nivel de discrepancia
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-09-25%20a%20las%2014.15.26%203.png)
	- Comprobar si el valor que obtenemos tiene una distribución de X2
		- Comprobar en una tabla 
		- Comprobando los grados de libertad
			- Número de clases (K) : pi
			- r = parámetros de nuestra distribución 
			- **k-r-1**
			- En la uniforme r = 0
			- En la normal (N(M,desviación^2) -> r = 2 parámetros (media y desviación típica)
		- Buscamos el primer valor más pequeño que el mío
		
> En nuestro caso, para contrastar la uniformidad escogeremos *k*subintervalos de [0,1] de la misma longitud, siendo *p**i*= 1/*k*y, por lo tanto, *E**i*= *n/k*y *r*= 0, ya que no ha sido necesario estimar ningún parámetro de la distribución para obtener *p**i*.   

### Contraste Kolmogorov-Smirnov: Teórico VS Empírico
- Muestra: x1…xn
- Gráfico: Distribución escalonada
	- Valores más repetidos -> el salto es más grande
- Estamos contrastando que Fn(X) = F0(X)
	- Dibujaos la función de distribución 
- Medimos la distancia entre el valor experimental y el valor teórico
	- Nos quedamos con el **Máximo de todas las diferencias**

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-09-25%20a%20las%2014.24.40%203.png)



![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-09-25%20a%20las%2014.25.44%203.png)

### Contraste específico para el uniforme
Por debajo utiliza el X**2 (Chi cuadrado)
> En las prácticas se necesita este contraste  

- Agrupamos la muestra de 40 en 40 (sin ordenar)
- Calculamos el nivel de discrepancia entre lo observado y lo teórico en cada grupo
- Si es uniforme, comprobar que estos valores 
- Hacer el contraste (Chi Cuadrado o Kolgomorov-Smirnov) para comprobar que estos valores encajan con una Chi Cuadrado



## Contrastes de Aleatoriedad o Independencia estadística
#### Contraste de rachas
Generamos una muestra de nuestro generador
Secuencia de números: x1 .. xn
Convertimos en una sucesión binaria comparando un elemento con el siguiente. 1 si es menor (crece la racha) y 0 si es mayor (decrece la racha)
0’s -> Racha decreciente
1’s Crecientes

Contamos cuantas rachas hemos tenido en nuestra muestra
Calculamos varias muestras y varias rachas

**El número de rachas de cada muestra, debe  ser una normal con media y varianza estas**
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-09-25%20a%20las%2014.40.48%203.png)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-09-25%20a%20las%2014.44.09%203.png)


#### Contraste2: Contraste de rachas por encima y por debajo de la mediana
- Convertimos en sucesión binaria mirando la mediana. 1 si es menor y 0 si es mayor

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-09-25%20a%20las%2014.46.39%203.png)


#### TEST DE PÓKER
> Test de póker es el más potente y es el que usaremos  
> Contraste muy específico para contrastar generadores de números aleatorios.  

- Transofrmamos nuestra secuencia original en enteros (del 1 al 10)
- Agrupamos en grupos de 5. Para tener frecuencias acumuladas
	- cada clase son las jugadas de póker
	- La probabilidad de cada jugada es conocida por Teoría de la probabilidad. Probabilidad de póker, de full, de parejas, tríos … etc
- Para que funcione muy bien , tenemos que tener al menos 5 repeticiones en cada clase
	- Si el repoker, tenemos menos que juntar esta clase con la del póker
	- Esto es habitual para muestras menores de 250K
- 
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-09-25%20a%20las%2014.52.30%203.png)



# a03-03 - Tema2: Números aleatorios 2

Antonio estudió en el plan 92



## Recapitulación
**Bondad de ajuste** con dos 
Aleatoriedad (Rachas, Test de póker)

## Generadores congruenciales
Generadores algorítimicos recursos.
Punto de partida de números aleatorios.
Los siguientes generadores intentan solucionar las 2 carencias:
	- Longitud de secuencia finita -> Periodo
	- Secuencia, no es totalmente aleatoria

### Fórmula recursiva generadores congruenciales
- a: multiplicador
- b: sesgo
- m: módulo
- xn: 

> xn+1 = (a*xn +b) mod m  
> [0, m)  
- nunca podremos tener una secuencia mayor al módulo `m`
- Para transformar estos valores al intervalo 0,1 , tenemos que dividir por m

- Si b = 0  -> generadores multiplicativos
	- **Cuando son multiplicativos, el periodo máximo será** `m-1`


El generador debe ser rápido, por ello las operaciones deberían ser sencillas.

La operación módulo se puede realizar de forma eficiente

```py
def generadorCongruencial(x0=0, a=3939, m=2**31-1, b=0):
	return (a*x0+b) % m
```

Estas semirectas nos indican cuál es más aleatorio
Más rectas, más aleatorio.

Número finito de planos -> Estructura reticular; En más dimensiones se llama hiperplanos.

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-02%20a%20las%2013.23.37%203.png)

Observaciones: 
1. Un generador congruencial tiene ciclos. 
2. La longitud del ciclo depende de la selección de los parámetros (comparar casos 1 y 3). 
3. Dentro de selecciones de parámetros que conducen a una misma longitud de ciclo, algunas salidas parecen más aleatorias que otras (comparar casos 1 y 2). 
4. La representación de los pares (*x**i*, *x**i*+1) sugiere que éstos se disponen en un número finito de rectas (representación de tuplas -> hiperplanos). 

### Propiedades que se deben cumplir para tener un buen generador
Comprobar para cualquier generador si tiene periodo máximo.
Esta proposición valida la longitud de periodo, no nos permite elegir buenos valores.
> **Proposición**: Un generador congruencial tiene periodo máximo *m*si y sólo si:  
> 1) mcd (*b*, *m*) = 1;   
> 2) *a*= 1 mod *p*para cada factor primo *p*de *m*;   
> 	`a -1 es múltiplo de p`  
> 3) *a*= 1 mod 4 si 4 divide a *m*.   

Para conseguir una *Eficiencia computacional* el módulo debería ser `*m*= 2β`. La operación sería retener una cantidad de bits.
En la práctica, se utiliza `*m*= 2β-1` o `*m*= 2β +1` para evitar que sea div 4.

> **Proposición**. Un generador multiplicativo con módulo *m*= 2β ≥ 16 tiene periodo máximo *m*/4 si y sólo si *a*mod 8 = 3 ó *a*mod 8 = 5 y *x*0 es impar.   

b=0 , es lo mismo, pero nos reduce el 

> **m debe ser primo** y lo más grande posible  
> 	*m debería ser el número primo más grande que se pueda representar en nuestra aritmética de CPU (16, 32 o 64 bits)*  
> 	Los más frecuentes serán: `2^31-1` y `2^16+1` que además permite la eficiencia computacional  
> a debe ser una raíz primitiva de m-1  

> **Proposición**. Un generador multiplicativo tiene periodo *m*-1 sólo si *m*es primo. El periodo divide a *m*-1 y es *m*-1 si y sólo si *a*es una raíz primitiva de *m*-1, es decir, *a*≠ 0, *a*(*m*-1)/*p*≠ 1 mod *m*, para todos los factores primos *p*de *m*-1.   

Si encontramos una raíz primitiva, calcular las siguientes raíces es trivial.
> **Proposición**. Si *a*es una raíz primitiva de *m*, *a**k*mod *m*lo es siempre que mcd(*k*, *m*-1) = 1.   

Pueden haber muchas raíces.

### Distintos autores han analizado las distintas raíces primitivas para calcular su aleatoriedad
Se estudia por distancia espectral de los hiperplanos 

### Marsaglia, calculó una cuota superior
Número de hiperplanos aleatorios 
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-02%20a%20las%2013.40.11%203.png)
RANDU de IBM era muy mal generador

### Fishman y Moore (1986)
Analizaron todas las raíces primitivas de m 23093, identificaron 410 multiplicadores

Fishman posteriormente encontró a=16807 (generador congruencial estándar), a=48271 y a=69621 (estos dos eran mejores que el primero, pero fueron menos utilizados)

### Generador congruencial estándar
Arquitecturas de 32 bits, Park y Miller (1988) → mínimo estándar:

1. Ser de periodo máximo;
2. Que su salida parezca aleatoria;
3. Que se pueda implementar de forma eficiente en aritmética de 32 bits. 

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-02%20a%20las%2013.46.53%203.png)


### Método de Schrage (1983) (Evitando desbordamiento)
se pueden reordenar las operaciones para evitar el desbordamiento
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-02%20a%20las%2013.47.06%203.png)

Si nuestra simulación es muy compleja, y necesitamos secuencias mayores de (2147483647  -1), necesitaremos otro generador. para el resto se considera un buen generador.

## Otros generadores
### Generadores de registro de desplazamiento (aumenta el nivel de recursividad) - L’ecuyer
Para proponer generadores, es fundamental expresar el periodo de forma matemática. Normalmente basados en polinomios característicos. (Algebra finita de n elementos)

(Paper de referencia para hacer el trabajo y la presentación)

Si aumento el nivel de recursividad

Si el polinomio es primitivo ->El periodo de generador es  `m^k -1` (muchísimo más grande que m-1). Lo malo es que no aporta solución par aletoriedad

Nos dará secuencia de número binarios aleatorios
k = **número de retardos tomados**

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-02%20a%20las%2013.55.42%203.png)

NO NOS GARANTIZA ALEATORIEDAD

### Generador de Tausworthe
Coge secuencias binarias en valores entre 0 y 1 , distribuidos uniformemente.
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-02%20a%20las%2013.57.23%203.png)


**girador de Mersenne**: (práctica)


### Generadores de Fibonacci Retardados
La operación binaria suele ser +,-, * , XOR
El periodo máximo está relacionado al análisis de sucesiones lineales repulsivas de enteros.

Marsaglia

Da un periodo , fácil de implementar
Problema de estructura reticular. 

Son operaciones lineales : `axn+b` son generadores recursivos lineales

### Generadores no lineales
La no linealidad se puede introducir en dos puntos:
	1. Usar un generador con función de transición lineal, produciendo la salida mediante una transformación no lineal del estado.  (función de transición)
	2. Usar un generador con función de transición no lineal.  (transformación)

Es difícil demostrar su periodo.

### Método congruencial de inversión explícita
Es muy bueno en aleatoriedad (totalmente aleatorio), pero no mejora el periodo que sigue siendo m.

Método congruencial de inversión explícita 

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-02%20a%20las%2014.04.55%203.png)

Secuencia totalmente aleatoria, pero solo de longitud m

Determinar bajo que circunstancias se alcanza el periodo máximo, es muy complicado

> AES , es mejor que el anterior y se usa mucho para encriptación  

### Combinación de generadores
Combinar secuencias para aumentar la aleatoriedad y el periodo.
Lo difícil es demostrar matemáticamente el periodo.

- BARAJEO
	- permutación fija (barajeo): composición, no es muy buena
	- permutación aleatoria (barajeo): desordenar aleatoriamente la secuencia
		- primer secuencia nos da resultados
		- segunda secuencia es el índice para identificar qué valor es el que se devuelve

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-02%20a%20las%2014.11.39%203.png)

**Composición**
Tengo N generadores, cojo el resultado y realizo una operación entre ellos.

MRG32k3a -> está en una práctica para hacer en memoria

### Generadores paralelos
En simulaciones que ha falta paralización:
Distintos hilos de ejecución necesitan números aleatorios, ¿Cómo los distribuyo?
Va en contra de la propiedad de **reproducibilidad**

En la práctica se utiliza un mismo generador con semillas distintas por cada hilo de ejecución.

### Generadores comerciales
> Artículo de Park y Miller (1988) como advertencia sobre la mala calidad de algunos generadores comerciales.   

**ISML** implementa generadores multiplicativos de módulo *m*= 231-1 y multiplicadores *a*= 16807, 397204094 y 950706376. 

> Libro muy bueno: Numerical recipes 1992, 2007  
> Bueno para ingenieros e informáticos  
> Hay algoritmos implementados y eficientes  

> en la mayoría de lenguajes y herramientas estadísticas se utilizan congruenciales  

## Contrastes de aleatoriedad modernos
Test de póker, Huecos, rachas, permutaciones. .Disponibles en cualquier entorno estadísticos. Son muy básicos para validar a un generador.
Estos contrastes Siempre dirían que los generadores son “buenos”

### Contraste espectral
> Analiza la estructura reticular de los generadores, calculando la distancia de   los hiperplanos paralelos en diferentes dimensiones.  
Para validar contrastes hace falta un problema de optimización.
Como es una fórmula cuadrática y no lineal, es difícil calcular el óptimo
Hay heurísticas para aproximar la solución.

### Baterías de test de aleatoriedad
> 15 o 20 contrastes , con que uno diga que no sea aleatorio, el generador no es aleatorio.  
**Para la práctica**
www.stat.fsu.edu/pub/diehard

DIE HARD Randomness Test Suite : programa de estudio de aleatoriedad

### NIST (National institute of standard and technology)
Se usa más en criptografía en vez de en simulación.

### Tuftest
- Prueba
	- 
	- cumpleaños
	- de gorila

### TESTU01
simul.iro.umontreal.ca/testu01/tu01.html
Otras baterías

### 
La calidad  hay que revisar 


Los tests permiten 12MB , y los estudios suelen necesitar 40 muestras.

## Información adicional
Dos sitios excelentes y actualizados con abundante información sobre números aleatorios son las páginas de Hellekalek http://random.mat.sbg.ac.at y de L’Ecuyer http://www.iro.umontreal.ca/~lecuyer. 
Hay varios sitios que proporcionan generadores verdaderos de números aleatorios. 
* http://www.random.org, **que usa ruido atmosférico;**
* http://random.hd.org/index.html (Java EntropyPool), que emplea ruido 
proveniente de entradas en distintos sitios web y otros dispositivos físicos. 
Las revistas *Communications of ACM*y *Applied Statistics*publican a menudo nuevos algoritmos de generación de números aleatorios. En particular, los de esta última, pueden obtenerse de Statlib en http://lib.stat.cmu.edu/. 

> Para repetir un experimento, necesito almacenar toda la secuencia aleatoria completa de   

> ACM y Applied statics, cada 4 años saca estados de arte de generación de números aleatorios, y demás	 técnicas  

La librería científica GNU tiene una sección entera dedicada a números aleatorios http://www.gnu.org/software/gsl/manual/html$_$node/Random-Number- Generation.html. 

## Referencias
hay papers que habrá que mirar 1 o dos papers para realizar el paper



# Siguiente sesión veremos
Parámetros aleatorios.
Determinaremos la distribución  mediante el contraste de hipótesis

Generaremos valores de esa distribución

X~Distrib(param)

> Clave: operaciones que tenga que realizar, no disminuya mi periodo  

Para cada distribución que quiera generar, necesitaré varios valores aleatorios, por lo que el periodo ya no será `m-1`

> **Teorema central del límite**  
Si tenemos un buen generador de la normal, podremos generar muchas distribuciones.

## índice



# a03-04 Tema 3: Generación de variables aleatorias

Antonio Jimenez
Capítulo 3

## índice
- Generación de distribuciones continuas
	- métodos genéricos (de inversión, rechazo, cociente de uniformes)
	- métodos específicos (normal, exponencial, gamma, Erlang, Cauchy…)
- Generación de distribuciones discretas
	- Métodos genéricos ( de 
- Distribuciones multivariantes
	- 
- Procesos escolásticos
- Métodos basados en cadenas de Markov (métodos escolásticos)
- Conclusiones
- Referencias



## Métodos genéricos para variables continuas
### 1. Método de inversión
Solo se puede aplicar si tenemos la expresión matemática de la función de distribución 
`F(a) = P(X=a) = Integral[infinito, a] f(x)dx`

- generar un valor de la uniforme
- pasárselo como argumento a la función inversa

Inconvenientes:
- Expresión matemática de la función de distribución
- Coste computacional asociado al cálculo de la inversa o su ejecución

EJEMPLO
Weibull `W(alpha, 1)`; Muy utilizado en fallos de sistemas (*Sistemas de fiabilidad*). Tiempo hasta que una pieza falla.
Su función de distribución es: `F(x) = { 0 x<0; 1-e^(-x^alpha) x=>0)`

### ¿Cómo calculamos la inversa?
- lo igualamos a la u: `1-e^-x^alpha = u`
- despejamos x
- e^-x^alpha = 1 -u
	- aplicamos logaritmo neperiano
	- x^å = -ln (1-u)
- x = (-ln(1-u))^1/å
- sabemos que 1-u sigue siendo una distribución uniforme
- x = (-ln(u))^1/å

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.30.30%203.png)


### 2. Método de rechazo por Von Neumann 1951
Necesitamos la expresión matemática de la función de densidad `f(x)`

Suponemos que tenemos una segunda función `g(x)` de la cual es sencillo generar valores.

Tal que `f(x) <= ag(x)` la función necesita ser una constante `a` para cubrir todos los valores de f(x)

Dos problemas:
- Encontrar `g(x)`
- Encontrar la constante `a`

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.30.16%203.png)

Para generar la función g, es posible que necesite valores de la uniforme. (De mi generador)
En el bucle, necesitamos generar un número aleatorio por cada iteración.

El periodo de salida de este método siempre va a ser más pequeño.
Porque en cada iteración quemo números aleatorios hasta que se cumpla la condición de parada.


![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.34.01%203.png)

- Podemos observar que `ag` cubre todos los valores de f(x)
- Si el valor generado está por encima de f(x) lo rechazamos
- Si cae por debajo de f(x) lo devolvemos para usar

> Intentaremos que g(x) se parezca lo máximo posible a f(x) y que sea fácil generar valores.  
> Es decir que el área de rechazo sea muy pequeña, que a sea lo más cercano a 1.  
- P(X aceptado)  = 1/a
- Conociendo a, conocemos la eficiencia de nuestro algoritmo. `a=1` es la más eficiente, porque f(x) y g(x) dará el mismo resultado.

EJEMPLO (más obvia, usando la función de densidad de la uniforme):
Función ß , siempre genera resultados entre 0 y 1
Generación de una variable Be(3,4).
La media y varianza se pueden calcular a partir de åß

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.39.54%203.png)

- Queremos una función de densidad auxiliar que sea fácil generar valores
La función de densidad de la uniforme es `g(x) = 1`
- Cómo calculamos la `a`?
	- Necesitamos que a => f(x)/g(x) -> a=>f(x)
		- función en su máximo
		- de su máximo del cociente

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.44.53%203.png)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.43.51%203.png)
a > 2 -> algoritmo no es eficiente


![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.47.05%203.png)


EJEMPLO (Más complejo y eficiente) GAMMA
Tiene valores no negativos
Gamma puede ser Erlang y sería más sencillo.
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.47.55%203.png)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.49.15%203.png)

Dividimos entre `1/c` para que el área sea la unidad y por tanto sea una función de densidad.
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2013.50.22%203.png)

Luego hay que determinar el valor de `a` para que cubra la función de densidad original `f(x)`

> La función e densidad está relacionada con la función de distribución mediante una integral  
> F(X) -> distribución  
> f(x)  -> densidad  
>    
> F(x) = integral f(x)dx  
> Luego calcularíamos la función de distribución invertida F-1(x)  
>    
> También podríamos derivar la de distribución para obtener la de densidad  
> TODO: añadir gráfico  
>   



### Método de cociente de uniformes
Se puede usar si disponemos la función de densidad de nuestra distribución `f(x)`

> Dos variables distribuidas en el disco unidad  
> `(u,v) ~U(disco unidad)`  
> Entonces v/u -> distribución Cauchy  

> Si queremos otra distribución de Cauchy  
> siempre podremos encontrar un conjunto `Ch` que dos variables distribuidas uniformemente en ese conjunto. Su cociente nos dará la distribución que queramos  

*La división de dos personas nos dará una distribución concreta*


Proposición : Un punto u,v pertenece al conjunto `Ch`
Dado un punto u,v , 
Nosotros necesitamos generar 

- [ ] por qué el área de densidad es la unidad?

Usaremos el método de rechazo, sobre nuestra proposición que detenta si un punto pertenece a `ch`

Necesitamos calcular : m, pi y ps esa sería la función g(x) del método de rechazo que engloba 

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.02.18%203.png)


- generar un punto u,v
- comprobar si pertenece a `ch`
- si pertenece devolvemos su cociente `v/u`

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.07.02%203.png)


EJEMPLO Cauchy estándar
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.08.00%203.png)

> h es la función de densidad  
> su integral (aka área) siempre es la unidad  

han habido otros métodos que usan otras figuras geométricas para delimitar . Para reducir las regiones de rechazo.
- calcular poliedros
- calcular circunferencias

Como la comprobación de la proposición puede ser muy complicada, en el caso de que la función de densidad lo sea.

Mejora

- Definir dos conjuntos:
	- ci: en el interior `ch`
	- cs: que englobe a `ch`
	- Saber si un punto pertenece a una circunferencia es trivial
- Si pertenece a ci -> devolvemos el cociente
- si no pertenece a cs -> rechazamos
- si pertenece a cs y no pertenece a ci -> calculamos la proposición

> a es buena?  
> qué se necesita para cada método?  
>   

## Métodos específicos
### Distribución normal
Muchos fenómenos de la naturaleza siguen esta distribución
Poblaciones, -> campanas de gauss. Gran masa y colas por debajo y por encima.

La distribución normal, tiene dos parámetros: media mu y varianza sigma cuadrado.

La Y~(0,1) Normal(0,1) estándar

`X = mu + Y * sigma`


### Aproximación por método de inversión
> No existe la función de distribución de una normal. Por lo que a priori, no se podría calcular su invertida  
Pero existen buenas aproximaciones


### Aproximación de: Suma de 12 uniformes
Teorema central del límite: **T.C.L**
Si cogemos suficientes variables aleatorias y las sumo, el resultado de esa suma será 

X = (€Xi - suma de sus medias / suma varianza ^ 1/2) ~ N(0,1)

Como sumamos 12 uniformes, su media y varianza será la misma, y será suficiente en dividir entre 12

- X = suma de 12 variables uniformes -6 ~N(0,1)

> Muy eficiente  
> El problema es que dividimos en 12 el periodo  
> sigue siendo una aproximación  

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.27.24%203.png)





### !!! Método exacto: Método Box-Muller
Siendo las variables aleatorias independientes

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.27.40%203.png)

> No me generes de x y de y. Genérame un Radio y un ángulo  

g1(teta) -> 


- generar g1 ángulo con U(0,2π)
- obtener realizar el cambio

- En vez generar coordenadas cartesianas, genero coordenadas polares (ángulos y radios)
- deshago el cambio , coordenadas cartesianas y las devuelvo

La función de distribución de la exponencial
`F(x) ) 1-e^lamnda x/2`

Por último pasamos de las polares a las cartesianas


### Variante de Marsaglia
Intenta mejorarla desde el punto computacional estando funciones trigonométricas. Por que el sin y cos no son eficientes
El resto está en el libro.

### Otros métodos
> Si hemos visto un método exacto por qué ver más?  
En el análisis de  Thomas 2007 compara los rendimientos y precisiones.


## Distribución exponencial
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.42.21%203.png)

Función de densidad y de distribución muy sencillos.
La única operación hay que realizar el `ln`
> Puede ser un poco lento si el ln no está en HW, pero se considera un buen método  

> Disminuimos el periodo según å  

Para una å muy grande generamos una normal estandar

## Distribución de Cauchy
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.42.03%203.png)



## Distribución Beta
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.43.08%203.png)


## Distribución Weibull
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.43.18%203.png)


## OJO: Releer
Relacionadas a la normal standard

- Chi cuadrado
	- n variables , la suma de sus cuadrados es una suma 
	- Grados de libertad == número variables normal standard
- T de student
	- 
- F de Fisher-Snedecor

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.43.39%203.png)

## Chi cuadrado
	- n variables , la suma de sus cuadrados es una suma 
	- Grados de libertad == número variables normal standard

### T de student
Grados de libertad que se usan en la chicuadrado para su construcción

### F de Fisher-Snedecor


# Métodos genéricos para Variables discretas
> Soporte discreto, no implica soporte finito. Puede ser infinito.  

Función de masas `p(x) = P(x=a)`
Función de distribución `F(x) = P(x≤a)`
La función de distribución y de densidad se relacionan mediante un sumatorio (en vez de la integral en el caso de variable continua)
F(a) = 

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-09%20a%20las%2014.49.52%203.png)

Función de distribución son funciones escaladas. Cada salto representa la probabilidad de cada uno de los valores.

- - - -
Siguiente día continuamos 


# a03-05 Tema 3: Generación de variables aleatorias Y Cadenas de markov
- Antonio Jimenez
- 20191016

# Métodos genéricos para variables discretas DISCRETAS
## Métodos genéricos
- inversión
- rechazo
- ~~cociente de uniformes~~ (solo existe en continua)
- composición
- alias

## Método de inversión
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.09.21%203.png)
	- lo único que cambia es la función inversa
	- Generamos un valor aleatorio `u` ~U(0,1)
	- F(x) = x>=u
	- generaremos valores aleatorios 

**Experimento de Bernouilli** : tirar monedas
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.10.39%203.png)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.15.15%203.png)


![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.16.32%203.png)

Mejor preguntar los números más probables, y dejar al final 
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.16.21%203.png)

No es eficiente cuando hay soportes grandes.
Pero es ideal para soportes pequeños

### Método de rechazo
Variable aleatoria `x~Pi`  con función de masa `Pi`
`Y~qi`
Queremos generar una función de masa auxiliar (caso continuo de densidad)  que multiplicada por una constante

Igual que en el caso continuo:
`a` nos indica la eficiencia del método -> 1/a, número de iteraciones para aceptar un valor es `a`

Lo más directo es utilizar como función aux, la uniforme discreta.
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.20.55%203.png)


![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.23.55%203.png)


### Método de Composición
El método arias se basa en este método. Mejor ir directamente a Arias.
### Método de Arias (Walker 1977)
Intentar definir una variable, un conjunto de funciones de masas auxiliares que sea combinación lineal de ellas.
- Hace falta que la variable tenga un **Soporte finito**

Dos cosas a identificar:
- cual es el conjunto de funciones de masa
- Como se expresa esa combinación lineal

Sumatorio van de 1 a n-1 , Siendo n el valor máximo de mi soporte.

Ya sé que los pesos de mi mixtura será igual.

> Lema -> ~Para cualquier función de masa~ , siempre es posible identificar un valor i , donde `pi<1/n-1`  
> para ese i, existe un j != i tal que `pi+pj>1/n1`  

EJEMPLO
Si el soporte es 3, necesitamos dos funciones auxiliares Q1 y Q2 con el mismo peso (1/2)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.36.53%203.png)

Las funciones auxiliares tiene que sumar 1 y se tiene que concentrar en 2 valores

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.43.27%203.png)

Arias es el más eficiente para variables discretas
The square histogram method.

> **Resumen**  
> Soporte pequeño -> Inversión  
> Soporte Grande -> Arias o The square histogram method  


## Métodos específicos
### Binomial
X~Be(p) , dos posibles resultados

x = nº aciertos en n pruebas

Binomial

#### Problema
Cuanto más número de 
No es muy eficiente cuando n es muy grande.

Alternativamente, función recursiva.

Cual es la probabilidad de que x=0 P(X=0) = (1-p)^n

Es el método de la inversión , pero las probabilidades se calculan sobre la marcha.

Cuando n es muy grande se prefiere  calcular el método de arias.

### Geométrica
Relacionada con la Bernouilli y la binomial (acumulada de bernouilli)
`Be(p)`
`Bi(n,p)`

Si queremos saber el nº de fracasos hasta un éxito, la distribución es geométrica. `Ge(p)`

> Obtener la Geométrica, generamos una exponencial y nos quedamos con la parte entera.  
> La relación entre Lambda y P es:   
> ![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-16%20a%20las%2013.58.36%203.png)  


### Poisson
Método de conteo

REPASO
Posson(lambda) ~ `x`= nº de eventos en un intervalo de tiempo ~Poisson(lambda)
Ti = Tiempo que transcurre entre 2 eventos consecutivos ~Exp(Lambda)
Sn = tiempos hasta el suceso (ocurrencia) enésimo ~Gamma(n,Lambda)
> Tiempo hasta que aterrice el undécimo avión.  

> Gamma -> Suma de exponenciales  

#### Primer método
Función recursiva



## Distribuciones Multivariantes
Mi problema esté representado por múltiples variables 
Ejemplo: un piso (habitaciones, precio, zona, superficie, …)

> Independencia entre las variables aleatorias  
> Contraste de independencia.  
> Dos muestras, ¿Tienen dependencia?  

Función de distribución conjunta.
Primer hace falta saber si son independientes o no.

> Si son independientes, la función de distribución es el producto marginal.>   

En aprendizaje automático se encuentra una correlación, se elimina una de las dos, porque están dando la misma información

Markov (métodos genéricos), lo usaremos en sistemas multivariantes donde no conocemos las funciones de distribución


### Descomposición de Cholesky para obtener normal multivariantes
Nuestra matriz de covarianzas es el producto de una matrices y su traspuesta.
µ = Vector de medias
Z = normales estándar independientes 
#### Problema
Calcular la matriz L

## Procesos escolásticos (Importante para la práctica)
### Qué es un proceso de Markov
proceso esto


Siempre estamos rodeados por **Fenómenos aleatorios** (una partida, una variable aleatoria)
Cualquier fenómeno aleatorio lo estudiamos con las variables aleatorias
Necesitamos su 
- soporte S = conjunto de valores
- probabilidades asociadas

Encontrar un semáforo
- {Rojo, Verde, Amarillo}
- {Pr,Pv,Pa}

El soporte puede ser discreto o continuo

#### EJEMPLO de la ruleta
Apostar a un número o color.
En cualquier caso el resultado o soporte son dos: S = {0, 1}
Si pierdo (0) pierdo una ficha
Si gano (1) gano 2 fichas
Dependiendo del juego de azar (número o color) las probabilidades asociadas son distintas.

En vez de pensar en una sola partida, pensamos en una noche.
Eso es un proceso estocástico.
**proceso estocástico**(noche en el casino): muestra la evolución a lo largo del tiempo de un sistema que se va moviendo por distinto estados en función del resultado de ciertos fenómenos aleatorios.


Nuestro proceso estocástico puede tener un soporte S discreto o continuo
- S -> discreto -> el proceso es una cadena
	- la *cadena* de markov hace referencia que su soporte es discreto
- S -> Continuo

El TIEMPO: Conjunto de índices o instantes
- discreto
	- después de cada partida
- continuo
	- en cualquier tiempo

EJEMPLO: Noche en el casino
- Si quiero saber el dinero después de cada partida, analizamos el tiempo discreto
- Si quiero saber el dinero en cualquier instante: 7:30, 14:00 -> hablaremos en tiempo continuo
	- te pilla en medio de un proceso y no sabes exactamente donde

Todos los procesos estocásticos pueden ser de uno de esos 4 grupos.

- **PROPIEDAD DE MARKOV**:  
	- modo intuitivo : el futuro depende del presente pero no del pasado


> el futuro depende del presente pero no del pasado  
> Depende únicamente del estado actual  
> No de los estados que he pasado previamente  
> Por tanto estos procesos no tienen tendencia  

#### CMTiempoDiscreto
Que necesitamos matemáticamente hablando para modelizar una CM
- S : Conjunto “discreto” de estados
- P=(Pij) : Una matriz p de probabilidades de transición. Pueden haber muchos ceros.
	- probabilidad de pasar del estado i al j

#### CMTiempoContinuo
Que necesitamos matemáticamente hablando para modelizar una CMTC
- `S` : Conjunto “discreto” de estados
-  `P=(Pij)` : matriz p de probabilidades de transición
- `Ti` = Tiempo de permanencia en el estado
	- tienen carácter aleatorio
	- se asumen que tienen cierta distribución ~ Exponencial
		- con tasa `vi` que depende del estado en el que estamos
		- vi : Tasa de permanencia

Comportamiento 
- transitorio
	- en el caso discreto: 
	- nº de fichas en un momento dado
- estacionario
	- En qué estado me encuentro o nº de partidas 
	- Dónde estaría si el tiempo tiende a infinito

Como se analizan estos comportamientos?
en caso discreto es sencillo

Probabilidad de pasar de un estado i a un estado n -> se coge la matriz de probabilidad se eleva a n. Y ya tenemos las probabilidades tras n partidas.

Convergencia de matrices P^infinito -> converge a -> P

En tiempo continuo
Planteamiento y resolución de sistemas de ecuaciones diferenciales
Se usa en estudios de trayectorias.

Plantear las ecuaciones diferenciales es sencillo -> Chapman-Kolmogorov
Resolver esos sistemas es complicado

> Distribución límite o estacionaria  
> Probabilidad de encontrarnos en el estado cuando tiende a infinito  
> Ecuaciones lineales  







### Cómo simular cadenas de markov
Hace falta entender qué son las cadenas de markov


# a03-06 Tema 3: Generación de variables aleatorias Y Cadenas de Markov
- Antonio Jimenez
- 20191023
- Cap3-MUIA-GenVarAleat. Pag 53


## 4. Procesos estocásticos (De Markov)
> Cadena significa que el conjunto de estados es discreto  

- CMTiempoDiscreto
	- **S** - Conjunto de estados
	- **P** - Matriz de probabilidades de transición
- CMTiempoContinuo
	- **S** - Conjunto de estados
	- **P** - Matriz de probabilidades de transición
	- Ti ~ Exp(vi) 
		- **vi** = Tasa de permanencia y que habría que identificar

- Comportamiento
	- transitorio
		- en un momento determinado
		- En n iteraciones de una cadena de markov -> P^Infinito
	- estacionario (a largo plazo)
		- si `t -> infinito`
		- Se puede estudiar la convergencia cuando P^infinito

> Cuando lo utilicemos para generar distribuciones multivariantes discretas, hablaremos de cadenas. Si son continuas, habrá que generalizar a procesos estocásticos.  

La matriz de probabilidad de transición
Depende de la fila y generar una distribución de esa fila.

- Problema de eficiencia
	- Su diagonal 
	- Me intenta simular los instantes 

Vamos a modelizar el número de apuestas hasta que abandono un estado

¿Cómo hacerlo más eficiente?
- `Ts` = número de iteraciones (apuestas, instantes de tiempo discretos) / apuestas hasta que abandono el estado i . ~ Ge(Pss)
	- La distribución geométrica
		- con dos estados, quedarnos y abandonar
		- Probabilidad de éxito -> `Pii`
		- Probabilidad de fracaso -> `1 - Pii`
Hay que reconstruir la matriz , con la diagonal a 0’s, no nos interesa estudiar las simulaciones cuando de un estado se queda en sí mismo.
Garantizando que en cada estado se cambia de estado

Las tabla de arias se generan según las vamos necesitando. Porque hay estados que puede que no se visiten.

### CM En tiempo continuo
Cuando se modelizan, la diagonal ya es 0. No 
> En este ejemplo, se debe analizar las propiedades y conceptos de las distribuciones exponenciales  


## Métodos basados en cadenas de Markov
Distribución 
Identificar el Proceso escolástico o cadena de markov.
cuya distribución estacionaria (a largo plazo, `t -> infinito`) que sea la distribución (multivariante, compleja) conjunta de la que queramos generar valores.

Si la distribución es
- discreta -> cadena
- continua -> proceso estocástico

## El muestreador de Gibbs
Usado especialmente en **Inferencia Bayesiana**
 
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2013.38.32%203.png)

Distribuciones marginales de P1 y P2
`P(X=0) = p1 + p3`
`P(X=1) = p2 + p4`
`P(Y=0) = p1 + p2`
`P(Y=1) = p3 + p4`

Probabilidades condicionadas:
> Condicionas aquello a que conoces  
`P(X=0|Y=0) = p1/p1+p2`

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2013.42.12%203.png)


![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2013.42.33%203.png)


### Generalizamos
Densidadas condicionadas, por lo general, no será muy complicado, porque las calculamos suponiendo que nuestra variable es la única y está condicionada al resto de variables que asumiremos que son constantes.
Quedándonos únicamente una única variable

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2013.46.59%203.png)


EJEMPLO
Función de densidad
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2013.48.04%203.png)


Distribuciones condicionadas

Distribución (X1 | X2) ~Exp (lambda=1+x^2+2)
Luego habrá que multiplicar por las variables que tenga por el camino

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2013.55.11%203.png)

Será más eficiente, cuantas más variables, porque al calcular las condicionadas consideramos solo una variable y el resto constantes. Para cada variable.


## Algoritmo de Metropolis-Hastings (***MH***)
Es mucho más sencillo aplicarlo que el muestreador de Giggs

> El muestreador de Gibbs exige disponer de algoritmos eficientes para generar de las distribuciones marginales, condicionadas por las restantes variables, lo que no es siempre posible conseguir.  
> El algoritmo de Metropolis-Hastings (MH) requiere menos estructura en el problema, aunque típicamente, pero no siempre, será más lento. Sólo necesitamos poder:  
> •evaluar puntualmente la distribución objetivo, salvo una constante, y •generar observaciones candidatas de una distribución de prueba q(·, ·), que  
> satisfaga ciertas condiciones técnicas.  
> Entonces generamos una observación candidata y actualizamos el estado según ciertas probabilidades de rechazo de los candidatos.  


## Conclusiones
Librerías y páginas web donde están implementadas y probadas, para generar variables aleatorias
- Libro Recetas numéricas (C y FORTRAN)
	- Probadas y optimizadas
- SW estadístico R -> 
	- Aprendizaje automático - estadística multivariante
- EXTEND
	- simulación de sucesos discretos
- netlib
- Devroye 
	- winrand
- Statlib

Muchas veces se utiliza el método de inversión, aunque sea menos eficiente, porque producen menor varianza.

FIN.

# a03-06 Tema 4: Simulación de sucesos discretos SSD
- Antonio Jimenez
- 20191023
- Cap4-MUIA-SimSucDiscretos. Pag 0

## Índice
1. Conceptos básicos de la SSD
2. SSD de sistemas de espera complejos
	- Modelo G/G/1
	- Red de colas
	- Tesis doctora de Marketing Digital
3. SSD de un modelo de inventario probabilístico
4. Software de SSD
5. Referencias

## Conceptos básicos de la SSD
- Modelos continuos
	- procesos estocásticos evolucionan de forma continua en el tiempo.
	- Ejemplo CMTC
	- Estudio de dinámica de la población mundial, Trayectorias de aerolínea
	- El estudio transitorio, está llevado a ecuaciones diferenciales.
		- para el estudio de trayectorias de aeronaves en el tiempo
- **Modelos discretos**
	- Evolucionan de forma discreta en el tiempo
	- solo cambia en determinados **eventos** o **sucesos**
		- número de clientes hay en él, solo cambia cuando llega o se va un cliente

- t = Variable tiempo de simulación
- contadores = cuantas veces ha sucedi
- estado = subjconjunto de 
- actividades internas (endógeno) o externo (exógeno)
	- finalización de un servicio -> endógeno
	- llegada de un nuevo cliente -> exógeno

### Tipos Mecanismo de Reloj
- sincronía , orientada a intervalos. Se usa una rodaja de tiempo FIJA.
	- no la usaremos por sus inconvenientes
		- **se pierde información sobre el orden y los instantes que suceden en el tiempo**
	- Cogemos rodajas de tiempo `L`, avanzamos el reloj de simulación , hasta un tiempo posterior L 
		- cada instante L actualizamos 
		- el inconveniente es el valor que le demos a la `L`,
			- puede ser muy grande, en el que sucedan
				- Se asume 
			- muy pequeño
				- es ineficiente
- Simulación asíncrona
	- en vez de avanzar el reloj en intervalos fijos, avanzaremos el tiempo suficiente hasta el siguiente evento
	- Se ajusta al tipo de simulaciones que queremos realizar

Problema a tener en cuenta
Si avanzamos el tiempo hasta el siguiente evento, necesitamos 
- **Lista** de instantes en los que sucederán los próximos eventos
	- los distintos tipos de eventos
	- Estructura de tiempos exactos
		- habrá que actualizarla de forma automática, según se vayan sucediendo los eventos
	- ~Tiempo que transcurre entre eventos consecutivos~ 
		- determinísticos
		- probabilísticos

- Referencias 
	- Banks 2000: orientado a lectores basados
	- Banks 1998: Prácticos y novedosos SSD

¿**Qué tipos de sistemas podremos simular con SSD**?
De Eventos o sucesos.
problemas SISTEMAS DE ESPERA

## SSD de sistema de espera complejos : Modelo G/G/1
> Simulación de sucesos discretos.  

- **Sistema de espera**: llegan clientes a demandar nuestro servicio. Cuando llega un cliente tendrá que esperar en una o más colas.

Clientes de población infinita -> COLA -> Servidor -> Se van
- Proceso de llegada de carácter aleatorio.
	- llegan en lote? o de uno en uno?
- Cola: ¿Qué capacidad de espera?
- discriminación de 
	- FIFO, prioridades?
- N Servidores
	- idénticos o no
	- ¿A qué ritmo trabajan?
	- ¿Cola única y una por cada servidor?
	- Proceso de servicio aleatorio

Si los servidores estuvieran interconectados serían Red de colas.
- Exponencial, Markovianos: 
	- si se cumplen las siguientes condiciones, las fórmulas serán cerrados
	- Proceso de llegada individual -> P.Poisson ~homogéneo~
	- Cola -> FIJO
	- Tiempo de servicio -> Exp(µ) e idéntico para todos los servidores
		-  el tiempo es constante en el tiempo
		- e independiente del estado del sistema

El 99% de los casos reales, no se cumplen. 
El 1% son los sistemas informáticos, sí cumplen estas condiciones, porque no se cansan, son idénticos, etc.
> Si se cumpliesen estas condiciones NO HACE FALTA SIMULACIÓN  

El Estado del sistema está definido por el nº de clientes
Los eventos serán: Llegada de un cliente | Finalización de un servicio

Podemos preparar

En un instante `T-> instante en el que no permitimos más entradas al sistema`. Horizonte de simulación
La simulación finalizará cuando el sistema quede vacío de clientes. 
`Tp` es el delta desde T hasta que finaliza la simulación. Carácter aleatorio

### ¿Qué vamos a calcular?
1. Tiempo medio en el sistema
2. Tiempo medio en la cola
`n` es la variable de estado
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2014.41.51%203.png)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2014.45.36%205.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2014.52.43%205.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2014.52.56%205.png)





# a03-07 Tema 4: Simulación de sucesos discretos

- Antonio Jimenez
- 20191030
- `Tema 04 - Simulación de sucesos discretos/Cap4-MUIA-SimSucDiscretos.pdf`

Array de eventos con el tiempo en el que deberían ser ejecutados.
Cada vez que se consulta uno, se reemplaza por el siguiente tiempo de ese evento.

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2014.45.36%206.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2014.52.43%206.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-23%20a%20las%2014.52.56%206.png)

`Lista.tLL = 1000`  identifica que no hay personas en la cola.


# Red de colas
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2013.41.18%203.png)
En este ejemplo hay 4 eventos. 3 eventos de entrada y 1 de salida.
No son 6 eventos, porque la salida del nodo 1 es en realidad la entrada del nodo 2 y del nodo 3 y así sucesivamente.
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2013.30.37%203.png)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2013.30.50%203.png)
`X` :Tiempos de dos entradas consecutivas de Poisson(lambda) es el tiempo exponencial del mismo parámetro.
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2013.38.12%203.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2013.38.20%203.png)
El tiempo medio del sistema será :
Tiempo medio del nodo 1 + tiempo medio del nodo 3 (porque todos los clientes pasan por ahí) + tiempo medio del nodo 2 * Probabilidad(pasar del nodo 2)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2013.43.05%203.png)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2013.44.13%203.png)
Aquí se incluye la llegada_cliente del nodo2 o nodo3
“” Sería optimizable, modificando únicamente el Lista.tsx “”

# SSD de un modelo de inventario probabilístico
Método de inventario probabilístico. Problema típico de investigación operativa.
> Modelos de inventario con fórmulas cerradas tienen demasiadas hipótesis y restricciones para ajustarlo a problemas reales.  

## Sistema de almacén de un único producto.
1. Somos dueños de un almacén con un único **producto**.
2. Los **clientes** vienen a comprar un producto(s) con un proceso de llegadas -> normalmente `Poisson`
	1. los clientes tendrán cierta demanda
		1. probabilidad discreta
3. Les vendo los productos a un **precio**
4. Le haremos pedidos a un Proveedor y tendrá un **coste**
	1. coste fijo K (coste administrativo)
	2. coste al nº de artículos que yo pida
		1. Los proveedores hacen **descuento** por grandes pedidos.
5. Los pedidos tardan en llegar. `L`: **tiempo líder** ~
6. `h`: **Coste de almacenamiento**. Coste de mantenimiento del almacén
	1. vamos a considerar que el coste es por unidad almacenada y unidad de tiempo

Decisiones que toma el dueño del almacén:
Consideramos que el precio de venta y el coste del proveedor ya están negociadas/definidas.
- **Política de pedidos**: Cuándo pido y nº de artículos
	- Aperiódicas
		- Pido cantidades distintas cuando el almacén decae cierta cantidad.
		- p = nivel por debajo se dispara hacer el pedido
		- P = valor de referencia de cantidades a pedir
			- cantidades a pedir será la Diferencia entre P y el nivel actual del inventario
	- Periódicos
		- En un mismo intervalo fijo de tiempo, pido cantidades distintas

### ¿ Cuales son los objetivos ?
Los valores a simular serán estos 3.
- `MAX(beneficio)`
- `MAX(Calidad del servicio)` para (`min(pérdida de clientes)`)
	- % clientes satisfechos
	- % del tiempo del almacén a 0 (vacío)
		- min(tiempo del almacén vacío)

## EJEMPLO
`r = precio de venta`

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.14.52%203.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.19.33%203.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.19.41%203.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.19.49%20copia%203.png)

> Queremos optimizar la combinación de  `p` (trigger a realizar pedido) y `P` (valor de referencia a pedir)  

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.27.30%203.png)

Beneficio será: `R - H - C`

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.30.38%203.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.31.36%203.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.32.18%203.png)
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.32.39%203.png)


Con la política de pedidos actual (p=30 y P100), han habido muchos intervalos con el almacén vacío.
139 clientes insatisfechos con 289 ventas perdidas.
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.42.50%203.png)
En la práctica los procesos de llegada serán Poisson no homogéneos

> Se suele dejar un parámetro fijo (100) y jugamos con el otro parámetro  



![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.48.33%203.png)

Dejamos fijo p=30 y jugamos con P
Para p=30, el P debería ser 317.
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.48.52%203.png)

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-10-30%20a%20las%2014.53.39%203.png)

Página 42 -

## SW SSD

# a03-08 Tema 5: Simulación y optimización. Introducción 

- Antonio Jimenez
- 20191118
- `Tema 05 - Simulación y optimización/Cap5-MUIA-Introducción.pdf`

## Índice
1. Programación matemática
	1. Optimización 
2. Métodos de solución exactos 
3. Heurísticas
4. Heurísticas vs. metaheurísticas
5. Clasificación de metaheurísticas 


## 1. Programación matemática
2ª Guerra mundial, grupos multidisciplinares. Asignación de recursos y estratégicos y tácticos.

Situación de radares en la costa británica para maximizar el área la detección de aviones nazis.

- **Programación lineal (PL)**: Una función matemática es lineal cuando sigue este esquema: `ax1 + bx2 + cx3 ...`
	- Podemos resolverlos mediante el método de simplex, siempre que seamos capaces de modelizar el problema como una ecuación lineal.

Una de los éxitos es que la PL es una de las herramientas más utilizadas dentro de la IO.


### Problema de optimización
- **Variables de decisión**:  cuyos valores óptimos queremos conocer.
	Qué cantidad debo producir de cada uno de los modelos de coche.
- **Función objetivo**:  Función matemática y lineal definida sobre las variables de decisión. Se utiliza para identificar cuál es la mejor combinación de valores de nuestras variables de decisión . (max o min)
- **Restricciones**: Limitaciones dentro de nuestro problema y se tienen que satisfacer. Limitaciones prácticas en nuestro problema.
- **Solución óptima**: La solución óptima debe satisfacer todas las restricciones


### Cómo construir un modelo de optimización
### Proceso de formulación de un modelo lineal

1. **Determinar las variables de decisión y representarlas algebraicamente**
> Las variables de decisión son los factores sujetos a cambios cuyos valores pueden variar, o al menos hacerlo dentro de unos ciertos límites, bajo el control del decisor o modelizador.   

En general, las representaremos mediante *x**j*, *j*= 1,…,*n*, y en notación vectorial como **x**= (*x**1*,…,*x**n*). La solución óptima se indica con **x***= (*x**1****,…,*x**n****). 

Variables Continuas vs. Discretas (Programación Lineal Entera) 
PROGRAMACIÓN LINEAL CONTINUA - PLC
PROGRAMACIÓN LINEAL DISCRETA/ENTERA - PLE
O MIXTA

2. **Formular las restricciones**
Pueden ser inecuaciones : <= , >= o ecuaciones =

- `g_i(x) <= b` -> restricciones de **disponibilidad**
	- por ejemplo: el número de personas trabajando no puede superar 10
- `gi(x) >= b` -> restricciones de **demanda**
	- por ejemplo: vehículos a producir, al menos de 300 unidades

- Soluciones factibles: verifica todas y cada una de las restricciones del problema.
	- Conjunto de región factible `(F)`

> Las restricciones, expresadas como ecuaciones o inecuaciones lineales en las variables de decisión, generalmente representan la limitación en la disponibilidad de algún recurso.  


3. **Formular la función objetivo**
> La función objetivo a optimizar será una función lineal en las variables de deci- sión. De manera genérica podemos decir que representa los deseos del decisor de maximizar un beneficio o minimizar un coste. Su forma matemática es.  

> Más de un objetivo simultáneo à Programación Lineal Multiobjetivo   

`Z` es el valor en la función objetivo.
`max z = f(x)`

Modelo algebraico de una modelo lineal:
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-11-18%20a%20las%2015.32.04%203.png)



## Ejemplos de modernización de Programación Lineal
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-11-18%20a%20las%2015.32.31%203.png)

x1, x2, x3 = Negra, Rubia, Sin Alcohol
> `max z = 4x_1 + 7x_2 + 3x_3`  
> `2x_1 + x_2 + 2x_3 <= 30`  
> `x_1 + 2x_2 + 2x_3 <= 45`  
> `x_i >= 0`  


![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-11-18%20a%20las%2015.47.39%203.png)

Nota que sacaré en la primera asignatura:
max z = `5 + (x1-12)/(20-12)` +
`5 + (x2-20)/(45-20)` +
`5 + (x3-25)/(60-25)` +
`5 + (x4-18)/(30-18)` 
/
4

> Si no se pueden verificar todas las restricciones -> el problema es infactible  
> Que exista una solución óptima - única  
> Que existan soluciones óptimas alternativas  

> No acotado (max z -> \infinite) (min z -> - \infinite)  

## Métodos de solución exactos
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-11-18%20a%20las%2016.15.13%203.png)

Estos son los métodos de solución exactos para problemas de optimización.

### Método de simplex

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-11-18%20a%20las%2016.15.48%203.png)

En programación lineal si existe una solución factible, el segmento que los une está contenido dentro del conjunto.
Los vértices son puntos extremos.
La solución óptima será uno de los puntos extremos.

Conjunto ~no~ convexo : el segmento no está contenido dentro del conjunto.

El simplex realizará un proceso de búsqueda entre los puntos extremos.
No necesitará comprobar todos los puntos. Se detiene al alcanzar el óptimo.

### Multiobjetivo

![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-11-18%20a%20las%2016.36.40%203.png)

- Solución eficiente, pareto óptima o no dominada: Es imposible encontrar cualquier solución 
![](a03%20Me%CC%81todos%20de%20simulacio%CC%81n/Captura%20de%20pantalla%202019-11-18%20a%20las%2016.34.28%203.png)

Solución: 
- Satisfaciente: Solución **eficiente** que representa las preferencias del decisor
	- se aproxima al ideal
- Aproximación del conjunto eficiente

## Heurísticas
Surgieron para dar solución al problema de transporte. Antes de las heurísticas se enviaban los problemas a supercomputadores en estados unidos.

Problemas de optimización combinatorios.
Procedimientos aproximados (no nos garantizan la solución eficiente). Con cierta probabilidad.
Ganamos eficiencia en tiempo de cómputo, pero perdemos un poco de precisión.

### Ejemplos de heurísticas
Problemas de redes, de transporte, flujo de redes.
Soluciones enfocadas a problemas concretos en vez de soluciones generales (acotación, …).

Se desarrollan para resolver problemas concretos.
Problemas que cuando aumentan su dimensión son “imposibles” de resolve en un tiempo razonable

### Problemas de transporte
Problema de Minimización entero.
Algoritmos: MEN (Esquna noroeste), MAV (vogue), MODI

### Problemas de asignación
Determinar costes de asignación. Variables binarias, asignación 1 asociado, 0 no asociado. (se podría resolver con el método de Ramificación o acotación binaria)
Algoritmo: Método Húngaro


### Problemas de secuenciación de control en redes
Algoritmos: CPM (determinista) y PERT (ß tiempo que tardan en resolverse las tareas).

### Camino de longitud mínima y máxima
Algoritmos: **Dijkstra**, Floyd

### Flujo en redes
Algoritmo de etiquetación de Ford-Fulkerson

### Árbol mínimo de máximo alcance
Redes. Conectar todos los nodos con mínimo de coste.
Algoritmo de **Prim**.

### Problemas de algunas heurísticas:
- no suelen garantizar la solución óptima
- desarrollados ad hoc para problemas concretos
- quedan atrapados en óptimos locales

## Metaheurística
1986 por **Glover** , investigador que más pronto y más MH ha propuesto. Siendo la primera MH la búsqueda tabú.
Meta (más allá) y heurística.

Obtención en tiempo razonable de una solución eficiente y satisfaciente. Buenas soluciones (satisfacientes) con un coste computacional razonable, pero sin garantizar la optimalidad.

**Aplicables a un gran número de problemas**

Su objetivo es **evitar quedarse atrapados en óptimos locales.**

Referencia a mecanismos de optimización de la naturaleza.

Hay que analizar la convergencia probabilística.
Recocido simulado convergencia con probabilidad 1.

- - - -
> Las metaheurísticas son una clase de métodos aproximados de optimización combinatoria que proporcionan **un marco general para crear algoritmos híbridos combinando diferentes conceptos derivados de la IA, la evolución biológica y los mecanismos estadísticos.**   
> La **evolución** de las metaheurísticas ha tenido un comportamiento exponencial en los últimos 35 años, resolviéndose problemas que tiempo atrás parecían inabordables.   
> En época reciente se han extendido los métodos de optimización como **hiperheurísticas**que son procedimientos de búsqueda de muy alto nivel que se sitúan por encima de las metaheurísticas.   
> Elevan la generalidad de las metaheurísticas y se encargan de seleccionar, en cada momento y para cada problema, el método heurístico o metaheurístico más adecuado. Esta selección se hace en función del tiempo que tarda cada algoritmo o en función de la calidad de la solución que alcanza cada uno de ellos.   

Las hiperheurísticas pueden identificar qué tipo de heurísticas funciona.
Distancias mínimas -> MH constructivas como colonia de hormigas funciona muy bien.


PAG.22

Recocido simulado 