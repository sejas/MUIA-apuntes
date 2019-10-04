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