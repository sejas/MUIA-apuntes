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



# a07-03 Introducción , visión general 
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


![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2017.15.12%202.png)

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
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2017.21.31%202.png)

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

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2017.26.33%202.png)

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

![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2017.42.03%202.png)

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
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page21image5584496%202.png) 

**Mathheuristics**: mezcla de soluciones matemáticas y metaheurísticas

## Clasificaciones
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page23image6005280%202.png) 
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
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/page30image5900528%202.png) 

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
![](a07%20Bu%CC%81squeda%20inteligente%20basada%20en%20metaheuri%CC%81sticas/Captura%20de%20pantalla%202019-09-30%20a%20las%2018.08.46%202.png)

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