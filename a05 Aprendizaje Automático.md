# a05 Aprendizaje Automático

# a05-02 Performance Evaluation

Pedro Larrañaga, Concha Bielza

# Bondad de un clasificador
El rendimiento de un clasificador antes nuevos ejemplos
> Estimación “honesta”  


Información de partida
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2015.13.05%202.png)

## Regiones de decisión
- Región de decisión
	- 
- Frontera de decisión
	- Nos interesan fronteras muy flexibles
	- Las redes bayesianas generan hiperplanos de líneas rectas
	- Una red con un par de capas ocultas, crean fronteras de “cualquier” flexibilidad. (Curvas)

## Función de Pérdida / Riesgo

Función de pérdida 0 o 1 , si fallas pagas una unidad, si aciertas no pagas 

- Riesgo esperado: valor atribuible para un clasificador y se calcula como una integral
	- Similar a una esperanza matemática
	- `*R*(φ) = 􏰆 *L*(*c*, φ(**x**))d*p*(**x**, *c*)`
- Función empírica del riesgo
	- Asume que es uniforme para todos los puntos
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2015.20.21%202.png)


## Clasificación binaria
> ¿Como calcular la bondad de un clasificador?  

Tabla de incontingencia
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2015.23.17%202.png)

TP: true positives
FP: false positives
FN: false negatives
TN: true negatives 

Son valores enteros

Medidas de mérito


![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2015.24.44%202.png)

* Accuracy 
* Sensitivity or Recall 
* Specificity 
* Positive predictive value or Precision 
* Negative predictive value
* *F*1 -measure : Están jugando con varios valores de la tabla. EC1, recuperación de información. 
	* Media armónica entre la precisión y el recall.
	* F1 = 1 / 1/2(1/Prec + 1/Rec) = 2/ ((Prec+Rec)/Prec*Rec)
* Cohen’s kappa statistic : 
	* Cuanto más cerca de 0 , más cerca estaremos de la hipótesis de independencia

> Media armónica: Inverso de la media aritmética de los inversos  

> Hipótesis de independencia  
> P(C>0) <->P(Fi(x)>0)  

> Lo normal es utilizar una medida  

Puedo entrenar un clasificado para maximizar un objetivo (cohen o accuracy o ….)

## Matriz de coste
En vez de buscar maximizar un objetivo , no es equivalente a minimizar el coste total.
Solo es equivalente y la función de pérdida es 0-1
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2015.38.19%202.png)


## Brier Score
Clasificadores probabilísticos
> Es un score de calibración  
Todas las probabilidades las llevan a 0 o a 1 -> Clasificador bien calibrado

Compara este clasificador con lo ideal.
- 0 está muy bien
- 2 es lo peor

Piramidal es + , se mide la distancia al punto euclideo (1, 0)
Interneurona es - , se mide la distancia al punto euclideo (0, 1)

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2015.41.37%202.png)


## Curva Roc
Se tiene en cuenta `FPR: False Positive Rate` y `TPR: True Positive Rate` al unísono.

![](a05%20Aprendizaje%20Automa%CC%81tico/Foto%2026%20sept%202019%20154851%202.jpg)
Exijo como mínimo 0.50 (Última columna)
+,+,-,+,
FPR -> cuando exijo 0.5 ; TPR -> 0.5
Si voy moviendo el umbral, ir moviendo desde 0.21 (el más pequeño) hasta el más alto.

La curva roc , en realidad es una polígona, y es la unión de todos los puntos que hemos conseguido moviendo el umbral.

## Dominancia de pareto -> Multiobjetivo
B domina a A, porque B es mejor en los dos criterios TPR y FPR
C no domina ni a B ni a A
Cuantos más criterios tenga, el **Frente de Pareto** será muy grande
> No soy el mejor , y nadie es mejor que yo  
No hay nadie que me domine -> pertenece al frente de pareto

## Algoritmo ROC análisis en una clasificación binaria
“tresshold?” aka th aka t
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2016.01.33%202.png)


Una cosa es la curva, pero lo que se utiliza es el área bajo la curva
Cuanto más area tiene, mejor es el clasificador


![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2016.03.43%202.png)

Ranki es la posición del positivo, ordenados de probabilidad de mayor a menor.
Lo ideal sería que la suma i - ranki sea 0, para que AUC(fi) sea 1

### Para problemas multi clase
hablamos de volumen

## Métodos de Estimación honesta
- Performance estimation
	- Single resampling
	- Multiple resampling

- Repetir y coger una muestra de tamaño n 1 millón de veces
	- Calculo  el Parámetro poblacional mu, media muestral 0.18
	- Hago un histograma
	- 

> Estimador insesgado (sin sesgo), es perfecto  
> La diferencia Lo que esperas estimar y la esperanza es 0  

Que el estimador tenga poca variabilidad. Varianza mínima entre todos los  insesgados“Frontera de tramel round” 
Estimador eficiente

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2016.22.29%202.png)

### Hold-out
	- Hago una partición de la muestra : Selección aleatoria , sin reemplazamiento.
		- Para entrenar
		- Para testear
> no es una estrategia muy inteligente  

### k-fold cross-validation (Kurtz, 1948)
- Entreno con toda la muestra
- Para validar:
	- Separamos la muestra en k piezas
	- Los clasificadores intermedios, 
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2016.27.32%202.png)
> Si k= 10 -> La intersección entre los clasificadores es del 80% (K-2)  

> El clasificador   
Estimaciones insesgadas, si k es muy alto 

> Si k coincide con el tamaño de la muestra y solo testeamos  
> Mucha variabilidad, porque el resultado es 100 o 0  
> Leave-one out cross validation  

Stratified
Cuando las bases de datos están dsevalanceadas, respecto a la variable clase
La clasificación se hará de forma estratificada, que en cada rodaja se mantenga el nivel de FP FN

El resultado del clasificador Acc = 

> Hoy en día es muy recomendado el k-fold para que tu clasificador sea entrenado con tu muestra entera  

## Multiple resampling-based estimation methods
### Repeated hold-out
Es mejor que que el hold out, porque no se han desperdiciado casos

### k-fold cross validation
10x10 cross validation , repetir 10 veces 
Dietterich (vaca sagrada) 5x2 k-fold no se usa

### Estimación bootstrap
Extracciones con reemplazamiento
Cada muestra tendrá el mismo tamaño que la muestra original
Hasta conseguir mi muestra de tamaño mil
Problemas:
- Probabilidad de que todos sean el mismo: `N(1/N)**N`
- Otro problema menos probable es que la muestra de test sean de la misma clase (todos + o todos negativos)

La probabilidad de no coger un elemento de la muestra es 1/e ~= 0.368
Efron, vaca sagrada
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2016.46.56%202.png)

La estimación con bootstrap no es insesgada, pero sí lo es en el límite. Asintóticamente no sesgada.
Lo bueno que tiene una varianza muy pequeña, en muestras pequeñas va bien

### Comparar clasificadores desde un punto de vista de test de hipótesis
Comparamos los resultados uno o varios datasteis y uno o varios clasificadores en un test de hipótesis

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2016.51.24%202.png)

Veremos el paired samples y el friedman test

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2016.52.18%202.png)

El p-valor bajo -> se rechaza la hipótesis
“El p-valor debe 0.05 suele ser significativo y se rechaza la hipótesis”
Generalmente se hace con el accuracy 

> no está bien hecho del todo  
> se critica porque el k-fold -2 son dependientes  

Por eso se corrige la no independencia

### Lo más genérico con 1 base de datos
Tengo 6 clasificadores y 1 única base de datos
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-09-26%20a%20las%2016.56.43%202.png)

Test de Nemenyi para encontrar 

### Lo más genérico con varias bases de datos
**Familywise** error, probabilidad de encontrar al menos un ti po de error in cualquier comparación
Corrección Bonferroni

- [ ] Sentirnos libres para enviar un correo a concha y pedro si estamos interesados en participar en minería d e datos con problemas reales. 1 o dos becas. O hacer un doctorado en este tipo de cosas.




# a05-03 Arboles de clasificación - 2.5 Classification trees

## Introducción
Concha Bielza, Pedro Larrañaga

    x1 … xn | c
1
2
3

Variables | Predicción de clase (está enfermo, no)

Dos grandes grupos de clasificación
- -> No probabilísticos -> Los que te dan directamente la etiqueta
	- KNN : K vecinos más próximos
		- decides según lo que te dicen los k vecinos
		- buscamos casos similares
	- Árboles
	- Redes neuronales
	- ** soporte
- -> Te dan la etiqueta y la distribución. Es mucho más rico y normalmente te quedas con la probabilidad más alta
	- Redes bayesianas
	- Regresión logística

> Cuando no son etiquetas y son números reales, no es un problema de clasificación, sino de regresión  

### ¿Qué es un árbol de clasificación?
OJO! Los árboles de decisión -> es otra cosa en Sistemas de ayuda a la decisión. Aunque a veces se utilice el término incorrectamente

- Muy usado y popular
- aproxima función discreta-valor. La función aprendida es representada por un árbol de decisión
- Robusto a datos con ruido
- Representa una disjunction of conjunctions de constantes en el atributo valor de instancias
	- División de opciones. Colección de ORS con ANDS
		- *(Outlook=Sunny*∧ *Humidity=Normal)*∨ *(Outlook=Overcast)*
∨ *(Outlook=Rain*∧ *Wind=Weak)*
- árbol Parendido puede ser re representado como colecciones de reglas if-then (intuitivo)
- 

### Representación como un árbol
- cada nodo es una pregunta
- cada rama es un valor que toma la variable
- el nodo hoja son etiquetas de predicción
- 

### Ejemplo: Jugar al tenis
Outlook=Sunny, temperature=Hot,, humidity=High
Son variables continuas discretizables
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2015.21.47%202.png)

> XAI -> Explainable AI  
Más garantías de que sea segura, justa, entender lo que dice el modelo para justificarlo.

> FSS -> Feature Subset selection  
Selección de datos (variables) **relevantes**, no redundantes.
Queremos conseguir un conjunto pequeño de variables que describa con precisión.
Jugar a quitar y poner
3 métodos:
- filtrado
- montura (wrapper)
- embedded

- División de opciones. Colección de ORS con ANDS
		- *(Outlook=Sunny*∧ *Humidity=Normal)*∨ *(Outlook=Overcast)*
∨ *(Outlook=Rain*∧ *Wind=Weak)*

Los aboles se pueden representar como una disjunction de conjuctions 

Navaja de okham, principio de parsimonia. Lo más simple es mejor.

### Generación de reglas
Los aboles se pueden representar como una disjunction de conjuctions 

**Inducción de reglas**
Del árbol pasamos a las reglas
De las reglas, es muy difícil pasar al árbol

> Determinar las fronteras de decision que nos ofrecen los árboles  

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2015.33.28%202.png)
> Cada nodo es una frontera (división) paralela a los ejes  

árboles oblicuos, preguntan por diferentes variables a la vez. [No lo vemos]
Nosotros vamos a preguntar por una variable cada vez  (> o <), por lo que nos creará líneas divisoras paralelas a los ejes cardinales.

Classification trees: salidas discretas
	`CLS, ID3, C4.5, ID4, ID5, C4.8, C5.0`
Árboles de regresión
	`CART, M5, M5P == M5’`

## Índice


## Algoritmo básico ID3
ID3 -> dicotómico iterativo [Quinlan, 1986]
Particionan el dataset anterior en grupos por ramas

- Based on CLS (Concept Learning Systems) algorithm [Hunt et al., 1966], that only used binary attributes
- Greedy search strategy through the space of all possible classification trees Construct the tree top-down, asking: which attribute should be tested at the root?
- Answer by evaluating each attribute to determine how well it alone classifies training examples
- Best attribute is selected, a descendant of the root is created for each value of this attribute and the training examples are sorted to the appropriate descendant
- Repeat this process using the examples associated with each descendant node to select the best attribute at that point in the tree (always forward, searching among the not yet used attributes in this path)
- Stop when the tree correctly classifies the examples or when all attributes have been used
- Label each leaf node with the class of the examples

> Ganancia de información === Información mutua  
> Entropía de la clase, menos la entropía de la clse cuando conocemos Xi  
> Nos interesa que sea muy grande, porque implica que los valores es muy grande  

- et step: how to select which attribute to test at each node in the tree?
- We would like the most useful for classifying examples; that separates well the examples
- ID3 chooses mutual information as a measure of the worth of an attribute (maximize)
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2015.44.08%202.png)
- Expected reduction in entropy (uncertainty), caused by partitioning examples according to this attribute

### Cómo elegir un nodo raíz
- Fijo esta variable.
	- ¿Qué pasa cuando vale 0 y cuando vale 1 ?
- Máxima ganancia de valor, debe ir al principio del árbol, porque selecciona más 

## Pasos para construir el árbol a partir de los datos
> !!! TODO: hacer los cálculos de las transparencias en casa.  

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2015.47.11%202.png)

1. Calcular la entropía de la clase para elegir el nodo raíz
	1. lo aplicamos para cada una de las variables
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2015.48.34%202.png)
2. Outlook tiene la mayor `Ganancia de información === Información mutua`, por lo que será nuestro nodo raíz
	1. 
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2015.52.53%202.png)
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2015.53.13%202.png)
3. Volvemos a calcular la entropía para cada rama. Rain (solo 5 instancias), Sunny (otras 5 instancias).
	1. 
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2015.54.30%202.png)

### Observaciones y desventajas
> Es una heurística, por lo que seguramente no lleguemos a un óptimo global.  

- Because of being greedy, it can lead to a local optimal solution rather than global
- Extension of ID3 to add a form of backtracking (post-pruning the tree)
- Because of using statistical properties of all the examples (in info gain), search is less sensitive to errors in data
- Extension of ID3 to handle noisy data by modifying its stopping criterion: create a leaf without perfectly fitting the data (label with majority)
- Complexity increases linearly with the number of training instances and exponentially with the number of attributes
- It has been shown that the selection of variables with more values is favored

### Deventajas
- Determine how deeply to grow the tree
- Choose an appropriate attribute selection measure Handling continuous attributes
- Handling training data with missing attribute values Handling attributes with differing costs
### Problema de Overfitting
Problema demasiado ajustado a los datos
Es mejor, buscar algo Más general, con menos variables

> Fallo intrínseco debido al parámetro de parada  
> ID3 lo va a hacer muy bien con el training y muy mal con el test  

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.01.43%202.png)

### Dos estrategias de Poda
Podamos el árbol para simplificarlo y que sea más genial

- Prepoda: No se usa
- Postpoda:
	- Después de construir el árbol completo con el ID3 -> podamos
	- Más costoso, porque hacemos y luego deshacemos
	- Funciona de abajo a arriba
		- nos apuntamos cuanta precisión tiene el árbol antes de la poda
			- esta precisión se utiliza en un subconjunto de poda (que es diferente al de test)
		- miramos los subárboles, un nodo (casi hoja) con sus hojas directas
			- conjunto de poda
		- y sustituimos el subárbol y ponemos la etiqueta mayoritaria
		- comparamos la precisión y nos quedamos con las que mejora el resultado.


### Alterantivas que teóricamente mejora, pero en realidad NO
Otros atributos de selección de valores, diferentes a la precisión
Ejemplo: Fecha 
Para corregir las Variables con muchos valores (distribución uniforme)  uniformemente repartidos, entropía altos. Hay que penalizarlos

Atributo: Grain Ratio
**Cociente de ganancia**

En la práctica no tiene tanto impacto, comparado con la poda

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.09.34%202.png)


## Variables continuas -> Las discreteamos
- Nodo A
	- < C
	- >= C
**Cómo encontrar C?**

Cambios de la clase

Ejemplo:
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.13.44%202.png)

Generamos cortes dinámicamente. Buscando puntos medios entre los cambios de clase de acuerdo a la variable continua. Pueden aparecer o desaparecer
- Ordenar
- Buscar cambios
- Elegir el punto medio
- Decidir con los atributos y las “”¿variables?””

### Datos que faltan MISSING
Si tenemos muchos datos, podemos eliminar las filas con esos campos
Pero lo más habitual es “*imputar*” , rellenar los missings
	- Hay SW que lo resuelve con estadística
	- Datos que cuestan recoger (datos de pacientes), o datasets pequeños no merece la pena borrar filas.

> PROGRAMA PARA LA PRÁCTICA: Hueca  

- Solución 1 -> Asignar la moda. El valor que más se repite
- Solución 2 -> Asignar la moda, pero solo los de mi misma etiqueta
- Solución 3 -> Asignar toda la distribución de probabilidad que hay en la columna

Estas estrategias se pueden hacer a nivel de dataset o durante una iteración de ID3

### Incluir el coste en la selección de medida de atributos
Dinero, tiempo, molestia
**Lower-cost attributes**
Queremos favorecer los atributos baratos
Y penalizar los más caros
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.26.19%202.png)

Para normalizar los costes entre distintas variables, es una función subjetiva, que no tenga unidad de medida.

## C4.5
Se llama C , porque fue escrito en C y 4.5 es la versión.

**Cociente de ganancia === gain ratio**

Reglas de post-poda

r1: si x1 = 1, x3=0, C=yes

Borramos contextos, ramas.
Esto produce que varias reglas se cumplan. Hay que calcular qué regla es la mejor.

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.29.33%202.png)



## MUNDO CONTINUO - **Continuous class variable (numeric prediction)** - ¡ REGRESIÓN !
- Generalize these ideas for continuous regression functions
- Regression tree: at the leaves the value represents the response mean value of the instances that reach the leaf
- Adopted by the well-known CART system [Breiman et al., 1984] We approximate a non-linear function by a piecewise constant one Valid for any kind of attributes
- Model tree: at the leaves there is a linear regression model to predict the response of the instances that reach the leaf
- M5 algorithm [Quinlan, 1992] and M5’ [Wang and Witten, 1997]
- Any kind of attributes, especially continuous Regression trees is a particular case of model trees


### Regresión !
Tengo puntos esparcidos en un eje. Hay que buscar la función lineal representa esos puntos
Hipótesis, modelo
`Y = B0+B1X+epsilon`
Estimación: `Y = B0+B1X` (todos con ^)
Están alineadas las medias.
Y esperanza

Lo que estima una regresión es una media en cada X

### Árboles de regresiones
Abre opciones, y cuando llega a un nodo hoja -> llega a una variable respuesta (dependiente Y aka C)
Se usa en el SW CART
Es como una función constante a trozos

### Model Tree
No da números, da modelos, es mucho más potente
Los nodos hojas son funciones

Ejemplo:
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.39.48%202.png)

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.41.15%202.png)

Cuando hueca implementó el M5, le pusieron el ‘ prima, porque no era seguro que fuera el mismo.
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.41.45%202.png)

> ¿Qué criterio de bondad utilizamos para poner cada nodo?  
> Buscamos que no haya mucha varianza (desviación típica) -> los valores son muy parecidos  

Nos interesa que los valores se vayan pareciendo para que la media acierte.
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.44.52%202.png)

- Nos interesa suavizar los pasos de unos hiperplanos a otros se pueden añadir las siguientes estrategias
	- Stop growing the tree when:
			- Only a few instances remain (≤ 4)
			- Class values of instances that reach a node vary very slightly (its SD is a small fraction of the overall SD with all data, e.g. 5 %)
	- Also pruning

Manejar atributos discretos X
Si una variable toma valores discretos (sexo, colores, etc)
Los convertimos en K-1 variables discretas
Sexo: H|M -> Hombre -> x1 = 0 | 1
Color: Rojo|Amarillo| Verde -> x1,x2 = 0,1 | 1,0 | 0,0
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.47.09%202.png)

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-03%20a%20las%2016.52.36%202.png)

## Conclusiones
- ID3 greedily selects the next attribute to be added in the tree
- Avoiding overfitting is important to have a tree that generalizes well ⇒ Pruning the tree
- Many extensions to ID3: handle continuous attributes, with missing values, other attribute selection measures, introduce costs
- Continuous class: model trees (M5) with linear regressions at the leaves

# a05-04 Bayesian Classifiers

20191010
2.3 Bayesian classifiers
Pedro Larrañaga

## Índice
1. Naive Bayes
2. Selective naive Bayes
3. Semi-naive Bayes
4. Tree augmented naive Bayes
5. Forest augmented naive
6. Bayes Superparent-one-dependence estimators k-dependence
7. Bayesian classifiers Bayesian network augmented naive
8. Bayes Markov blanket-based
9. Bayesian classifier
10. Unrestricted Bayesian classifiers
11. Bayesian multinets
12. Summary

> El clasificador más utilizado en el grupo  

## Clasificador generativo
Si tengo N predictoras, las distribución tendrá N+1 variables

Redes bayesianas -> grafos

x1 -> C
x1 * x6 dados sus padres,

## Estimación de parámetros
> Siempre habrá que estimar parámetros independientemente de los   

Máximo verosímil o aproximación bayesiana
- MLE ->
	- ^P(X2=2 | C=1, X3=3)
- Estimación bayesiana
	- estimación de laplace cuando `å = 1`
		- se puede usar máximo verosímil y aproximarla con laplace
	- Schrmann-Grassberger rule: `å=/frac{1,/sub{R,j}}`


Smoothing suavizado de mis estimaciones y que ningún parámetro valga 0

## 1. Naive Bayes
- Desventaja
	- los números a estimar no son independientes

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2015.49.34%202.png)

Cómo es la frontera de decisión? -> Es un hiperplano

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2015.50.05%202.png)

Pesó como una losa saber que las fronteras eran hiperplanos, 36 años en que surgiese una nueva propuesta de clasificador bayesiano
Fronteras de decisión demasiado simples
Funciona bien para bio informática, donde hay muchísimas variables en una muestra pequeña

### Naive Bayes con hidden variables
Se añaden variables ocultas
Región de decisión es mucho más simple.
- El modelo es más complejo de entender
- El modelo es más pesado para inducción

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2015.55.55%202.png)

## 2. Selective naive Bayes
Es el mismo naive bayes, pero no se usa todas las variables que nos llegan, sino que hacemos una selección de variables. 
Nos quedamos con un subconjunto.

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.06.21%202.png)

- Filter: No involucro al clasificador
- Wrapper: Cuanto de bien lo está haciendo el clasificador

## 3. Semi-naive Bayes
Es el mismo naive bayes con **super nodo**
La variable puede tomar tantos valores como el producto de (X1,X3)

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.08.20%202.png)

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.08.35%202.png)

- comienza como una estructura vacía, 
- Independientemente de los valores p(c|x1,x2,x3,x4) coincide con p(c)
- Tiene un porcentaje de bien clasificados que coincide con la clase mayor de c
	- 80% positivos, 20% negativos -> si siempre clasifica en positivo, acierta el 80% de casos
- Se busca le mejor opción entre: (se pueden usar en todos los pasos menos en el primero)
	- añadir: 
		- 
	- unir: 

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.11.40%202.png)

Crea super nodos indicando que esas variables están muy relacionadas dado C


## 4. Tree augmented naive Bayes (TAN)
Lo más usado para reemplazar naive bayes
Nuestro algoritmo va a encontrar ese árbol
Filter -> basándonos en cantidad de información mutua
	
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.17.04%202.png)

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.17.17%202.png)

Árbol expandido de peso máximo, donde el peso se calcula partir de cantidad de información mutua de dos variables predictoras dada una clase.
	Dos aristas con mayores pesos.

Árbol no dirigido, para convertirle en dirigido, se coge un nodo al azar y se convierten sus  ___ en arcos

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.19.34%202.png)
No nos sirven c) y d) porque los arcos no pueden tener más de un padre, para que no se invalide la condición de árbol.

- Necesitamos la probabilidad C
	- x1 | C
	- X2 | x1 y C
	- …

El modelo no es complejo, porque todas las variables tienen solo 2 árboles.
C y otro nodo

## 5. Forest augmented naive
En vez de un árbol, se considera un bosque
> No es tan popular y no entramos en esto  

## 6. Bayes Superparent-one-dependence estimators - SPODE
SPODE
Tipo de estimador de una dependencia.
- En un ODEs
	- forma particular de un TAN
	- Cada variable predicadora, se permite que dependa de una variable
- SPODEs
	- se permite que todas las variables dependan de la misma variable
	- son interesante porque el AODE (abarajes the predictions of all qualified SPODEs) -> Metaclasificador

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.25.04%202.png)
Tiene suficientes casos como para poder estimar de ellos. Se necesitan al menos 30 casos.

## 7.  k-dependence Bayesian classifiers 
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.27.31%202.png)

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.30.55%202.png)

## 8. Bayesian network augmented naive
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.31.08%202.png)
Son propuestas de teoría de información porque son filter.
Calculamos cosas que involucran dos o 3 variables y según eso construyo nuestro modelo.

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.32.44%202.png)

> La complejidad no está limitada  

## 9. Bayes Markov blanket-based Bayesian classifier
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.34.56%202.png)

El manto de markov asocia cada variable con
- sus padres
- hijos 
- padres de los hijos.
subconjunto de variables del que realmente depende esa variable

Cómo determinar este manto
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.36.15%202.png)

> Es backward, eliminando variables hacia atrás  
Va eliminando las variables hasta aproximarse al MB(C)

Una variables es eliminada si la info que nos da, con respecto a las variables que ya hay es prácticamente nula

Eliminamos variable a variable, manteniendo la distribución de probabilidad.  Que se parezca lo más posible cuando condiciones a todas las variables
Que se parezca según la divergencia de ****

## 10. Unrestricted Bayesian classifiers
Muy parecido al manto de markov MB
> C puede tener padres igual que en MB  
Se aprenden con algoritmos genéricos de Redes bayesianas, donde C juega igual que el resto de variables

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.39.52%202.png)

> La estructura la hemos conseguido con métodos genéricos  


## 11. Bayesian multinets
Surgieron para representar independencias condicionales que dependen del contexto

> Se representa la Independencias condicionales dependientes del contexto.  
EJEMPLO: Una enfermedad (la tienes o no). Entre los sujetos adultos > 55 años, las variables se interelacionan de forma distinta que en los jóvenes.

Variable hipótesis o variable **** (en el ejemplo es la edad)

La variable clase es “Tienes enfermedad” “No la tienes”
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2016.40.21%202.png)

más ricos a nivel de semántica, dependientes del contexto

## 12. Summary
- Se puede evaluar con el “bayes score”
- Resultados competitivos
- Descubren conocimiento, son explicables , transparentes etc. XIA

- Provides a posterior probability for each possible value of the class 
- Competitive results (accuracy, Brier, ROC) with the state of the art in supervised classifiers 
- Knowledge discovery from the structure of the Bayesian network 


## Referencias
- TAN -> N. Friedman, D. Geiger and M. Goldszmidt (1997). Bayesian network classifiers. Machine Learning, 29, 131-163
- HIPERPLANOS -> M. L. Minsky (1961). Steps toward artificial intelligence. Transactions on Institute of Radio Engineers, 49,8-30 

# a05-04 KNN K-Nearest Neighbors - Vecinos más cercanos

20191010
2.2 K-NN-MUAI pdf
Pedro Larrañaga

Paradigma vs modelo
Paradigma -> Genérico,
Modelo -> algoritmo aplicado a una base de datos

Inducción del modelo, transducción del modelo

Muy intuitivo para el ser humano.

Mimetiza lo que hacemos cotidianamente

## Índice
- The basic k-NN algorithm
- Theoretical results
- Variants of the basic k-NN
- Distance selection
- Prototype selection
- Instance-based learning

## The basic k-NN algorithm

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2015.06.49%202.png)


Zonas de influencia si fuera un 1-NN
No son fronteras de decisión
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2015.07.16%202.png)


- Advantages
		- 1 Able to learn complex decision boundaries
		- 2 No loss of information because there is no modeling (abstraction) phase
		- 3 A local method
		- 4 Few assumptions about the data
		- 5 Easily adapted as an incremental algorithm and also works when the input is a data stream of instances
		- 6 Easily adapted to regression problems
- Disadvantages
		- 1 High storage requirements
		- 2 Slow in classification time
		- 3 Sensitive to the value of k, the distance metric choice, the existence of irrelevant variables, and noisy data set
		- 4 There is no explicit model

## Theoretical results
	* **1**For unlimited quantities of data, the *k*-NN algorithm is guaranteed to yield an error rate no worse than twice the Bayes error rate (the minimum achievable error rate given the data distribution), when *k*increases as a function of the number of data points (Covert and Hart, 1967) 
	* **2**The repeated application of Wilson’s editing (a prototype selection method) will lead to the Bayes error rate (Devijer and Kittler, 1982) 
		* en el límite nos lleva al error de bayes
	* **3**Specified explicit decision boundaries for *k*-NN algorithms (Bremmer at al., 2005) 
		* Hay expresiones analíticas para las fronteras de decisión


## Variants of the basic k-NN
No se suele usar por defecto, se suele usar alguna variante.

### Weighting neighbors
The contribution of each neighbor depends on its distance to the query instance, with more weight
being attached to nearer neighbors
The weight wj of the j-th neighbor can be defined as a decreasing function h of its distance to the
instancetobeclassified,x:wj =h(d(xj,x))
The query instance will be assigned to the label with the largest total weight

### Weighting predictor variables
A weight to each predictor variable, that can be proportional to its relevance with respect to the
class variable
d(x, xi ) = 􏰅nj=1 wj δ(xj , xji ), where wj is the weight assigned to variable Xj , and δ(xj , xji )
measures the distance between the j-th components of x and xi
The weight wj may be proportional to the mutual information between Xj and C

> Más peso   

### Average distance
The distances of the neighbors to the query instance are averaged for each class label, and the label associated with the minimum average distance is assigned to the query

> En vez de pesar los casos considero lo k-vecinos cuales son positivos y negativos y calculo la distancia media y me quedo con la menor  

### k-NN with rejection
Demands some guarantees before an instance is classified
If the guarantees are not met, the instance remains unclassified until processed by another supervised classification algorithm according to a cascading procedure
A usual guarantee refers to the threshold for the most frequent class for the neighbors of the instance to be classified

Esto puede ser uno de los metaclasificadores de cascada

> No siempre voy a tomar una decisión.  
> Solo si tenemos muchas garantías, que   
> Si k=10, si 9 o 10 son del mismo tipo  
> Los sin clasificar se dejan para otros clasificadores  


## Distance selection
### El problema de medir el aprendizaje. The metric learning problem
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-10%20a%20las%2015.22.15%202.png)

## Prototype selection
Estamos buscando un subconjunto de base de datos que sea consistente con la frontera de decisión
Consistencia de la frontera de decisión: Que la frontera de, es la misma que tendría con el resto de la base de datos

### Condensation, edition, hybrization

Si el segundo ejemplo es de la misma clase, no se tiene en cuenta.

- Prototype selection aims to output a representative smaller-sized training set than the original one that has a similar or even higher classification accuracy for new incoming data
- Ideally subsets that are both decision boundary consistent (the decision boundary found with the subset is identical to the boundary for the entire training set) and minimum consistent (the smallest subset of the training data that correctly classifies all original training data)
1.  **Condensed nearest neighbors algorithm (Hart, 1968)**
	- Iterative and starts by initializing the subset with a single training instance
	- In a second step, it classifies all remaining instances based on the subset, transferring any incorrectly classified samples to the subset
	- The last step repeatedly goes back to the second step until no transfers occur or the subset is full Incremental, order dependent, and neither minimal nor decision boundary consistent
	- The output subset will retain points that are closer to the decision boundaries, also called border points. At the same time, it will remove internal points
2. **Edition methods (Wilson, 1972)**: Quita los puntos que no están de acuerdo. No hay orden. Se hace al final del todo.
	- Removes points that do not agree with most of their k nearest neighbors (noisy instances)
	- Smooth decision boundaries
	- Homogeneous groups
3. **Hybrid methods**
	- Combine edition and condensation strategies: first editing the training set to remove noise and smooth the decision boundary and then condensing the output of the edition to yield a smaller subset

## Instance-based learning
IBL -> Principios de los 90 y es el Machine Learning actual

- Instance-based learning (Aha et al., 1991) extends k-NN by providing incremental facilities, significantly reducing the storage requirements and introducing a hypothesis test to detect noisy instances
		1. **IB1**: Normalization of predictor variable ranges (avoiding, or reducing, the differences in variable weights for the Euclidean distance between two instances) and incremental instance processing
		2. **IB2**: Only instances near the decision boundaries are needed (reduce storage requirements). The set of informative instances is approximated as the training instances misclassified by IB1
		3. **IB3**: Noise-tolerant extension of IB2 that decides, using a simple test, which of the saved instances should be used to make classifications and which are believed to be noisy (these are discarded)

## Referencias
T.M. Covert, P.E. Hart (1967). Nearest neighbor pattern classification. IEEE Transactions on Information Theory, 13, 21-27
E. Fix, J.L. Hodges (1951). Discriminatory Analysis, Nonparametric Discrimination: Consistency Properties. USAF School of Aviation. Technical Report 4
D.L. Wilson (1972). Asympotic properties of nearest neighbor rules using edited data. IEEE Transactions on Systems, Man, and Cybernetics, 2(3), 408-421


Selección de prototipos y de instancias


> Cambio de concepto  
> Concept ref   
> 	Virtual:   
> 	Real:   


# a05-05 Rule induction. 2.6 Rule-Induction-MUAI

- Pedro Larrañaga
- 20191017
- 2.6 Rule-Induction-MUAI


Conocimiento
Motor de inferencia del sistema experto

## Índice
- algoritmo 1R
	- muy simple en la que se basa el resto
	- trata de buscar reglas muy simples
- algoritmo AQR
- algoritmo CN2
- algoritmo RIPPER

## R1
Para cada valor de la clase
Selecciona una regla por variable
Se queda con la regla que más porcentaje de clasificados tenga

## RIPPER

## IREP
- D es la unión entre D
	- GROW - crecer
	- PRUNE - podar
- Y la intersección es vacía.
	- D se participan en DGrow y DPrune
	- Con ejemplos + y -
		- para una clase binaria

Si es multi clase, se compara la clase X VS el resto

El conjunto de reglas

Una sucesión es una regla de literales.
Literal 

Hablamos de intersección de literales

- **Cover** -> Cobertura -> son los ejemplos para los que esto es verdad
Cubre un conjunto limitado de casos.

IREP funciona de forma voraz hacia delante

IREP greedy forward y empieza en 0.

En esta regla no hay ningún literal, y en cada paso se introduce un literal que maximice .
FOIL -> que vaya mejorando
Dejaré de introducir literales cuando no encuentre ningún literal hasta que no haga mejorar un **criterio FOIL**


![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-17%20a%20las%2015.24.41%202.png)


Regla R -> Regla actual, cubre 90 ejemplos de la base de datos, de los cuales positivos son 70 y negativos son 20

Consideramos 2 especializaciones de esa regla
R’ = R + Literal1 -> cubre 80 ejemplos +50 y -20
R’’ = R + Literal2 -> cubre 80 ejemplos

Ambas son dos especializaciones de R

> Buscamos la regla de  mínima entropía  

IREP pone a competir reglas especializadas

La fórmula da más valor a la parte positiva que a la negativa

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-17%20a%20las%2015.34.20%202.png)


PODA
Criterio PRUNE
La regla es backward, siguiendo el orden inverso.
Primero pruebas con el último literal que ha entrado

ALGORITMO
Está en bucle es hasta que no quedan ejemplos positivos
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-17%20a%20las%2015.37.17%202.png)

# a05-05 Selección de variables. 2.7 Feature subset selection

- Pedro Larrañaga
- 20191017
- 2.7 Feature subset selection
- REVISAR LAS TRANSPARENCIAS

> No es PCA (Extracción de nuevas variables)  
> No es MDS (Multidimensional Scaling)  
> No es TSNE  

- Clasificación supervisada
- Muchas variables
	- no son relevantes
	- otras son redundantes

En probabilidad se busca Omega(S) = 2^n
Si supera 50 o 100 , nos desborda

Ventajas Desventajas
- Reducción de dimensionalidad de datos
- Ayuda a los algoritmos de aprendizaje en su velocidad y efectividad
- mejora la precisión del clasificador
- Mejora de la interpretación porque hay menos variables
- La desventaja es: computational burden 

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-17%20a%20las%2015.51.36%202.png)



## Aproximación Filter
Juega con las propiedades intrínsecas de los datos
> Para hacer una selección filter no hace falta recurrir a ningún clasificador  
> Esta selección será válida para cualquier tipo de clasificador, porque no le involucramos  

De todos los subconjuntos (2^n) cuál es el mejor?

- Funciona muy bien en grandes datasets
	- una variable
- La selección se realiza solo una vez
	- sirve para todo

- Filtrado 
	- univariante
		- a cada variable le aplico una función en relación a la clase
			- y elijo un threshold a partir del cual me quedo con todas las variables y tiro el resto
	- multivariante
		- evalúo cada subconjunto
			- el subconjunto depende de la búsqueda 🤷🏻‍♂️



![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-17%20a%20las%2016.01.43%202.png)

PEDRO
>> Esto no sé lo que es. Mejor os lo miráis en casa
>> Quería que nosotros leyéramos las transparencias y salgamos a presetar los algoritmos AQR y CN2 de `2.6 Rule-Induction-MUAI.pdf`
>> Me estoy liando, mejor os lo miráis en casa

>> Esto es un poco lío [pag 26/48]
>> No, no lo entiendo, no lo entiendo
>> Me lo apunto, y os lo cuento la siguiente clase
>> Esto no funciona

>> Qué sentido tiene, si tiene algún sentido para vosotros
>> Lo estoy volviendo a hacer mal
>> Lo estoy liando
>> W1 se refiere solo a la primera  coordenada
>> Perdón, estaba bien hecho
>> Perdón , perdón
>> No, estaba mal hecho, ahora está bien
>> No , i se está refiriendo al caso y la j se está refiriendo , digamos, a la variable



## Filter Model free

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-17%20a%20las%2016.20.12%202.png)
Para cada variable Xj tendremos una regla
Va seleccionar (filter) 
Cuanto de relevante es la variable
Si utilizamos esta variable para clasificar, cuantos éxitos tendría

Cuanto más grande es, más seguro estoy de que es relevante

## Aproximaciones por envoltura
Subconjunto de variables y construyo el clasificador
Evalúo como de bueno es ese clasificador

> Tengo que construir un clasificador  
> Es costoso computacionalmente  

Heurísticas 
>> La asignatura no va de heurísticas de búsquedas , así que no voy a hacer muchos comentarios
>> No sé, me voy a saltar
>> Podéis echar un ojo, pero creo que os lo van a contar mejor en otra asignatura
>> Os lo van a contar.
>> Voy terminando, aunque veo que faltan varias cosas

VNS -> 
Suponemos que hay una vecindad


## Estabilidad en la selección de variables


# a05-06 Regresión Lineal
- Concha
- 20191024
- `2.4 Logistic regression.pdf`

- Modelos discriminativos
	- regresiones
- Modelos generativos
	- bayesianas


Una regresión es el modelo es una formula, que depende de unos parámetros que vamos a estimarlos.

Método de máxima verosimilitud -> likelihood

## Motivación
### Objetivos
- Buscar la relación entre una o más variables productivas y dependientes.


## Approach

## Intuitions

## Expresiones : Ratio de riesgo
> En medicina es mejor dar un porcentaje para el riesgo, en vez de decir que el paciente está enfermo.  

## Expresiones: odds (posibilidades) and log it
- Regresión lineal:
	- ß1 = es el cambio en e Y cuando en X1 se incrementa en 1
		- es lo que cambia el logit cuando la X1 se incrementa en 1
	- ß2 = es el cambio en e Y cuando en X2 se incrementa en 1
	- …
	- ß0 es cuando todos los parámetros son 0. Del patrón 0.

Y = logit de π = `ln(π/1-π)` = `ß0+ß1X1+…ßkXk`

**Escala de los logit**


## Método de máxima verosimilitud
> > levantad la mano  
> > más alto  
>   
Exponencial(lambda)
f(x) =lambdae
Función de densidad  de muchas de las que hay

muestra de tiempo de vida de bombillas: x1, x2 ,x3 , sabemos que estas muestras vienen de una exponencial

Maximiza la verosimilitud = 

Primero vamos a calcular la función de densidad de nuestra muestra
`f(x1,x2,….,x5)`
Idénticas e independientemente distribuidas.
`f(x1) * f(x2) ...*f(x5)`
Lambda*e^-lambda*X1 * Lambda*e^-lambda*X2

Pasamos de verlo en función de las x a verlo a una función de lambda.

lambda^s

Función de densidad en base del parámetro. Nos dice que es más verosímil (más se aproxima), cuanto más alto sea el número.

Hay que calcular la segunda derivada y evaluarla en los puntos que son 0 en la primera y ver que sea máximo.

max de lambda L(lambda) es igual que calcular el máximo de lambda en LN(L(lambda))
El máximo se alcanza en el mismo punto, tomemos LN o no

Tomamos derivadas 

> Cuando queremos calcular  
> también lo podemos usar para calcular el coeficiente de   
> Cogemos datos para la muestra  
> Calculamos la función de verosimilitud   
> Maximizamos esa función  
> Maximizamos el LN  
> tomamos derivadas para calcular el máximo y en la exponencial nos saldrá que Lambda es `1/la media de la muestra`  

> Podríamos memorizar las funciones para calcular los parámetros de las distribuciones dados unos parámetros  

## Para maximizar el LN(L()) Newton-Raphson 

## Feature subset selection

**^ = Estimador = Variable aleatoria**

- Eliminar correlaciones en los predictores
	- Important to remove it, as done in linear regression
		- Se comparte en la regresión lineal
	- correlaciones altas , hacen una varianza alta

Salida de regresión logística:
- Term i = variables
- ßi = 
- SEi = error
- t-valor = ßi / SEi
	- estadístico de **Wald**
	- se compara con la t-student
	- 
> Se hace mucho en regresión lineal para ver por separado si cada variable la podemos quitar  
> No es muy fiable en regresión logística  


Salidas de predicciones
Coeficiente de 
ASE = Asintotic Error -> 


### Incluir efectos no lineares
Se crean variables que son productos de dos variables.
Va en contra del principio de parsimonia
Principio de jerarquía , si quitas a la variable, no metas la pareja

### Tests de Hipótesis
p valor = probabilidad de tener una muestra más rara , y se rechazaría la hipótesis.


## Términos
- Insesgado = Esperanza[media de X] = µ
- varianza pequeña = eficiencia
	- marca la estabilidad




**WEKA**
Modelo discrimanativo
aparecen funciones complejas, 
Máxima verosimilitud -> 
Estrategias FSS
	tests específicos para tener una estrategia backward

# a05-07 METACLASSIFIER - Metaclasificación
- Concha
- 20191031
- `2.8 Metaclassifiers.pdf`

## PAPER para el POSTER
**PAPER Metodológico**
Artículo de revista (no de conferencia).
Enviar un email con el paper seleccionado.

## Motivación
- *Non free-lunch theorem:* Wolpert and MacReady 1996
- cada algoritmo converge mejor y falla en ciertas circunstancias
- Similar 


## Formas de caracterizar metaclasificadores
1. Distintos espacios de características (features)
	- un clasificador de voz, otro de imagen
	- cada clasificador hace una predicción
- Un combinador
	- que agrega datos

2. Un espacio único/común de características con diferentes clasificadores, dónde cada clasificador son de:
	- diferentes tipos
	- entrenados con diferentes muestras
	- cambio de parámetros

3. mejores set de componentes
	- no nos centramos tanto en la **precisión**
	- es mejor la **diversidad** , para que cometan diferentes errores
		- si todos dan la misma salida, no sirve tener/consultar varios

Resumen
- no nos centramos en optimizar la **precisión** de los clasificadores por separado
- son elegidos por **simpleza**
- cada uno es preciso en diferentes instancias, está **especializado** en subdominios
- esperamos que el **error decrezca** , porque su **varianza** decrecerá
	- Bias-variance decomposition= total expected error of a classifier
	- Variance: source of error due to the particular training set used, inevitably finite and not fully representative of the actual population
	- Bias: measures how well the learning method matches the problem (the persistent error of the algorithm that can’t be eliminated even by taking an infinite number of training sets into account) 

# Métodos básicos
- Fusión de etiquetas 
	- voto de la mayoría
		- con más votos
	- mayoría simple 
		- que haya más de la mitad de votos de acuerdo 51%
	- voto de la mayoría con un threshold
		- 80% de los clasificadores 
		- podríamos quedarnos sin respuesta , sin etiqueta
			- `undefined`, no es fiable
			- o si hay un empate
	- voto de la Mayoría ponderada
		- pesos por cada clasificador
		- hablan de la confianza, la bondad del clasificador
		- brier score, curva ro 
- Fusión de la salida de los valores continuos 
- Stacked generalization
- Cascading 

## Fusión de etiquetas (Árboles, …)
- L: nº de clasificadores (i)
- R: valores de las clases (j)
- x: un caso cualquiera de entrada
- dij(x): 1 o 0 , 1 si clasificador i clasifica a x como j , e.o.c. 0

Votos por mayoría.
Para métodos no probabilísticos.

## Fusión de salidas continuas (Regresiones, TAN). Salidas con probabilidad o una variable continua
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-31%20a%20las%2015.46.58%202.png)

Función de soporte que saca un resumen de los resultados de cada clasificador.
- Media:
- Mediana: la utilizamos para evitar la influencia de valores muy en los extremos.
- Máximo, mínimo
- Media  recortada: Trimmed 
	- jurados de competición (olimpiadas)
	- Se recortan los extremos, por ejemplo recorte de 20%, si tenemos 5 , quitaríamos el más alto y el más pequeño y sobre el resto haríamos la media.
- Multiplicamos los valores: Ojo, si hay algún cero nos rompe el resumen.
- media generalizada: con nivel de optimismo del combinador

## Método apilado de generalización (Wolpert 1992)
- Clasificadores de diferentes tipos
	- árbol
	- kan
	- reglas
	- …
- En la capa 0 hay X clasificadores y su salida es la entrada de un árbol que será el clasificador que de el resultado.
- En la capa 1 hay un clasificador en forma de árbol que intenta entender la decisión de cada clasificador. El stacking intenta aprender cuales son los más fiables o qué relación hay entre ellos.
	- Es brillante
	- Idea mía, mejor que un árbol una red neuronal
	- Podríamos equipararlo a un combinador inteligente en forma de árbol
- Tener en cuenta que el clasificador de la capa 1 debería se entrenado con labels generadas de forma honesta. con datos de testing y no de entrenamiento.

## Clasificador en cascada
Los clasificadores se esperan unos a otros
Las instancias se pueden explicar 

Al final se suele poner el k-nn, que suele ocuparse de las excepciones


# Métodos avanzados
- **Bagging** = Bootstrap Aggregating (Breiman 1996)
	- Remuestreo
	- Probabilidad de ser elegido en la muestra de bootstrap será 63%
		- se utiliza cuando la muestra es pequeña
	- Vamos buscando la diversidad
	- Dividimos los datos de entrenamiento (training set) para entrenar cada clasificador
	- Todos los clasificadores tienen que ser de la misma clase. (Todo Árboles, todo reglas, todo redes neuronales)
		- Los árboles, reglas, redes neuronales, son muy inestables, pequeños cambios en las entradas
		- Tiene sentido usar sólo clasificadores inestables
			- con pequeños cambios 
	- Voto por la mayoría
		- labels
		- porcentaje -> media y cogemos el mayor
- **Randomización**
	- **Random Forest** (Breiman, 2001) -> famoso por ganar muchas competiciones de Kaggle
	- Además de las filas, se cogen las columnas de forma aleatoria.
		- Cógeme 5 y 8 filas al azar
	- Lo bueno de este método, se puede utilizar cualquier tipo de clasificador (estable o inestable).
- **Boosting**  (Freund Shapire, 1996)
	- Bagging es un Método en paralelo
	- **Boosting** no, es en serie
		- Intenta aprender de los errores de los clasificadores anteriores
		- Muestreo selectivo: No todas las instancias tienen la misma probabilidad de aparecer en cada  clasificador.
			- las instancias mal clasificadas por el clasificador anterior tienen mayor probabilidad de se la muestra del siguiente clasificador
	- **AdaBoost** = Adaptive Boosting
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-31%20a%20las%2016.40.07%202.png)
- **Hybrid**
	- otras opciones que aparecen en el Weka
		- Lazy Bayesian Rules (Zheng y Webb, 2000)
			- Combinación de Reglas con Naive Bayes
			- Concha no se acuerda
		- Naive Bayes Tree (Kohavi, 1996)
			- En sus hojas tiene naive bayes tree
		- Logistic Model Trees
			- es sus hojas tiene regresiones logísticas

## Metaclasificadores en Weka
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-10-31%20a%20las%2016.46.02%202.png)

## Conclusiones
- Combining classifiers to try to find decision boundaries suitable for the problem 
	- Many possibilities
	- We lose interpretability 
- Conference *Internat. Workshop on Multiple Classifier Systems*(MCS) since 2000 has allowed organising the knowledge in this field, although it started in ’90 
- Active field of empirical research (still discussing about how and why it works) 
- Many webs, e.g. www.boosting.org, with much info 

Kuncheva (2004) 70% del libro es sobre combinadores.



# a05-08 Multi-Label Classification

- Pedro Larrañaga
- 20191107
- `02-Supervised-classification/2.9 Multi-label classification.pdf` Pag 0

# Introducción. Categorización de texto
- ACM Computing Classification System 
	- Clasificar los documentos en las 11 
- Eur-Lex
	- Reducir de 200K a 5000 variables
- Aviation Safety Reporting System (ASRS)
	- 60 tipos de problemas que pueden aparecer en los vuelos
- ENRON
	- Fuga de emails de compañía
	- Se usa como pagemark para realizar comparaciones
- Image understanding
	- problemas de visión, detectar distintos de objetos en una imagen
- NLP
	- detectar la edad, sexo, es nativo en el lenguaje?
- diagnóstico médico
	- asdf
- Multiobjective regression - Multilabel classification
	- Predecir 
- Emotional categorization of music
	- también se usa como benchmark. Datasetn Emotions
- Clasificación de patentes internacional
	- 
- Bioinformatics
	- clasificación de la función de los genes
- Neurología
	- Especia del animal, 
- Clasificación demográfica
	- De una cara, predecir la raza, edad, sexo
- Verificación de identidad mediante selfies
- HIV Resistencia de drogas
	- es un coctel de fármacos, y el cuerpo humano se hace resistente
	- predecir cual es el siguiente coctel de fármacos que deberíamos recomendar al paciente

Muchas variables que son objetivos al mismo tiempo.
- Categóricas y binarias -> Mult-label classification
- Multiclass targets -> Multi-dimensional classification
	- nominal
		- matriz de costo por fallar de clase a a clase b
	- ordinal
		- necesariamente un fallo entre clases lejanas es un fallo más grande que entre 
	- mezcla -> 
- Numerical targets -> multi-output regression

## Notación
Pag 26




Hamming Loss -> Media  extendida de la diferencia simétrica a todos los casos y a todas las medidas

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-11-07%20a%20las%2015.42.07%202.png)


## Métricas de evaluación
- 0/1 subset accuracy 
- Hamming Loss
- Information Retrival View
- One-Error
- Coverage
- Ranking Loss
	- Cuantas etiquetas no propias tiene delante 


## Methods for Learning Multi-label Classifiers

- Binary relevance
		- 
- Ranking via single-label learning
		- Heurísticas
		- no puedo con el problema voy a hacer chapucillas
		- voy a considerar todos los casos que tienen solo una etiqueta
		- ignora casos con más de una etiqueta
- Pairwise methods
		- **Ranking by pairwise comparison**
			- Voy a coger dos etiquetas a la vez
			- Para cada ejemplo, cada modelo
			- No selecciono cuando están los dos , o cuando no está el segundo
			- Producimos “6” nuevos modelos de clasificadores
				- para un nuevo ejemplo, se lo paso a los 6
				- Creamos un ranking por la cantidad de veces que responde un clasificador
				- Nos podemos quedar con cualquier clase y todos los que están por encima de ese ranking
		- Calibrated label ranking
			- Más sofisticado que el pairwaise
			- Creamos una etiqueta virtual lambda 0
			- Sin perder ningún ejemplo, contrastamos cada una de las etiquetas contra esa etiqueta virtual
			- 
- Methods that combine labels
		- Label powerset
		- Pruned sets
- Ensemble methods
		- RAkEL
		- Ensemble of pruned sets
- Identifying label dependencies
		- Correlation-based pruning of stacked BR models
		- Chi-Dep
		- Chi-Dep ensemble
		- Hierarchy of multi-label classifiers


## Adaptation Methods. Probabilistic Chain Classifier
- Boosting
- Rank-SVM
- Decision Tree
- Neural Network
- K -Nearest Neighbor
- Instance Based Using Mallows Model Instance Based + Logistic Regression
- Generative Parametric Mixture Model
- Probabilistic Chain Classifier
- Bayesian Network
	- Diagnóstico múltiple
	- Teorema de bayes
	- Multi-dimensional bayesian Network Classifier (MBC)
		- defino la estructura de la red bayesiana
		- 3 subgrafos
			- 1. Clase
			- 2. Puente
			- 3. Parámetros predictoras
		- Distintas arquitecturas
			- Empty - Empty
				- no hay relaciones entre 
				- Previo filtrado para la extracción de variables predictoras basado en un **PCA**
				- Selección basada en un GA para 
			- PGM - Tree-tree
			- HAIS
				- multietiqueta -> multiobjetivo
				- NSGA-II
					- Estructuras no dominadas
			- Bielza 2010 UPM-DIA Technical Report
				- DAG-DAG MBC



Saltar del multi-etiqueta al multi-dimensional pero en ordinal.






# a05-09 Unsupervised Classification - Clustering
- Concha
- 20191114
- `03-Unsupervised-classification/01-AA_Cluster_MUIA.pdf`


## Áreas
- Marketing
	- clientes
- Biología
	- 
- Seguros de coche
	- accidentes, fraude
- Web
	- documentos (basados en términos)
	- logs, grupos de usuario con accesos similares

## Tipos
- Jerárquicos : 
	- 
- No jerárquico
	- particional : k grupos prefijados, normalmente se barren varios k’s y nos quedamos con el que parece mejor
	- Probabilístico: asume que 

## Pasos del clustering
1. Elegir la medida de similitud
2. Elegir una técnica para ser usada (jerárquica o no)
3. Elegir el método / algoritmo de esa técnica
	1. y el número de k si corresponde
4. interpretación los clusters formados (inferir las propiedades que dividen el objeto de acuerdo a la agrupación)
	1. dar nombre

> Buscamos un grupo con cohesión interna y aislamiento externo  

### Similitud?
Cercanía entre objetos.

Es un método exploratorio para generar un conjunto de hipótesis. No para testearlos.
Exploración multivariante de análisis de datos es útil para scatter plots, chernoff’s faces, stars, awnrew’s curves.

- Las caras de chernoff
	- dibujo a nivel de instancia:
		- primera fila del dataset y lo convertimos en una cara
		- Cada n es un rasgo de la cara (ojos, nariz, boca, sombrero, color de pelo)
		- más de 30 variables es complicado para el ojo humano
	- ~útil para estimar la cantidad de ks~ 
- Estrellas: Lo mismo que chernoff pero 
- Andrews’s curve : Cada instancia es una curva trigonométrica
	- se superponen las curvas
- **Plot de coordenadas paralelas**
	- el orden en el que pongas el las x afecta mucho a la representación
	- [Parallel Coordinates in Matplotlib – Ben Alex Keen](http://benalexkeen.com/parallel-coordinates-in-matplotlib/)

## Dos enfoques
1. Aglomerativo (Bottom-up) o ascendente
	1. el más usado
	- hago n clusters
	- 
2. Divisivo (Top-down) o descendiente 


EJEMPLO
5 puntos en el espacio R3

## Distancias
- Single-linkage or nearest-neighbor: la distancia más pequeña. Al nodo más cercano.
- Complete-linkage or farthest neighbor: la más grande
- average-linkage: la media
- centroid: el punto intermedio (vector con la media coordenada a coordenada)
	- centroide entre 
- Ward’s: Suma de cuadrados y se trata de minimizar
	- se calcula el centroide del cluster
	- se calcula la suma de distancias al cuadrado de cada punto al centroide 
	- nos quedamos con el menor

Se genera un **Dendrograma**

**Scree plot** o regla del codo.
Diagrama de distancia a la que se ha alcanzado vs nº de paso . Podamos quedamos en el 

### Micro arrays de ADN
Nivel de expresiones de genes.
Instancias 100 vs genes 50K. Rojo sobre expresado, Verde infraexpresado

## Clustering particional
j=1,…N instancias
i=1,…,K clusters
rij={1 si xj se asigna a cli , 0 eoc}

mu sub i -> prototipo del cluster i = centroide

La función objetivo es minimizar la suma de las distancias al cuadrado entre el elemento y el centroide al cuadrado, multiplicado por `rij` (en el caso que está en el cluster.

1. Seleccionas k semillas (los centroides de los clusters)
2. Asignamos cada objeto al cluster más cercano
3. actualizar centroides
4. Repetir el proceso hasta que los centroides no cambien. (convergencia)

## K-mean - K-medias
### Forgy (1965)
Gran sensibilidad. Depende mucho de cómo 
Los centroides no se actualizan mientras estamos calculando las r’s

### MacQueen (1967)
Cada vez que se asigna una r se calcula la mu


### Segmentación de una imagen (Libro de Bishop 2006)
Representación de una imagen en K colores.
Clustering de pixels

		R	G	B
Pixel 1 :
Pixel 2: 
…
Pixel N: 

## Preguntas
- Jerárquico o no
- qué método/algoritmo 
- qué distancia

- Jerárquico 
	- no hace falta preasignar la K
	- dendrograma es útil
	- La reasignación no está permitida
	- sensible a la distancia escogida
- No jerárquico
	- sensitivo a la partición inicial
	- una buena opción es realizar el jerárquico para coger las semillas o elegir la K

### Qué algoritmos

### Dentro de 
K-medias funciona bien si son compactos
	nos permite una partición del espacio para usar como predictor
	**dirichlet’s tessellation**
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-11-14%20a%20las%2016.33.34%202.png)
	
Cuidado con las escalas 

Para evitar caer en un mínimo local, podemos usar una estrategia Multi comienzo
La mediana es el elemento que está en el centro


## Distancias

Minkowski’s distance
P= 1 Distancia Manhattan - Manzanas de las ciudades
P = infinito Tcheychev


~Distancia de **Mahalanobis** = distancia de entre dos puntos que no afecta la escala.~


## Cómo evaluar la solución del cluster
Hay más de 30 medidas, pero evaluar con estas medidas no es riguroso.

- Distancias entre centroides
- Medida de Silhouette: numerador distancias dentro y denominador distancia externa. Silueta

Lo mejor (aunque es subjetivo ) La **validación externa** , el experto.

### Interpretación la solución
- Poner un nombre a nuestro centroide ( 
- Una buena técnica es comparar las diferencias entre centroides

**Lo que más se usa en el departamento es contrastar con una clasificación supervisada** 
Se coge el dataset y se completa con la etiqueta obtenida del clustering.
Y se convierte en un problema supervisado.
Aplicamos una técnica: como árbol de decisión


PAG.42

# a05-10  COLONIAS DE HORMIGAS
- Alfonso
- 20191118
- 

## Índice
* 1. Colonias de hormigas naturales 
* 2. La hormiga artificial 
* 3. El sistema de hormigas 
* 4. Otros sistemas de hormigas 
* 5. Aplicaciones 
* 6. Optimización multiobjetivo basada en CH 
* 7. Referencias 

## Colonias de hormigas naturales 
Algoritmos basados en cómo se comportan las hormigas. Van dejando feromonas y calcular el camino mínimo entre dos puntos.

Además de las feromonas se toma en cuenta la información de la distancia.

Se toma la decisión del camino para que no sea voraz y favorecer la búsqueda.


Probabilidad 
\tau = Lo que cuesta de ir de `i` a `a`

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.15.01%202.png)

## La hormiga artificial
Mecanismo probabilístico de construcción de soluciones al problema (un agente que imita a la hormiga natural).

Además tiene una información heurística 
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.21.03%202.png) adicional.

### Problema del viajante (TSP) o cartero chino
Se puede resolver por esta MH.

Hormiga artificial debe elegir un camino con una probabilidad que depende de la cantidad de feromonas (Tau) y la información heurística que se tenga sobre esos arcos ().

La información heurística qué se tiene es la distancia entre dos nodos. Suele ser la inversa de la distancia.

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.24.56%202.png)

å = 0 -> solo nos fijamos en el heurístico
ß = 0 -> solo nos fijamos en las feromonas

### Actualización de la feromona

![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.34.32%202.png)
![](a05%20Aprendizaje%20Automa%CC%81tico/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.34.46%202.png)

1 - ro = cantidad de hormonas que permanece

## Otros sistemas de hormigas
* 1. Sistemas de hormigas elitistas(*AS**e*) 
	* a los arcos de la mejor solución de los arcos en concreto, se les suma una cantidad proporcional al parámetro e * el camino mejor (1 / distancia)
	* Estamos intensificando
	* mejores resultados que el no elitista
* 2. Sistemas de hormigas basadas en rankings (*AS**rank*) 
	* Tomaremos las `w-1` caminos mejores
	* Solo echamos hormonas a los primeros arcos y en función de su ranking
	* (w-r) *feromonas
	* donde r es el ranking
	* valor típico de w = 6
	* además al mejor global se le suma una cantidad mayor w*feromonas
* 3. Sistemas de hormigas max-min (*MMAS*) 
	* Tenemos una cantidad mínima y máxima de feromonas
* **4. Sistemas de colonias de hormigas (*ACS*)** 
	* **Explota más la experiencia acumulada por las hormigas en la búsqueda que el AS**
	* Para el depósito y evaporación de la feromona solo se considera la hormiga que generó la mejor solución hasta ahora
	* una nueva actualización (local) de feromona basada en cada hormiga.
	* Cambia la probabilidad de ir de un nodo a otro cuando `q<q_0` va al nodo que haga máximo el
	* valor típico de probabilidad de aceptación es 0.9
	* esta probabilidad es más **determinista**. 
	* también difiere en cómo se actualiza la feromona
		* lo que no se evapora * un parámetro `ro=0.1` solo se aplica a los arcos de la mejor-global
* 5. Sistemas de hormigas mejor-peor  (*BWAS*) 
* 6. Estudio comparativo 
* 7. Sistemas de hormigas con búsqueda local 