# a07 Búsqueda inteligente basada en metaheurísticas

# a07-00 Tasks - Búsqueda inteligente basada en MetaHeurísticas

- 20190923
	- [x] Enviar email de formar el grupo
		- > Antonio Sejas <antonio@sejas.es> 5:29 PM (37 minutes ago) to amateos, l.guasp, alicia.olivares.gil
		- > Buenas tardes Alfonso, Gracias por la introducción de hoy. Siguiendo tus indicaciones te adjunto los datos de nuestro prometedor equipo. Nombre completo Email Lucia Guasp Alburquerque l.guasp@alumnos.upm.es Alicia Olivares Gil alicia.olivares.gil@alumnos.upm.es Antonio Martín Sejas Mustafá asejas@alumnos.upm.es ¡ Muchas Gracias ! --
	- 

# a07-02 Introducción - busqueda-inteligente-basada-en-metaheuristicas

> Se intentará acabar la asignatura en Diciembre  

Profesor: Alfonso Mateos Caballero
Alfonso
2110 (junto a Antonio Jimenez)
amateos@fi.upm.es
910672901

Resolver problemas de optimización.
Solución rápida suficientemente buena.

Trabajando en AENA
Es mejor que eviten un choque de aviones, aunque los movimientos no sean los óptimos.


## Grupo de investigación
Herramientas y problemas que se llevan.
Grupo Análisis Decisión y estadística
Web: dia.fi.upm.es/dasg/
Director de Grupo Antonio,  1994 
Directora del departamento Pepa

### En qué trabajamos en el grupo
Sistemas Multicriterio, sistemas de ayuda a la decisión. Concha.
Restauración de ecosistemas acuáticos contaminados en el desastre de chernobil por radionucleidos. En varios países. Tienen simulación y han estudiado la central nuclear de almarán.

Publicaciones: Se intenta destacar JCR Q1 y Q2

### Problemas activos actualmente - Líneas de investigación
- Indra:
	- Aluminio, piezas de coche, en qué orden deberían encenderse para satisfacer la demanda a menor coste posible.
		- Utilizando _Recocido simulado_
- Crida: 
	- Herramienta para asignar controladores aéreos a diferentes sectores.
	- 2 controladores por sector, ejecutivo que habla con los pilotos y planificador que está atento a los sectores adyacentes
	- Antes lo hacían por plantillas óptimas
		- para controlar 2 sectores se necesitaban 8
		- 3 + 1+ 1 , óptimos , pero la suma no era óptima
	- El grupo hizo metaheurísitias
		- pidieron redistribuir controladores para trasladar tráfico ante bajas temporales de controladores o atmosféricos.
	- Habrán Becas por CRIDA en el 2º cuatrimestre
- Crida aeronáutica y enaire:
	- Determinar distintos flujos por el espacio aéreo
	- Los aviones van por puntos similares a autopistas
	- El tráfico aéreo aumenta y 
	- Se quiere determinar los flujos de aviones según el histórico
		- **encontrar patrones**
	- Saldrán 2 o 3 Becas de 800€ (2 Trabajos Fin de Master). Solo hay que cumplir unos objetivos, sin horario.
		- Nos darán datos y habrá que calcular flujos
- AI.Innovation Space
	- Determinar precio de hoteles para cada noche
	- usando histórico del hotel y scraping de la competencia
	- Análisis de riesgo adversario
		- La competencia es quien quería quitarnos los clientes
- modelos multicriterio y models de interdependencia para la gestión de riesgos. 
- Tienen un Doctorando con varios doctorados, inspector de hacienda,  62 años y 
	- Ha publicado artículos en : Estudios económicos (revistas de economías). Review de fiscal JCR. Revistas de España con impacto en . 2 Artículos de de un libro.
	- análisis muy sencillos han encontrado con cosas muy llamativas
		- Representan un individuo, jurídica que paga a hacienda en un grafo
		- Y determinar familiares de cada persona. Mi mujer y mis hijos o padres mayores.
		- Antes no se cruzaban los datos
			- Como los datos se pueden tener durante 10 años
			- Se han descubierto todos los familiares
		- Porcentajes de empresa
			- Yo tengo el 20% de la empresa
			- hijo1 10%
			- hijo2 15%
			- Dueños de empresa y yates y viajes a ibiza
		- 270 millones de arcos
	- Se publican artículos con datos
	- El 10% de las personas más ricas tienen el 85,06% de la riqueza en España
	- La Caixa ha dado dinero para divulgar los resultados.
- Si se nos ocurren ideas para descubrir a los malos, hay líneas de investigación.  Lucha contra el fraude.
- 



## Resultados de aprendizaje
- Aplicar MH para resolver  poblemos de optimización uniobjetivo y multiobjetivo (económicos, medioambientales, sociales).
- MH hay tantas como animales, del cuco, colonia de hormigas , del lobo, … de todo tipo
	- Veremos la taxonomía y las más representativas (más usadas) de cada clase. Suelen ser las primeras que se crearon.
- Manejar los términos y realizar exposiciones en público sobre la temática.

## Capítulos
1. Introducción
2. Métodos Analíticos de optimización multiobjetivos
	1. 3 
	2. Primero modernizamos con variables, restricciones y variables objetivo.
	3. Si hay método analítico, lo resolvemos
	4. Con programación lineal, 
		1. Si el problema es muy complejo o si necesitamos un resultado muy rápido
	5. Si no podemos, entonces usaremos MH
3. MH evolutivas - Algoritmos genéticos multiobjetivo
4. MH de búsqueda global - *Recocido Simulado* : Con probabilidad 1 se alcanza la solución 1
	1. En la práctica no se busca la solución optima, porque requiere demasiado tiempo
5. MH Constructiva. Colonias de hormigas
6. M de Búsqueda Global - *Búsqueda Tabú*

Otras MH las explicaremos nosotros
Muy buenas soluciones en muy poco tiempo

## Taxonomías
> Figuire 10.3  
Metáforas de la vida, inspiradas en naturaleza, matemáticas , física, etc
Trayectoriales
Deterministicas - Scotásticas
UNS usa varios entornos
Con memoria (Tabú, para evitar ciclos) - sin memorias

## MH
**Algoritmos basados en biología**
Programación evolutiva - Fogel 1966 - 
Algoritmos Genéticos - Holland 1975 -

Una MH observa la naturaleza para encontrar la solución óptima.
Nido - Comida, van en línea recta , siendo ciegas. Si pones un obstáculo, lo rodean por el sitio más corto. Podemos utilizar este mismo método 

Tiene un hijo de 17 años. 
Problemas de las reinas para que no se maten entre sí.

Crear una MH no es difícil, pero es difícil que sea buena.

**Social Based**
**Mathematics**
**Chemistry**
**Sport**
**Music**
**Non-Metaphor based**

## En qué se han utilizado
## En qué se han basado
	Biología
Pasa como con la Lógica difusa , como no había nada hecho, y funcionaba bien, se empezó a publicar mucho.
Utilizar MH para problemas que nunca se habían utilizado hasta ahora.

## Para qué tipos de problemas se utilizan?
Normalmente problemas numéricos de optimización , planificación de horarios, data mining, comunicaciones , transporte

[VÍDEO: Visualización de MH para el problema del viajante](youtube.com/watch?v=rYjxtmt8g9A)
- Recocido simulado
	- muchísima exploración e intensificación
- Tabú
	- explora e intensifica
- Algoritmos genéticos
	- Se entiende muy bien, pero es muy lento

## Bibliografía
Para aprobar la asignatura será suficiente con las transparencias
Coello, C.A. Van
Data science y redes complejas enfocado a ML y redes complejas
Hacienda y otros problemas
Con los algoritmos implementados en Python
Teoría de grafos

## Sitios de MH
vnsheuristic.ull.es

## Evaluación de Aprobar
- Tests sencillos a realizar en casa. “”Individuales”” con apuntes.
	- 10% Semana 3 : temas 1 y 2
	- 10% Semana 7 : temas 3 y 4
	- 10% Semana 16: temas 5 y 6 (último examen y asignatura antes de vacaciones de navidad)
- Medirán el grado de conocimiento a muy nivel. Incide mucho en lo que es importante

- 15% Presentación oral de las prácticas sobre algoritmos evolutivos y recocido simulado. Semana 7, 8 o 9 
- 15% Presentación oral de las prácticas sobre GRASP, nubes de partículas , Pop Music, Scattter Search y Colonias de hormigas. Semana 12 o 13
- 5% Participación en las presentaciones realizadas por los profesores y resto de compañeros.
- 35% Memoria detallada del trabajo realizado asociado a las presentaciones orales, tanto teórica como su aplicación. Semana 16


### Práctica
Grupos de 3 personas
Cada práctica son 3 ejercicios. 2 Presentaciones suelen ser necesarios.

2 posibilidades:
	- Aplicar MH explicadas en clase (Recocido Simulado) para resolver un problema.
	- Explicar una MH Nueva no vista en clase. Con un ejemplo sencillo.

Las prácticas se puntúan de 10 al 0.
A la mejor un 10, y de ahí va bajando.
El mejor maraca el baremo. 

La memoria se entrega al final, aunque hayas expuesto antes.

La memoria tiene que tener lo que tiene un artículo.
Resumen abstract. Qué vamos a hacer
Introducción. Dónde lo hemos aplicado.
Análisis: Lo que hayas hecho
Explicar el pseudo código de l algoritmo
La implementación no hace falta que esa nuestra.
Se valorará más la interfaz que el código. (Él es matemático).
> El vídeo del viajero me ha parecido muy interesante.  
Tienes que dominar la MH

Detalla la labor realizada, análisis de parámetro
tiempo de computación

Bibliografía.
EN PDF. 

Las preguntas se harán a cualquier miembro del grupo.

### Criterios de evaluación
Hay que entregar el ejecutable.
Puede ser nuestro o de internet.
Transpariencias

> Tarea  
> Enviar:  
> `Nombres | Email` de cada integrante de equipo a amateos@fi.upm.es  



# a07-03 01 Tema 01
20190930 - Alfonso

- **Optimización**:
	- Calcular máximos
	- calcular la ruta más corta entre dos puntos
		- grafos representados entre distnacias
	- *problema de la mochila* o del ladrón: mochila de una capacidad, solo soporta 15 KG, beneficio máximo
		- Grandes contenedores de Asia, capacidad para un número limito
			- determinar como colocar los contenedores en el barco y ordenarlo de forma óptima
	- En industria 4: orden cronológico de cómo deben funcionar las máquinas de montaje
	- Gestión de tráfico aéreo: Aeropuertos: Aterrizajes, despegues, y como se mueven por dentro.
		- Asignación de puertas a aviones
		- Gran cola de aviones, 4 o 5 aviones para despegar
	
> Todo se podría resolver por metaheurísticas, El problema es modelizarlo  

## Optimización
Función objetivo, determinar 
Las variables tendrán restricciones.
X es el conjunto de soluciones factibles que satisface las restricciones


![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2017.15.12.png)

	- **Programación lineal**, existen métodos que permiten resolver el problema de *forma exacta*. El problema es que hay cientos de miles de variables, y el tiempo de cómputo es demasiado alto y por ello usaremos metaheurísticas.
		- Continuo
			-  **Método de simplex**
				- es el mejor y más utilizado
		- Entero
			- Del pto de vista matemático es más complejo de modelizar
			- Ramificación y acotación
			- Planos de corte
			- Relajación de lagrange
		- Multiobjetivo
			- Simplex multiobjetivo
			- e-restricciones
			- ponderaciones
			- programación por metas
	- **Programación No Lineal**, hay métodos buenos, pero deben cumplir ciertos requisitos. En general será mejor utilizar metaheurísticas.
		- Restringida
			- Métodos para problemas muy concretos
		- no restringido
			- gradiente
			- newton

### Ejemplo de Programación Lineal Continua
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2017.21.31.png)

Un problema ante de nada hay que modelizarlo matemáticamente
- ¿Hay algún método analítico que lo resuelve?
- Visión general del problema

Al ser dimensión 2 podemos resolverlo de forma gráfica

El simplex nos dice que el óptimo estará en un punto extremo
El óptimo estaría en 0, A, B o C
Se sustituye en la z en cada uno de los puntos extremos.
Vemos que el máximo es el pto B . Existe una solución única
Parte gris es el conjunto de soluciones factibles

### Programación lineal entera

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2017.26.33.png)

> No se puede redondear al ser entero  
> Si redondeamos, la solución estaría fuera de la región de soluciones factibles  

El óptimo sería el 2,2

### Programación Lineal Continua
> Objetivos conflictivos  
> Más velocidad vs menos gasto de combustible  
No existe  una solución en la cual tome en todos los objetivos el mejor valor. Porque los objetivos son conflictivos entre sí.


Solución óptima conjunto de soluciones
> **Solución óptima multiobjetivo** : cuando no existe otra solución que mejore todos los objetivos a la vez  

> Solución no dominada, eficiente u óptimo de pareto  

El óptimo no sería B, C y D sería la frontera, la línea continua

Solución de compromiso, si quieres maximizar solo una

> Podemos cambiar de maximizar a minimizar  
Maximizar una función === Minimizar la función cambiada de signo
Y el resultado lo cambiaremos de signo

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2017.42.03.png)

Representación del problema y representación de las soluciones efectivas

> Las soluciones óptimas sería la línea O’-A’-B’  
Si te dan un ideal, coges el pto más cercano a ese ideal

- Solución factible -> Verifica todas las restricciones de las variables
- Óptima -> Las mejores de las factibles
- Satisfaciente -> “”Óptimos de pareto””

## Heurísticas y Metaheurísticas
- Problemas combinatorio: fuerza bruta y obtener la mejor solución
	- Hay un algoritmo exacto que nos dará la solución óptima
- Clase P
- Clase NP
	- complejidad exponencial

**Heurísticas vs Metaheurísticas** : 
- Heurísticas: Algoritmo inteligente para solucionar un problema determinado
	- Usa toda la información del problema, suele quedarse en un óptimo local porque se queda con lo mejor que va encontrando.
- Metaheurísticas:  Clase métodos aproximados de optimización combinatoria que proporcionan un marco general para crear algoritmos híbri- dos combinando diferentes conceptos derivados de la IA, la evolución biológi- ca y los mecanismos estadísticos 
	- intenta salir de los óptimos locales
- Hiperheurística:
	- Dependiendo a la clase del problema, elige metaheurísticas híbridas para resolver ese problema

### Learnheuristics
**Learnheuristics (Calvet et al., 2017):**Hibridación de metaheurísticas con aprendizaje automático para la optimización con entradas dinámicas. 
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page21image5584496.png) 

**Mathheuristics**: mezcla de soluciones matemáticas y metaheurísticas

## Clasificaciones
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page23image6005280.png) 
Recocido simulado, nature-inspired
Trayectorial
- GA -> Algoritmos genéticos basado en la naturaleza, imita como se reproducen los individuos y está basada en poblaciones
	- Son lentos
- TS -> Búsqueda tabú
- VNS -> para rutas de madrid, barcelona y valencia
- GRASP -> 


## Propiedades deseables en una metaheurísticas	
- **Simple**: La metaheurística debe estar basada en un principio sencillo y claro; fácil de comprender. 
- **Precisa**. Los pasos y fases de las metaheurística deben estar formulados en términos concretos. 
- **Coherente**. Los elementos de la metaheurística debe deducirse naturalmente de sus principios. 
- **Efectiva**. Los algoritmos derivados de la metaheurística deben proporcionar soluciones de muy alta calidad; óptimas o muy cercanas a las óptimas. 
- **Eficaz**. La probabilidad de alcanzar soluciones óptimas de casos realistas con la metaheurística debe ser alta. 
- **Eficiente**. La metaheurística debe realizar un buen aprovechamiento de los recursos computacionales; tiempo de ejecución y espacio de memoria. 
- **General**. La metaheurística debe ser utilizable con buen rendimiento en una amplia variedad de problemas. 
- **Adaptable**. La metaheurística debe ser capaz de adaptarse a diferentes contextos de aplicación o modificaciones importantes del modelo. 
- **Robusta**. El comportamiento de la metaheurística debe ser poco sensible a pequeñas alternaciones del modelo o contexto de aplicación. (Que un parámetro no afecte excesivamente a una solución)
- **Interactiva**. La metaheurística debe permitir que el usuario pueda aplicar sus conocimientos para mejorar el rendimiento del procedimiento. 
- **Múltiple**. La metaheurística debe suministrar diferentes soluciones alternativas de alta calidad entre las que el usuario pueda elegir. 
- **Autónoma**. La metaheurística debe permitir un funcionamiento autónomo, libre de parámetros o que se puedan establecer automáticamente. 

## Historia general
## Flujo : Esquema básico de metaheurísticas
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page30image5900528.png) 

Una solución o una población de candidatos a soluciones
- Start -> Inicializamos con valores random
	- cuantas más soluciones tengamos, mejor, pero tardará más tiempo
		- El recocido simulado solo trabaja en una solución, pero podemos paralizar el proceso
- **Fitness** -> Calculamos el objetivo que tenemos. Cómo de bien se ha adaptado al medio. Lo buena que es esa solución.
- Satisface?
	- Sí -> Solución final
	- No-> Generamos nuevos candidatos  y vamos a fitness

Si lleva un número X de iteraciones y no mejora la solución, estamos en un óptimo o óptimo local

La generación de población selección de candidatos depende de la eta

- Explotación -> quedarse con lo mejor.
	- Suele ser muy rápida, pero hay más probabilidades de quedarnos en un máximo local
- Exploración/Diversificación -> Mucho gasto computacional
	- MAYOR DIVERSIFICIACIÓN -> Mayor probabilidad de encontrar óptimos globales

El equilibro es la clave.

# Clasificación
Las explicaremos en problemas uniobjetivo y luego pasaremos a multiobjetivo
Las diferencias son pocas, la diferencia está en el fitness, el objetivo.
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2018.08.46.png)

- Búsqueda Global o Trayectoriales, se van moviendo de solución en solución
	- **no quedar atrapadas en un óptimo local**
		- CÓMO SALIR DE UN M LOCAL
			- a.  volver a comenzar la búsqueda desde otra solución inicial
			- b. modificar la estructura de entornos
				- Entorno: Soluciones vecinas: intervalo, intercambiar nodos ….
			- c. permitir movimientos de empeoramiento de la solución actual.
	- ejemplos
		- 	Recocido simulado
			- principio de diversificación, pero al final hay explotación
		- Búsqueda tabú: 
			- con memoria (a largo y corto plazo) para no caer en bucles
			- Parte de una solución aleatoria
			- O de una dada por una heurística
			- Usa otras metaheurísticas y es una hibridación secuencial
- Evolutiva: Manejan un conjunto de soluciones (población) en cada iteración
	- Se basan en poblaciones, imitan la evolución de los seres vivos, naturaleza
	- ejemplos: 
		- Algoritmos genéticos
			- Los que sobreviven son los que más se adaptan al medio, se mezclan entre sí para 
			- para producir diversificación realizo mutaciones
		- Meméticos
			- MEME: unidad de transmisión cultural o imitación
		- Optimización de partículas inteligentes o algoritmos de nubes de partículas: Social entre bandadas de pájaros
		- algoritmos culturales
		- estimación de distribuciones
		- Búsqueda dispersa
		- Scatter search
		- Es más lenta porque trabajamos con poblaciones de soluciones
- Constructiva : Parte de una solución inicial vacía , se añaden componentes de forma voraz hasta construir una solución. Parten de una solución vacía.
	- GRASP: Greed 
		- Construye una solución de forma iterativa y usa un óptimo local
	- Colonia de hormigas (2001)
		- Como optimizan el recorrido desde el hormiguero hasta la comida
	- Concentración de heurísticas
		- En vez de quedarse con el mejor, combina las soluciones y obtiene una mejor
	- POPMUSIC: Partial Optimization Metaheurísticas Under Special Intendification Conditions
		- Divide y vencerás
		- No suele ser buena, porque el óptimo de un problema no es el problema de los subproblemas






# a07-03 Métodos analíticos de optimización multiobjetivo
20190930

## Introducción
Multiobjetivo, todos los problemas actuales son multiobjetivos.
Económico, sociales,

Optimizar un vector de funciones

Frontera de pareto.
¿Cuál es el mejor animal que corre (guepardo), vuela (halcón peregrino) y nada (pez espada)? -> El mejor en todo es Pato

> Manera de : Dando pesos, ponderando  
> El objetivo 1 es 5 veces más importante que el 2  

Los pesos deben estar Normalizadas (sobre el intervalo 0,1)  para que el peso tenga su significado
4 , 1  -> 4/5 , 1/5

> La importancia de los pesos: Importancia relativa que tiene ese   

Los pesos indican la importancia relativa, que ese valor sea el mayor para que la suma sea la mayor posible

> Una solución es no dominada o eficiente , cuando los pesos son > 0  
Si lambda sub k > 0 , x* P(lambda)

¿Cómo saber si es ?

> !!! Las ponderaciones nos ayudan a usar un sistema multiobjetivo a uno uniobjetivo  



# a07-04 Tema 02 Métodos analíticos para la resolución de problemas de optimización multiobjetivo

02 - Tema 2. OptimizacionMultiobjetivo
Página 14


![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.10.09.png)

Este método no podemos sacar todas las mejores soluciones no dominadas.
No es un método bueno para sacar 
Es un buen método para comprobar que la solución dada es eficiente o no. Siempre que 
La forma de saberlo es 

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.09.11.png)

### Problema beneficio - contaminación


## Método de las epsilon-restricciones
> Quiero maximizar cierto objetivo y para el resto de objetivos me conformo con estar por debajo de este valor.  
> “”Por debajo de lo que se permite por ley””  

Si nos dan un valor decisor, tenemos una solución **satisfaciente**

El método de ε-restricciones consiste en optimizar una función objetivo fl(x) de f, que se supone más importante que las otras, introduciéndose además números reales εk (k ≠ l) para las restantes funciones objetivo que correspon- den a cotas inferiores propuestas por el decisor.

Estamos restringiendo la región factible.
> Teorema: Toda solución óptima y única, podemos asegurar que es eficiente.  

Si no es única, 

> No podemos asegurar que la solución es óptima si no es única.  

### Ejemplo de forma genérica
€1, …..               …€m
`max(f1(x), …., fm(x)`
sa: x€S

Lo resolvemos por por €-restricciones

1. max(f1(x9))
	1. sa. x€S
	2. f2(x) >= €2 
	3. …
	4. fm(x) >= €m
2.

Esto nos dará la primera solución x1, con el a

Las que se han obtenido por igualdad, se ponen.
Si hemos obtenido por >=, ponemos el valor que hemos puesto en la f1(x1)

La función objetivo f1(x) >= f1(x*1)
Se va actualizando epsilon

> Como en las restricciones de €epsilon, tiene un >=  ,   
Puede pasar que los epsilon sean muy grandes , en el primer problema que resuelvas, puede ser infalible.
> Nunca vas a pecar de usar  epsilons muy pequeños	  
En cuanto se actualicen.

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.40.42.png)

> Algoritmo para sacar soluciones óptimas alternativas.  

> Nos ayuda a sacar una solución no dominada  


## Programación por metas
Nos dan pesos.
Es muy difícil para un decisor, porque tiene que comparar
Lo más fácil es dar unas metas, j¡uno de los objetivos

^fi son cada una de las metas con objetivos.

Voy a comprar uno coche por 20K€, intento gastar menos de 20K€, consumo, a ser posible quiero acercarme a 4 quedarme por debajo de 10

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.47.40.png)
Cada objetivo se acerque a una meta, ya sea por arriba o por abajo. En ambos casos tengo la misma penalización.

No es un problema lineal, hay que linealizarlo

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.49.38.png)

- d+: Esta por encima de la meta
	- lo que me sobrepaso por encima de la meta
- d- : calculo lo que estoy por debajo de la meta
- d+ + d- = nos queda el valor absoluto

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.51.36.png)



Ejemplo:
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.52.49.png)

Resolvemos por método de simplex

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.54.35.png)


Además podemos ponderar las soluciones

A más grande la Lambda -> Prefiero quedarme corto que pasarme. Porque estamos minimizando.
Más grande la lambda, se va a hacer cero más rápido, y la otra tendrá más libertad.
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.55.54.png)

Ejemplo
¿Qué estamos diciendo al problema?
Queremos alcanzar el primer objetivo	, quedándonos por debajo
Queremos alcanzar el segundo objetivo,  quedándonos por encima 2 veces más.
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.57.59.png)


### Casos especiales: Dentro de las metas , dar prioridades
Una vez resueltos los objetivos de la primera prioridad, buscamos las siguientes objetivos de la siguiente prioridad. Manteniendo las soluciones anteriores encontradas.

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2017.59.49.png)


EJEMPLO.

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-07%20a%20las%2018.02.41.png)

La primera prioridad se reserva para las restricciones.
Solo consideramos las restricciones, luego miramos la segunda prioridad

> Lo primero que vamos a hacer es comprobar que el problema es factible  

Parecido a lexicographic.

Solución
- Prioridad 1.
	- que se cumplan todas las restricciones
		- ¿cuál sería el objetivo?
		- pongo las variables de exceso y defecto en la primera restricción
		- x1+3x2+d-1 -d1+ = 24
			- min P1(d+1
			- Se tiene que cumplir que la variable `d1+` de exceso sea 0, para que sea <= 24
			- `min P1(d1+ …`
		- 2ª restricción
			-  `min P1(d1+ + d2+`
		- 3ª restricción
			-  `min P1(d1+ + d2+ d3+)`
- Prioridad 2 
	- >= 21
			-  `min P1(d1+ + d2+ d3+) + P2(d4-)`
- Prioridad 23
	- Maximizar -> cambiamos de signo a la función z2.
			-  `min P1(d1+ + d2+ d3+) + P2(d4-)+P3(d5+)`

```
sa:
# Prioridad 1
x1+3x2+d1- - d1+ = 24
2x1+x2+d2- - d2+ = 18
x1+x2+d3- - d3+ = 10
# Prioridad 2
2x1+3x2 + d4- - d4+ = 21
# Prioridad 3. OJO! Está cambiado de signo
4x1 + 2x2 + d5- - d5+ = 12
```


¿Qué valor objetivo tiene que dar para que el problema sea factible?
todas las variables d1+ + d2+ + d3+ tiene que ser 0 para que sea factible
Si z*1 != 0 , no es factible. Si algún di+ es != 0 , no es factible.

Problema 1. `Z*1=0`
```
x1 + 3x2 + d1- - d1+ = 24
2x1+x2+d2- - d2+ = 18
x1+x2+d3- - d3+ = 10
x,d >= 0
```
Problema 2
```
x1 + 3x2 + d1- - d1+ = 24
2x1+x2+d2- - d2+ = 18
x1+x2+d3- - d3+ = 10
d1+ + d2+ + d3+ = 0
2x1+3x2 + d4- - d4+ = 21
x,d >= 0
```
Problema 3
```

```

La solución de Lambda nos dice:
2 Unidades por encima a la contaminación que quería llegar.



**OJO!!**
> !!! IMPORTANTE !!! Qué  d cogemos?  
> <= -> di+  
> >= -> di-  
> = -> di+ + di-  


> Objetivo VS Restricción; ¿ Qué pasa cuando no se cumplen	?  
Objetivo, intentamos acercarnos a la meta lo máximo por encima o por debajo, y la solución te da lo más cerca puedes quedarte
Una restricción te hace el problema infalible.

- [ ] Test próximo lunes
	- desde antes de las 6:00 a las 23:59
		- el primer test dura unos 15 minutos
	- Problema de elegir pesos 
	- En cualquier momento de ese intervalo
	- en cuanto te conectas, el número de preguntas, tiempo.
	- Te puedes mover y contestar todo lo que quieras
	- hasta que no lo envías, no se guarda
		- si no lo hemos podido enviar, avisarle para que busque en el historial
	- 10 Preguntas de un saco de 20 a 30,  diferente orden.
		- preguntas fáciles
	- Solo se puede hacer una vez.
	- La nota saldrá cuando la última persona entregue su ejercicio.


- Prácticas muy sencillas
	- Recocido simulado, para colocar las reinas sin que se maten entre sí
	- Es lo básico
	- podemos hacer lo que queramos
		- Podemos resolverlo hasta 1000 reinas, viendo como crece el tiempo
			- es el tiempo de computación
		- o con otro algoritmo
	- La mejor práctica vale 10, y las demás se comparan
	- pdf sin faltas ortográficas
	- Hay que presentar el algoritmo (pseudocódigo) y un ejemplo para que se entienda bien
	- La implementación es opcional, pero hay que compensarla con un estado arte. Del año, la variación y distintas variantes que han surgido.

Alfonso explicará 2 algoritmos más. (2 semanas) y empezarán las presentaciones.
Se planificará. Se puede cambiar un grupo por otro.
Los 3 miembros tienen que hablar de 3 problemas. Problema por persona. No tiene que ser de tiempo simétrico.
La implementación podemos usarla nosotros de cualquier sitio. Lo importante es entender los parámetros y explicarlo.



# a07-05 Métodos de proximidad y diversidad

- Alfonso
- 20191021

O expone uno cada día. O los tres cada vez.

4 … de noviembre, 3 y 16 de diciembre. 
Las preguntas van a todos

## Prácticas
Aplicar una metaheurística en los problemas test

1. Obtener soluciones (Aproxime, Profundidad, Intensificación, Convergencia)
	1. se calcula calculando la distancia a la frontera de pareto
2. mantener la diversidad dentro de la población (Diversificación)
	1. cómo representa, si lo representa todo o parte de él
	2. las medidas entre las solucione deberían ser similares

Si el problema es convexo, discreto y uniformidad. Cada metaheurística tendrá mayor dificultad

### Test 1
Los problemas se van a diferenciar en cómo es su conjunto de soluciones
Bueno para problemas convexos

### Test 1
Para problemas no convexos

### Test 3
Para problema no continuo, converge a cada uno de ellos.

### Test 4
Tiene un óptimo global, pero muchos óptimos locales.
La mayoría se quedan en locales.

### Test 5
Discreto, Muchos óptimos locales

### Test 6
Junto al 5º son los dos más complicados


## ¿Qué significa que converja o diversifique bien?
### Métodos para la **proximidad**
1. Proporción de error
	1. cuantas no están en el conjunto no dominado
	2. Q=Tamaño 
	3. Qi=1 ; e = error (1, no error 0)
	4. Cuanto más grande sea el error 
	5. se utiliza poco, porque es muy sencilla
	6. pero es muy rápida
	7. 3 en conjunto de pareto, 5 soluciones totales -> `ER = 3/5 = 0.6`
2. cobertura del conjunto
	1. Soluciones dominadas / Soluciones que estamos comparando
	2. Las soluciones serían similares al ejemplo anterior -> `ER = 3/5 = 0.6`
3. ~Distancia generacional~ : de las mejores
	1. GD = /Q
		1. La distancia euclídea 
		2. entre el número de soluciones
	2. Siempre debemos comparar el mismo número de puntos para cada metaheurística
4. Máximo error de la frontera óptima de Pareto
	1. Te calcula la máxima distancia
	2. nos quedamos con el peor de los casos
	3. Se utiliza mucho en economía, cuando quieres evitar la máxima pérdida

### Métodos para la **diversidad** (para conjuntos continuos)
1. Espaciado: Resta de cada punto ^2
	1. Calculamos la distancia media entre los puntos obtenidos
	2. Estamos calculando la varianza, desvianza típica
	3. Nos gustaría que la dispersión respecto a la media sea 0
		1. todas las distancias iguales, igual que la media
	4. Que sean equidistantes
		1. El **problema** es que no mide 
2. Extensión: 
	1. El problema se consigue midiendo entre los extremos
		1. y dividiéndolos entre el número de puntos que hemos generado de la frontera
	2. Además se mide la distancia entre el extremo óptimo y 
3. Máxima extensión
	1. solución simple y mala
	2. Se miden únicamente los extremos
	3. Solo compara la máxima amplitud
4. Medida de desviación como la Chi cuadrado
	1. Si tengo 8 puntos en el conjunto no dominado y 24 puntos de la metaheurísica
	2. cuantos puntos de la metaheurística deberían estar próximos al conjunto
	3. Cuantos puntos hay próximos a cada punto óptimo, y los comparamos con los predichos por la chi cuadrado
	4. Cuanto más alto ese valor, mejor

La medida que se suele usar es la ~**Distancia Generacional Extendida**~


### Métodos para comparar la **proximidad y la diversidad**
1. HiperVolumen
	1. se calcula el peor punto, el antiideal
	2. se calcula y suma el área de cada punto de Q. (Región/Rectágulo que es peor que el punto mismo)
		1. cuanto mayor área domine, mejor es la MH
2. Superficie de logro basada en métricas estadísticas
	1. considerar diferentes rectas y mirar el orden de cada una de las rectas
	2. se calcula el histograma y la distribución
	3. contraste de smirnov
	4. Es mucha estadística para algo que podrías hacer con un hipervolumen
3. Métricas ponderadas
	1. 

Los mejores son el **SPEA** y el **NSGA**
En todas las prácticas hay que comparar las 6 MH



# a07-05 Recocido Simulado

- Alfonso
- 20191021

- Decrecimiento lento:
	- 
- Decrecimiento rápido:
	- máxima entropía
	- quedamos atrapados en una solución local

## Optimización Local y Global
- Local: El mejor en un entorno, en un conjunto de puntos
- Global: el mejor de todo el entorno de la función

## Entorno en Optimización continua. Función
## Entorno en problemas de optimización combinatoria

## Método de máximo descenso




## **Búsqueda aleatoria pura**
## **Problema de optimización combinatoria**
## **Métodos de multicomienzo**

#
- Recojo una solución (aleatoria o cerca del óptimo)
- MH trayectoria, trabaja solo con una única solución
- Cojo una solución del entorno aleatoria
- la comparo con ella
- si es mejor -> la cojo con P=1
- si es peor -> la cogemos solo si P=0.X
	- la probabilidad depende de un parámetro
	- Temperatura de ese momento
	- mayor temperatura, mayor probabilidad de aceptar 
	- si la solución es muy mala,  es menos probable que la cojamos
	- `p(i) = exp(- (f(y) - f(xi))/Ti)
- Primero exploración o diversificación
- La temperatura debe quedarse constante si la temperatura desciende progresivamente, quedando constante
	- Para poder comparar con las cadenas de Markov y demostrar su convergencia.

- Problema de airbus
	- han cerrado el centro del aeropuerto en barajas, y lo han movido aquí a getafe
	- 3000 personas trabajando , y las recogen en autobús
	- Calcular rutas óptimas
	- Solución
		- clasificar a los trabajadores
		- una vez 
		- 

# a17 03.00 COMPUTACIÓN EVOLUTIVA I 
20191014 - computación evolutiva
alfonso
`03 3.1 Computación Evolutiva`


## Algoritmo genético
Tiene poblaciones, Selecciona los que mejor se adapten (mejor resultado en la función fitnes) , los mezcla, muta y es un ciclo.

- Generar (aleatoriamente) una población inicial
	- a no ser que tengamos una idea de dónde encontramos una solución óptima
	- si hay falta de diversificación , caeremos en un óptimo local
- Calcular la aptitud de cada individuo
	- Según la función fitness 
	- min/max función objetivo
- **Seleccionar** probabilísticamente según la base aptitud
	- mejores individuos, tendrán más probabilidad de reproducirse
- Aplicar operadores genéticos ( **cruce y mutación**) para generar la siguiente población
	- probabilidad de cruce > que mutación
	- la mutación aporta diversidad para no caer en óptimos locales
- ciclo hasta que la condición se satisfaga

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2017.21.04.png)


- La evaluación de una solución significa calcular el valor de la función objetivo y la violación de restricciones 
	- a parte de la función a optimizar
	- también aparecen las restricciones que no se cumplen
		- solemos poner una penalización por cada restricción que no se cumple
- El algoritmo genético enfatiza la importancia del cruce sexual (operador principal) sobre el de la mutación (operador secundario), y usa selección probabilística. 

### 5 componentes necesarios para aplicar un algoritmo genético
- Una representación de las soluciones potenciales del problema
- Una forma de crear una población inicial de posibles soluciones (normalmente un proceso aleatorio)
- Una función de evaluación que juegue el papel del ambiente, clasificando las soluciones en términos de su “aptitud”
- Operadores genéticos que alteren la composición de los hijos que se producirán para las siguientes generaciones
- Valores para los diferentes parámetros que utiliza el Algoritmo Genético (tamaño de la población, probabilidad de cruce, probabilidad de mutación, número máximo de generaciones, etc.)
	- Grande -> Más tiempo de computo
	- Pequeña -> menos diversidad

### Complejidad
- Complejidad del algoritmo genético
	- np complejos en tiempo poliminial, dependiendo de la población
	- depende de las variables
	- Son de las más usadas
		- inconvenientes: gastan mucho tiempo porque se trabaja con poblaciones
		- Muy sencillas de entender


### Población
- Tamaño
	- Las poblaciones pequeñas corren el riesgo de no cubrir adecuadamente el espacio de búsqueda, mientras que el trabajar con poblaciones de gran tamaño puede acarrear problemas relacionados con el excesivo coste computacional. 
	- Goldberg efectuó un estudio teórico, obteniendo como conclusión que el tamaño óptimo de la población para cadenas de longitud l, con codificación binaria, crece exponencialmente con el tamaño de la cadena. 
	- Alander, basándose en evidencia empírica sugiere que un tamaño de población comprendida entre l y 2I es suficiente para atacar con éxito los problemas por él considerados. 
- Inicial
	- aleatoria
	- Habitualmente la población inicial se escoge generando cadenas al azar, pudiendo contener cada gen uno de los posibles valores del alfabeto con probabilidad uniforme. 
- Función objetivo
	- La regla, general para construir una buena función objetivo es que ésta debe reflejar el valor del individuo de una manera "real", pero en muchos problemas de optimización combinatoria, donde existe gran cantidad de restricciones, buena parte de los puntos del espacio de búsqueda representan individuos no válidos.
	- Para este planteamiento en el que los individuos están sometidos a restricciones, se han propuesto varias soluciones.
	- La primera sería la que podríamos denominar **absolutista**, en la que 'aquellos individuos que no verifican las restricciones, no son considerados como tales, y se siguen efectuando cruces y mutaciones hasta obtener individuos válidos, o bien, a dichos individuos se les asigna una función objetivo igual a cero.
	- Otro enfoque está basado en la penalización de la función objetivo. La idea general consiste en dividir la función objetivo del individuo por una cantidad (la penalización) que guarda relación con las restricciones que dicho individuo viola.
	- Un problema habitual en las ejecuciones de los Algoritmos Genéticos surge debido a la velocidad con la que el algoritmo converge. En algunos casos la convergencia es muy rápida, lo que suele denominarse convergencia prematura, en la cual el algoritmo converge hacia óptimos locales, mientras que en otros casos el problema es justo el contrario, es decir se produce una convergencia lenta del algoritmo.
	- El problema de la convergencia prematura, surge a menudo cuando la selección de individuos se realiza de manera proporcional a su función objetivo.
	- En tal caso, pueden existir individuos con una adaptación al problema muy superior al resto, que a medida que avanza el algoritmo "dominan" a la población. Por medio de una transformación de la función objetivo, en este caso una comprensión del rango de variación de la función objetivo, se pretende que dichos "superindividuos" no lleguen a dominar a la población.

*Problema de Hamming* : quitar soluciones, reducir la población si son muy cercanas
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2017.29.23.png)


## Algoritmos genéticos binarios
Los que más se utilizan. Y los más sencillos.

- EJEMPLO: Minimizar el coste del material de fabricación de un cilindro 
cuyo volumen sea de al menos 300ml. 
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page10image23958192.jpg) 
donde d es el diámetro y h la altura (0 ≤ d*,*h ≤ 31). 

1. **Modelizar** para entender el problema
	- podemos resolverlo por un método exacto?
2. C = es lo qu me cuesta cada K 
	- min el coste -> `C * (Área del cilindro + las dos tapas)`
		- min coste = C(2πrh + 2πR2)
			- restricciones s.a:
				- volumen sea >= 300 ml : `πr^2*h >= 300`
				- altura menor de 31cm : `0<=h<=31`
				- diámetro menor de 31cm : `0<=d<=31`
3. El problema tiene 2 variables: d y h
4. función no lineal
	- Para solucionarlo, necesitaremos usar Algoritmos genéticos

- SOLUCIÓN
	- lo podemos hacer con variables 
	- discretizar (podríamos hacer fuerza bruta, calculando todos los posibles valores: 31*31 y quedándonos con las factible)
		- usaremos variables binarias
		- para representar d usamos 5 bits `d = (0,0,1,0,1)`
			- `h = (0,1,0,1,1)`
		- partes
			- gen
			- cromosoma
			- alelo
	- 1ª población: Generamos 6 posibles cilindros
		- usando funciones aleatorias
		- los que no son factibles, los penalizamos
			- y la selección natural los acabará eliminando
			- la penalización puede ir acorde con cuanto de mala es la solución
	- Seleccionamos los mejores individuos
		- en el ejemplo, cuanto menos cueste más probable que se seleccione
		- DIFERENTES MÉTODOS DE SELECCIÓN
			- selección por **Toreno**
				- se cogen 2 soluciones y nos quedamos la mejor de cada pareja
				- solo dos veces cada uno de ellos
			- **proporcional**
				- **mecanismo de la ruleta**
					- cada solución según su fitness 
					- mayor fitness mayor probabilidad (más boletos)
					- se tira la ruleta una vez por cada miembro de población que nos quedaremos, en nuestro ejemplo 6 veces.
				- **ruleta de restos estocásticos**
				- **Muestreo Universal Estocástico**
					- Sólo un número aleatorio es elegido para el proceso de selección completo, r.  
				- Método de **selección ordenada**
					- Orden 1
					- Orden N
					- aptitud = al orden en la lista
			- clasificación
				- no nada bueno
		- Operador de cruce
			- 2 posiciones de cruce
				- tras haber seleccionado, se hace un cruce
				- un trozo del cromosoma se intercambia entre los padres
				- si tengo 2 padres, tendré 2 hijos
				- probabilidad de cruce, valor alto
					- algunos miembros no se cruzan
			- Cruces uniformes
				- hay una probabilidad de intercambio
		- Operador de Mutación `pm`
			- se mutan todos los genes que marca la probabilidad
		- Reloj de mutación
			- `1/pm` , saltando `-pmLN(1-r)` siendo r un valor aleatorio a mutar
			- se usa mas, porque ahorra generar más números aleatorios
	


# # a17 03.00 COMPUTACIÓN EVOLUTIVA II
20191014 - computación evolutiva
alfonso
`03 3.2 Computación Evolutiva`

- Las binarias tienen el fallo que soluciones próximas, tienen distancia de hamming muy alta.
- Segundo fallo: longitud del cromosoma

- Hay que definir nuevos cruces


## Algoritmos Genéticos con parámetro real ; 

### Cruce lineal (Wright, 1991) 

- i : que variable estoy considerando
- t : iteración en la que estoy
- Los hijos deberían estar cerca de los padres
	- Se coge la media (el hijo que está en el medio de los 2)
	- Se coge uno a la izquierda y otro a la derecha
		- se suele coger la misma distancia de un padre a la media
- Se cogen los 2 hijos que den mejor fitness, 

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.12.05.png)



### Cruce Naive
Se cogen los padres y se intercambian la información, de modo similar al binario
Se cambia una de las componentes y se intercambian. Es como hacer un rectángulo e intercambiar los padres por el valor de los otros dos ángulos
No suele dar buenos resultados

### Cruce Mezcla (Blend)  (BLX-å) - Recombinación por Aleación
Si los hijos caen en en medio -> favorecemos la explotación
Si los hijos caen en uno de los lados de los padres, se favorece la exploración.
Explotación == unificación

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.20.53.png)

ui = 0 -> cojo el extremo inferior
ui = 1 -> cojo el extremo superior
=> cogemos cualquier valor en el intervalo 

Si å = 0 , cogemos cualquier valor en el intervalo

> Con BLX-0.5 es análogo con el lineal, pero se cogen soluciones directamente.  

Cuanto más juntos los padres, sus hijos más próximos

### Cruce Binario Simulado
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.26.04.png)

Si ß < 1 -> cruce es contractivo. los genes de los hijos se encuentran localizados entre los padres este tipo de algoritmos se localizan en la explotación

ß >1 -> exploración
ß = 1 -> los hijos son los padres

### Mutación aleatoria
Cualquier hijo que esté entre los padres

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.28.46.png)

No da buenos resultados

### Mutación no uniforme
Movernos por un padre, pero con una distribución distinta


### Mutación distribuida normalmente
Más utilizado

Una variable al confirmamos como antes.
El parámetro que damos es la desviación típica
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.31.03.png)

### Mutación Polinomial 
…

## Conclusión
Puede que funcione muy bien para un problema, pero puede ser que se comporte como una búsqueda aleatoria

Es mejor seleccionar la mejor metaheurística

> Normalmente se implementan varias MH y usas el que mejor resultado da.  
>   
> RS, BT, Genéticos  

> En industria 4 , una solución factible suele ser suficiente, si encima es óptima, es perfecto.  

> Los algoritmos genéticos convergen a la media  

## Aplicaciones
- Optimización (estructural, de topologías, numérica, combinatoria, etc.) Aprendizaje de máquina (sistemas clasificadores)
- Bases de datos (optimización de consultas) Reconocimiento de patrones (por ejemplo, imágenes)
- Generación de gramáticas (regulares, libres de contexto, etc.) Planeación de movimientos de robots
- Predicción

## Estrategias evolutivas
No tienen cruce, y solo aplican el operador de mutación.


- Las estrategias evolutivas fueron desarrolladas en 1964 por un grupo de estudiantes alemanes de ingeniería encabezado por Ingo Rechenberg. Su objetivo era resolver problemas hidrodinámicos de alto grado de complejidad. 

- La versión original (1+1)-EE usaba un solo padre y con él se generaba un solo hijo. Este hijo se mantenía si era mejor que el padre, o de lo contrario se eliminaba (a este tipo de selección se le llama extintiva, porque los peores individuos tienen una probabilidad de cero de ser seleccionados).
- En la (1+1)-EE, un individuo nuevo es generado usando:
- ![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page14image23887504.png) 
- donde t se refiere a la generación (o iteración) en la que nos encontramos, y N(0, fi) es un vector de números Gaussianos independientes con una media de cero y desviación estándar.


EJEMPLO: 
Las estrategias evolutivas siempre trabajan con valores reales

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.41.18.png)
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.42.19.png)

Comparamos el padre con el hijo y como maximizamos, nos quedamos con el más grande

- Diferencia, generamos mu padres con lambda hijos, nos quedamos con los mu mejores.
	- Los hijos compiten con los padres
- De los mu padres, generamos lambda hijos, y de esos hijos, nos quedamos con los mejores.
	- solo nos quedamos con los hijos

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.43.45.png)

### Convergencia de las Estrategias evolutivas
- éxito 1/5
	- el cociente entre mutaciones exitosas y el total esté en 1/5
		-  si está por debajo, hay que aumentar la desviación típica
		- si está por encima hay que reducir la desviación típica

Thomas Back, 1/7 para mu+L -EE


## Auto-Adaptación
## Programación Evolutiva: 

En vez de la Normal(0,1)
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-14%20a%20las%2018.48.24.png)

## Estrategias Evolutivas vs Programación Evolutiva 
Estrategia evolutiva -> a nivel de , se permite le recombinación
Programación evolutiva -> a nivel de especie, no se permite la recombianción
La Programación Evolutiva usa normalmente selección estocástica, mientras que las estrategias evolutivas usan selección determinística. 
Ambas técnicas operan a nivel fenotípico. 
La programación evolutiva es una abstracción de la evolución al nivel de las especies, por lo que no se requiere el uso de un operador de recombinación (diferentes especies no se pueden cruzar entre sí).
En contraste, las estrategias evolutivas son una abstracción de la evolución al nivel de un individuo, por lo que la recombinación es posible. 
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page24image25167744.png) 

## Algoritmos Genéticos vs otras técnicas evolutivas 
El AG usa selección probabilística al igual que la Programación Evolutiva, y en contraposición a la selección determinística de las Estrategias Evolutivas. 
El AG usa representación binaria para codificar las soluciones en un problema, por lo cual se evoluciona el genotipo y no el fenotipo como en la Programación Evolutiva o las Estrategias Evolutivas. 
El operador principal en el AG es el cruce, y la mutación es un operador secundario. En la Programación Evolutiva, no hay cruce y en las Estrategias Evolutivas es un operador secundario. 
Ha sido demostrado (Rudolph, 1994) que el AG requiere de elitismo para poder converger al óptimo. 
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page25image25483264.png)
Los AGs no son, normalmente, auto-adaptativos. 


### Diferencias de las técnicas evolutivas con respecto a las tradicionales 
Las técnicas evolutivas usan una población de soluciones potenciales en vez de un solo individuo, lo cual las hace menos sensibles a quedar atrapadas en mínimos/máximos locales. 
Las técnicas evolutivas no necesitan conocimientos específicos sobre el problema que intentan resolver. 
Las técnicas evolutivas usan operadores probabilísticos, mientras las técnicas tradicionales utilizan operadores determinísticos. 
Aunque las técnicas evolutivas son estocásticas, el hecho de que usen 
operadores probabilísticos no significa que operen de manera análoga 
a una simple búsqueda aleatoria. 

### Ventajas de las Técnicas Evolutivas 
- Simplicidad Conceptual. Amplia aplicabilidad.
- Superiores a las técnicas tradicionales en muchos problemas del mundo real.
- Tienen el potencial para incorporar conocimiento sobre el dominio y para hibridizarse con otras técnicas de búsqueda/optimización.
- Pueden explotar fácilmente las arquitecturas en paralelo. Son robustas a los cambios dinámicos.
- Generalmente pueden auto-adaptar sus parámetros.
- Capaces de resolver problemas para los cuales no se conoce solución alguna.

## Algoritmos Evolutivos 
- MOEA : Algoritmos Evolutivos Multi objetivos
	1.  Algoritmos que no incorporan el concepto de dominancia de Pareto en sus mecanismos de selección (ej. Aproximaciones que usan funciones de agregación lineal).
	2.  Algoritmos que ordenan la población basándose en la dominancia de Pareto (ej. MOGA, NSGA, NPGA, etc.).

Históricamente, podemos considerar la existencia de dos generaciones Principales de MOEA:
		1.  **Primera Generación**: Caracterizado por el uso de ordenación de Pareto. Algoritmos relativamente simples. Otras aproximaciones (más rudimentarias) fueron también desarrolladas (ej. Funciones de agregación lineal). Es también digno de mencionar VEGA, el cual es una aproximación basada en la población (no basada en Pareto).
			- VEGA MOGA NSGA NPGA
		2. **Segunda Generación**: El concepto de elitismo es introducido en dos formas principalmente: usando selección (μ+λ) y usando una
    población secundaria externa.
	- SPEA SPEA2, NSGA-II, PAES, microGA para optimización multiobjetivo.



# a17 03.00 INTRODUCCIÓN A LA COMPUTACIÓN EVOLUTIVA 
20191014 - computación evolutiva
alfonso
`3.0 Computación Evolutiva`


- Lamarck
	- Los sucesos físicos se 
	- si a un ratón siempre se le cortaba la cola, al final se heredaría
- Darwin
	- selección natural
	- los individuos compiten, el más fuerte sobrevive, se reproducen, mejores descendencias
- Weisman
	- germoplasma
	- células con información hereditaria
	- 
	- somáticas, que no transmitían nada
	- Experimento para refutar Lamarck
		- 1500 ratas y 22 generaciones
		- cosas que no usamos , tienen a desaparecer
- Mendel
	- leyes básicas de herencia
		- guisantes de colores
- Baldwin
	- seres vivos con mejor aprendizaje son los que sobreviven

Neo-Darwinismo

- **Pensamiento evolutivo**: nos quedamos (seleccionar) lo mejor, mezclar (reproducción), mutación, competencia.

- J. Bremermann
	- reproducción, selección y mutación
- Fogel
	- Programación evolutiva 1960
- Peter Bienert, Ingo Rechenberg y Hans Paul Schwefel
	- estrategias evolutivas
		- solo con la mutación, se obtienen resultados bastante buenos

# 



# a17-06 Recocido Simulado II
- Alfonso
- 20191028
- `04 Tema 4.1. Recocido Simulado Uniobjetivo.pdf`
- Pag 32

1. Se escoge una solución del entorno, puede ser random.
2. Algoritmo trayectorial -> siempre se evalúa una única solución
3. Si es mejor,  actualizamos nuestra solución
	1. Si es peor,  la aceptaremos dependiendo una probabilidad en función de la temperatura
		1. Método de metrópolis: Uniforme 0,1
		2. Si es mayor, la aceptamos, si no la rechazamos
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-28%20a%20las%2017.06.08.png)


> Converge con P=1 si la temperatura diminuye suficientemente lenta  
> CMTD,   

En la práctica, no se disminuye tan lentamente. Por lo que solo se puede garantizar una solución buena y no la óptima.


![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-28%20a%20las%2017.10.42.png)

- Aceptación -> Función de volmart (exp) 
- Criterio de parada ->
	- si no cambia la solución en x iteraciones
	- o la mejora es un porcentaje muy pequeño durante un % de soluciones
- Evaluación -> hay que utilizar la más rápida coputacionalmente, porque por cada iteración hay que evaluar al menos 2 soluciones

- **Temperatura**
	- Programación estática
		- los parámetros no cambian durante la ejecución
		- **recocido geométrico**
			- Cada L iteraciones la temperatura se multiplica por å = ~0.95
	- Programación dinámica
		- Depende del número de iteraciones
		- **recocido geométrico**
			- å no es una constante, sino que depende del número de iteraciones.
			- 

**Aceptación** : se suele aceptar la función de volmart, porque tiene en cuenta sus parámetros principales (Temperatura y cómo de buena/mala es la siguiente solución respecto a la actual )

- **Reglas de parada**:  € = 1 .. 5 %
	- L = Nº de pasos que no cambia la solución
	- si el % de aceptadas en L pasos es muy pequeña


## Variantes y mejoras técnicas
Recocido simulado:
Vamos quedándonos 

Han surgido muchos métodos para evitar calcular la exponencial.

- Exponenciación aproximada: En vez
- Iniciar en soluciones mejores
- Paralelización : No es muy paralelizable


## Problema de optimización continua
- Parámetros a dar:
	- r: Definir el entorno (soporte) Intervalo cerrado.
		- [x-r, x+r]
		- cuanto más grande es el intervalo, mayor diversidad
		- cuanto más pequeño, mayor intensificación
	- Tª inicial: 4000
		- depende del problema
		- para calcular una temperatura inicial
		- correr 100 veces con una temperatura, si no ha aceptado el 90% -> aumentamos la temperatura
		- si ha aceptado más -> la bajamos
	- Solución inicial
		- aleatoriamente entre 
	- L = Nº de iteraciones que la temperatura debe permanecer constante sin bajarla
		- 10 .. 100
		- cada L iteraciones, la temperatura decrece
		- L y alpha 
		- Cuanto más alta mejor. Porque ganas en diversificación. Pero será muy lento.
		- Para que converge, L debería tender a infinito.
	- Cómo decrecer la temperatura
		- geométrico: å = 0,95


> De una iteración a otra, la solución puede cambiar !!!  
> Es estocástico, probabilístico  

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-28%20a%20las%2017.39.16.png)


## Problemas a los que aplicar
- Procesamiento de imágenes
- problema del viajero
- circuitos electrónicos
- …

## Ventajas
Solución de buena calidad
**Método general**, se puede aplicar a cualquier problema de optimización.
Gran flexibilidad para las restricciones

## Inconvenientes
- Parámetros que estimar
- Tiempo de computación, depende de los parámetros y la función objetivo


## Parámetros
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-28%20a%20las%2017.48.18.png)
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-28%20a%20las%2017.48.38.png)


## Variantes
No son muy aceptadas
Son utilizadas para aumentar la velocidad.

### Método del Umbral (1991) 
No calcula la probabilidad, sino cómo de mala puede ser una solución para ser aceptada.
No se tiene en cuenta a la temperatura

Es más rápido, porque no hay que calcular probabilidades, ni el método de metrópolis.

Generalmente da una solución peor que el RS clásico.
Se utiliza cuando queremos una solución rápida.

T Grande -> Diversificación
T Pequeña -> Intensificación 

### Método de Gran Diluvio (Función de Maximización)
Tenemos unas islas, y una cantidad de agua. Si va lloviendo, el agua sube y la superficie para pasar de una isla a otra es más pequeño.
Parámetros:
- Cantidad de lluvia que cae
- Cantidad de agua
- f = función objetivo > Nivel del agua -> aceptamos
- Cantidad de agua += cantidad de lluvia

Diferencias con M. Umbral :
Al principio 



### Método de Record to record travel
Diferente nombre, misma filosofía de RS.

### Microcanónico
Usa energía cinética + potencial
Se basa en umbrales 

### IDEA
FRIO - CALOR
Ráfagas de búsqueda+intensificación

# a17-06 Recocido Simulado MULTIOBJETIVO

- Alfonso
- 20191028
- `04 Tema 4.2. Recocido Simulado Multiobjetivo.pdf`
- Pag 0

## Requisitos
1. Solución del entorno y compararla con la anterior

### ¿Cómo comparamos si es multi objetivo?
3 casos:
- a) SOLUCIÓN MEJOR: Si la solución actual es mejor en todos los objetivos -> se acepta con P=1
La solución actual domina a la anterior

- b) SOLUCIÓN NO DOMINADA (igual de buenas/malas): Si tenemos una solución que no domina (es mejor solo en algunos objetivos).
Entonces la aceptaremos con alguna P baja.
	- Dependiendo de como tratemos este caso es una variación diferente
	- Si la aceptas como a , ganamos en diversificación
	- si lo consideramos como c, ganamos en intensificación

- c) SOLUCIÓN PEOR: Si la solución actual es peor en todos los objetivos, hay que aceptarla con una P más baja aún.

- La función de evaluación es ponderada en todos los objetivos

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-28%20a%20las%2018.30.45.png)

### Solución eficiente
Si: 
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-10-28%20a%20las%2018.29.01.png)

## Método de SERAFINI
Potencialmente Eficiente = PE
Es eficiente según las soluciones que hemos generado.

Diferencia:
Probabilidad de aceptar : depende de:
- temperatura
- y funciones objetivo moderadas (lambdas)

### Reglas
exponencial de la máxima desviación.
	(O tal vez mínima, el profe no se aclara)
Se coge el peor de los casos


## ????
## Método Mosa

# Presentación y Test
Hay que hacer presentación de 20 minutos sobre NPGA

# a17-10 COLONIAS DE HORMIGAS
- Alfonso
- 20191118
- `05 Tema_5._ColoniasHormigas.pdf`

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

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.15.01.png)

## La hormiga artificial
Mecanismo probabilístico de construcción de soluciones al problema (un agente que imita a la hormiga natural).

Además tiene una información heurística 
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.21.03.png) adicional.

### Problema del viajante (TSP) o cartero chino
Se puede resolver por esta MH.

Hormiga artificial debe elegir un camino con una probabilidad que depende de la cantidad de feromonas (Tau) y la información heurística que se tenga sobre esos arcos ().

La información heurística qué se tiene es la distancia entre dos nodos. Suele ser la inversa de la distancia.

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.24.56.png)

å = 0 -> solo nos fijamos en el heurístico
ß = 0 -> solo nos fijamos en las feromonas

### Actualización de la feromona

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.34.32.png)
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-11-18%20a%20las%2017.34.46.png)

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