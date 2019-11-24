# a17 Ingeniería Lingüística

# a17-02 Herramientas de Ingeniería Lingüística
20190925

Jesús Cardeñosa Lera -> Coordinador

Laura Martín, Lingüista
Pertenece al CAID, fue la primera alumna
Recursos lingüísticos	y semánticos

Variabilidad lingüística, comas, puntos, orden.
Y respetar la coherencia y cohesión del texto.


## Generador de Lenguaje
Datos puros que se compran.
Las crónicas se generan 

[CRÓNICAS DE FÚTBOL](http://35.205.94.71:8080/leo/upload.action;jessionid=1BDED6)
http://35.205.94.71:8080/leo/
http://35.205.94.71:8080/gt/

Cada dato tiene variabilidad lingüística	
El washington post fue el primero
Los datos se pasan a reglas.

> No enseñes código, enseña un demostrador comercial  

Generación de informes crónicas para:
- Partidos de futbol
- Review de Móviles
- Bolsa

> Generación de lenguaje es sencilla  

> El paseo e interpretación es lo realmente difícil  

## Herramientas
### Tesauro (TesaurVAI++)
Entre 2000 y 5000 términos. Es muy laborioso. 
La profundidad cuenta.

Cargar textos 
Modificar palabras vacías

- Demo 1 
	- 30 sentencias judiciales del tribunal supremo
	- Saca 70.700 términos de una a 7 palabras
		- 564 y dónde está
	- Dejaron de comercializarla porque les hacían competencia por muy poco dinero
	- Extraemos las combinaciones de recursos, que aparecen y se repiten en estas sentencias
	- Son términos planos, ajenos unos a otros

Ontologías no están
TG -> término genérico
TE -> término específico
TR -> término relacionado
UP -> Varias opciones (Lápiz)
USE -> Menos frecuente (Lapicero)

Se va haciendo un árbol

## Clasificador
### Clasificador con glosario (Supervisado)

Con Glosario (un tesaurio)  por debajo
> Hay medidas para hacer un ranking en un clasificador  
Depende del tamaño del documento.

Se calcula la frecuencia de los distintos términos.

### Clasificador sin glosario
Le das 100 documentos y te los ordena por carpetas.
Carpeta 1, 2,3 ; Cuando las abres descubres que la 1 son actas, la 2 son curriculums.

El objetivo es si tienes carpetas de dropbox, en 6 meses están duplicados, 

> Entender un texto es tarea muy difícil   

El dato más importante era la calle, y no el nombre de la persona

> Los datos deducidos , experiencia laboral y experiencia docente mezclada  

> Todo en memoria  

### Buscador de noticias por términos	
https://www.social-clippingcom/resumenes/libre

> Busca directamente en los medios de prensa, no en google  

Informe diario con valores de bolsa
Tu metes tus URLS, tus medios, cada 10 minutos se vuelcan los datos 

Se genera un informe pdf con portada, índice, etc

Puedes filtrar los de españa los de chile

### Dilea : conjunto de locuciones
Inmaculada
https://www.diccionariodilea.es/inicio
Como María Moliner
30 años leyendo, cuando encontraba una locución las registraba

### Herramienta de diccionarios combinatorios
pacifico.dia.fi.upm.es:8080/HerramientaDiccionarios/
Ignacio bosque: 8000, 8 personas 8 años
Permite observar y saber cómo se combinan las palabras y obtener diferentes ejemplos de aplicación. Ofrece también la posibilidad de realizar búsquedas de marcadores discursivos
Diccionario con, de marcadores discursivos, de deícticos 

Marcadores discursivos

Deícticos : expresiones que te marcan información. Marcan tiempo, lugar, 
Están vacías de significado,  posicionan con respecto al contexto general
No pintan nada en Tesaurio

> Semántica: relacionar conceptos, no solo palabras  
Mañana es un sustantivo

> Redes de términos y como se pueden manejar para búsquedas finas  

### Patrilex
pacifico.dia.fi.upm.es:8080/patrilexweb/search
Igor va a hablar de esto. Que meta algo en ruso 
Podemos entender una lengua extranjera, pero es difícil buscar algo en ruso

- Demo
	- document
		- tokenizar
		- 
		- **palabras universales**(icl>writing>thing.equ>wirrten_document)
		- palabras relacionadas en 
			- 	tesauro representa el significado
hace 20 años había 1

> Wordnet: macro-ontología  


2ª práctica -> clasificador temático
3ª extractor ->

# a17-03 Modelos de representación de contenidos
# Palabras, vectores, análisis morfológico
Igor Boguslavsky 
iboguslavsky@fi.upm.es 


## Dónde hay contenidos
Texto en lenguaje natural (escrito o hablado)
Información en forma gráfica (tablas, diagramas , esquemas, dibujos)
Fotos, cuadros, vídeos
Audio

> En esta asignatura nos centraremos en lenguaje natural escrita  

## Qué unidades del lenguaje tienen sentido?
- Palabras
	- unidades idiomáticas, 
- Unidades morfológicas 
	- Terminaciones
	- s -> plural
	- presente, pasado, futuro
	- se expresan por sus **morfemas** (partes de palabras que significan algo)
- Orden de palabras 
	- Casi nunca añade significado adicional
- Construcciones sintácticas 
	- Entidad lingüística en varios elementos que pueden ser
		- no es palabra, ni orden morfológico
		- estas partes forman 
- Entonación 
	- Movimiento de tono
	- En escrito, se puede representar un poco atravesar de los signos de puntuación.

### Palabras
> Cualquier diccionario de la lengua (por ejemplo, María Moliner o Diccionario de RAE) describe el significado de palabras.   

El conjunto de los 6 significados no es nada
La unidad que funciona es cada uno de los significados por separado.

Los diccionarios representan el significado de las palabras en lenguaje natural.
Para máquinas hay que representarlos en un lenguaje formal

> Los ejemplos son útiles para la gente que aprende los idiomas extranjeros  

#### Cómo se representan los significados de palabras

### Unidades morfológicas, el número, el tiempo ….
**Singular – plural**
– casa ‘un objecto’, casas ‘más de un objecto’ 
**Presente – pasado**
– Doy una clase ‘en el momento cuando hablo’ – Di una clase ‘en el momento antes de habla’ 

### Orden de Palabras
En muchas lenguas el orden de las palabras es libre, por ejemplo en latín tiene mucha flexibilidad.
El inglés es más estricto

El orden de palabras está relacionado con las unidades morfológicas de la palabra
Si puedes expresar mucha información gramatical en cada palabra, entonces tendrás libertad

- Ejemplo:
	- In Austria German is spoken
	- German is spoken in Austria
		- El aleman Solo se habla en austria
		- El orden de palabras puede cambiar el significado

### Construcción sintáctica
Colectivo de Elementos morfológicos, palabras, orden ….

vanu ne reshit ́ etu zadachu
Ivan (Dat) no resolver (Inf) este problema
‘Ivan no puede resolver este problema’ 

La palabra puede está implícito en la construcción sintáctica

### Entonación
* Interrogación 
* Exclamación
* Emociones
* Ironía 
* … 

## Para procesar todo el contenido del texto hay que 
- representar el contenido expresado en el texto (estructuras de varios tipos)
- representar el conocimiento del mundo -> ontologías

Ejemplo:
> Las mismas palabras significan cosas distintas en contextos distintos  
Vas a la casa de un amigo, vas a su casa y él dice que que ponga su maletín aquí por favor.
Si lo pregunta un policía de aduanas, no es una propuesta educada, es una orden.

**Tipos de aplicaciones**
- Buscadores (Enfoque de saco de palabras perdiendo el orden)
	- Listas e palabras, modelo de espacio vectorial, indexación semántica latente
	- También usa la gramática, pero en muy poca medida y solo en buscadores muy avanzados como google.
- Traducción automática
	- Necesita estructuras más complejas que los buscadores
	- Estructura morfológica
	- estructura sintáctica
- Agentes virtuales (comprensión completa, inferencias)
	- Estructura sintáctica, semántica y ontológica

# Información : Representación de las palabras
## Términos relacionados o similares
Establecer relaciones entre los términos del texto
> Determinar Más cerca, más lejos y qué relación tienen entre ellos  

> Idea principal: Las palabras que se parecen semánticamente tienen patrones de coocurrencia parecidos, es decir se encuentran junto con las mismas palabras.   
El significado de una palabra se determina por sus vecinos, por las palabras con las que se combina
> Senado y parlamento aparecerán frecuentemente junto a votar y rechazar  

 Importante para RECUPERACIÓN DE INFORMACIÓN : es difícil de formular una buena consulta porque para un mismo concepto se puede definir por diferentes palabras

Expansión de consultas: Los tesauros nos ayudan a expandir consultas, buscando palabras relacionadas
Términos relacionados: tesauros o métodos estadísticos.

### Términos relacionados, ¿Para qué sirven?
#### Problema de desambiguación
- Desambiguación léxica: Una palabra muchos significados . Determinar cuál.
- Ambiguación sintáctica: Una oración tiene varias estructuras sintácticas.
	- La frase admite varias estructuras
	- La sintaxis, es la conexión de las palabras en una oración.
	- Ejemplo: Juan prometió llamarme el lunes 
		- El lunes me llamará
		- El lunes Juan prometió
- 


> El concepto de similitud puede ser distinto para distintas aplicaciones  
- ayuda al autor: autocorrectores, aplicaciones que ayudan a encontrar **sinónimos** (avión - aeroplano)
- Expandir consultas para Recuperación de información (buscadores): no solo sinónimos, relacionadas, de la **misma temática** clasificación (avión - aerolínea)
- desambiguación necesita palabras que aparezcan en los contextos similares, aunque su significado sea contrario (aumentar - disminuir). **Antónimos** tendrán los mismos vecinos

## 
### Espacio vectorial, Vector Space Model, VSM (Word embeddings)
- recuperación de información 1971 (Buscadores):
	- Seleccionar documentos según una búsqueda
	- Cada documento es un vector en un espacio multidimensional
	- La consulta también es un vector
	- Escogemos los documentos cercanos a nuestro vector de consulta
		- Nos dará Textos similares semánticamente
	- > Nos da distancias entre elementos
- Statistical semantics hypothesis
	- patrones estadísticos del uso de palabras pueden ayudar a  hacer una idea del significado del texto

### VSM fuera del RI
En otras tareas. Funciona bien cuando hay que determinar similitud cuando hay que determinar 
Está basado en frecuencias
> Los elementos que forman estos vectores están derivados de frecuencias  

Ejemplo: TOEFL(Test of english as Foreign Languages) -> 
Rapp(2003): artículo que intenta modelar el test. Acerca de los sinónimos.
![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-02%20a%20las%2018.26.47%202.png)

> **VSM**: Las relaciones nos dan similitudes entre palabras  

### Cuándo utilizar las similitudes entre los términos
**Matriz Vector-Documento**
1. Tenemos muchos documentos
2. hacemos una lista de todas palabras 
	1. el orden da igual (saco), pero será fijo
	2. por eso no distinguirá entre frases con palabras cambiadas
3. Limpiamos *stopwords*
	1. La física nuclear me gusta más que la física del plasma 
4. Hacemos matriz con documentos en las columnas y palabras en las filas
	1. en cada celda está la frecuencia de cada palabra

Ejemplo:
![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-02%20a%20las%2018.31.59%202.png)

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-02%20a%20las%2018.32.26%202.png)

La Columna habla la clasificación que tiene el documento
La palabra nos proporciona la información sobre dónde aparece el término 

### Indexación Semántica Latente (Latent semantic indexing) 
Disminuye la dimensión de los vectores
Transforma la matriz término-documento en el producto de otras 3 más pequeñas

### ¿Qué términos son más importantes? 
- Frecuencia: más repeticiones -> más importante es esa palabra para ese documento
	- El tamaño de los documentos afecta en la frecuencia
	- Para normalizarlo se utiliza `tf` term frequency
	- Para que sea importante también tiene que aparecer poco en el resto de documentos
		- `idf(i) = log N/n(i)`

### Contexto
* **Hipótesis distributiva**: palabras que aparecen en contextos similares suelen tener significados similares. 

### Similitud de relaciones: la matriz “par de palabras – patrón” 
> **Hipótesis distributiva extendida**: los patrones que aceptan los pares parecidos, suelen tener el significado parecido.  

- Filas: pares de palabras
	- (albañil, piedra), (carpintero, madera), (vidriero,  vidrio); (pájaro, insecto); (niño, libro)… 
* Columnas: patrones
	* X trabaja con Y, X come Y, X lee Y, … 
* **Hipótesis distributiva extendida**: los patrones que aceptan los pares parecidos, suelen tener el significado parecido.
*  X resuelve Y, Y está resuelto por X aceptan los mismos X-Y 

> * Hipótesis distributiva latente: si los pares de palabras ocurren en los mismos patrones, la relación entre los miembros es la misma.   


## La estructura morfológica 
- El modelo lingüístico multinivel
	- Estructura morfológica
	- Estructura sintáctica
	- Estructura semántica 


Ejemplo: `Los finales felices son historias sin acabar.`
Estructura morfológica antes de desambiguación:
1.1 EL -> ART, PL, M, CAPIT
1.2 ELLOS
2.1 FINAL
3.1 FELIZ
3.2 FELIZ
4.1 SER
5.1 HISTORIA 6.1 SIN
7.1 ACABAR 

S, ACC, PL, M, CAPIT S, PL, M
A, PL, F
A, PL, M
V, PRIND, PL, 3-P
S, PL, F
PR
V, INF 

1 y 3 son ambiguos


### Análisis morfológico
> -> La palabra más difícil morfológica en español son los verbos.  
> Cada verbo tiene 56 formulas  
Es medio, porque hay idiomas más pobres como el inglés, o muchos más como el finés o ruso que tiene 200 formas para el verbo

> La tarea es determinar la forma de palabra  
Para eso veremos los paradigmas
conjunto de todas las formas de la palabra. Patrón
Paradigmas
	- productivas
		- amar, beber y vivir son paradigmas productivos
	- irregulares

**Técnicas**
- Lista completa de todas las formas
	- fácil de hacer 
	- acceso rápido
- Inconvenientes
	- memoria
	- 

La alternativa es representar los paradigmas = patrones = fórmulas
- Es más fácil de completar: Para añadir esta palabra
- Nos predice el comportamiento de palabras nuevas
	- las palabras nuevas son productivas, sustancias químicas, procesos tecnológicos
		- Y se puede adivinar 
			- -izar -> es un verbo que implica proceso
	- las palabras irregulares como el verbo pensar , no se generan todos los días

- - - -








# a17-04 Modelos de representación de contenidos 2
Igor
20191009

## Resumen del día anterior
### Análisis morfológico
Proceso que recibe un texto, con fronteras entre palabras ya están delimitadas.
Antes hay que comprender dónde se termina la primera y empieza la segunda -> *Tokenización*

A cada palabra responder a dos preguntas:
- Nombre de esta palabra
	- nombre(forma) inicial del diccionario
- Rasgos morfológicos asociados a esta palabra
	- género
	- tiempo
	- número

El analizador morfológico, tiene que poder decir que “feliz” es un adjetivo, pero es ambiguo, ya que tiene “dos” formas. Masculino singular y Femenino singular

- **Paradigma** es la lista completa de formas
	- El paradigma puede ser representado de dos formas
		- Lista completa
			- fácil de hacer
			- fácil de buscar - rápido
			- 
		- análisis morfológico
			- más generalizado
			- reconocer patrones con conjunto de terminaciones
			- es más versátil ante palabras nuevas
				- preside el comportamiento de palabras nuevas
					- palabras nuevas aparecen todos los días, nombres de empresas, productos, aldeas de china ….
			- extracción de significado

— Página 38

Dos métodos de representación 
## Morfología a dos niveles
Kimmo Koskenniemi 1973
- Nivel superficial (estuvieron)
	- palabra escrita como en el texto
- nivel léxico
	- (estar, 

**Autómata de estados finitos**
NO ES ANÁLISIS MORFOLÓGICO.  No nos da información.

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-09%20a%20las%2017.25.45%202.png)

## **Transductores de estados finitos** (Final state transducer)
FST autómata que recibe los símbolos de entrada y genera los símbolos de salida 
![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-09%20a%20las%2017.28.18%202.png)
 
Se genera (transduce) el verbo en infinitivo
Recibe `tener` y genera `tengo`. Además añade información morfológica.
El 0 tachado significa : nulo, vacío, no hay entrada.
`tengo : tener + ind 1-p sg presente`

## Modulo morfológico en ETAP-3
Ruso. 


- Muy compacto
	- la descripción de cada palabra es muy corta
- algoritmo de análisis y síntesis de palabras
	- análisis
	- síntesis generación

- Ejemplos
	- ENTRY:AMAR
		- bas:amar t:1
		- tema -> parte de la palabra que sirve para conectar terminaciones (Raíz)
	- ENTRY:ALTO
		- bas:alt
	- ENTRY:EL
		- bas:el (ART, masculino)
		- bas:la (ART, femenino)

### Rasgos gramaticales
Hay que identificar qué rasgos gramaticales queremos utilizar
Tipos:
- **rasgos variables**
	- algunas formas de las palabras tienen este rasgo y otras no
	- adjetivos, tienen género y número
		- el género no caracteriza la palabra
- **rasgos fijos** : características de todas las formas de la palabra
	- amar -> todas las formas son verbos

- partes de la oración: fijas
	- Transformacióndepalabrasdeunacategoríaaotra:  responder – respuesta (palabras distintas) 
	- Inglés:Ianswer(V) – my answer(S) 
- Número fijo
	- gafas
	- tijeras
	- norte, suer, este, oeste
- Género
	- Para los sustantivos es fijo
		- algunos tienen género variable
		- profesiones: profesor, profesora, 
	- para los adjetivos es variable

## Estructura de la palabra
Partes de las palabras (morfemas)
- raíz: información sustancial que describe qué es eso
- sufijo: se añade a la raíz , no es obligatorio
- desinencia: o terminación, puede añadirse al sufijo o a la raíz
- prefijos: existen, pero no los veremos por ahora, porque no intervienen en la formación de palabras

Ejemplo:
Renaciste -> RENAC + ISTE (pernil, 2-p, sg)

Los adverbios no tienen desinencia, no tienen nada.
Ayer -> es solo raíz
Para las palabras no variables, no nos interesan sus sufijos.
> Si la forma de la palabra es única, no nos interesa para el análisis morfológico  
> Lo que nos interesa es distinguir las diferencias de significado entre las distintas de palabras  

## La idea del algoritmo del análisis morfológico 
> Para las palabras invariables, extraemos toda la información del diccionario  

- dividimos la palabra en partes
	- raíz / sufijo / desinencia
- cada parte tiene n>= 0 letras y rasgos asociados
- unimos rasgos asociados a cada parte

EJEMPLO
`amarás`
Buscamos un tema (una raíz)
Hay dos palabras cuya raíz puede ser el principio de esta palabra: 
- `am` (del verbo am-`ar`)
- `ama`
Hay que elegir la raíz que sea compatible con la desinencia

## ¿Cómo se describe la información en el diccionario? Etiquetas
ENTRY – introduce el nombre de la palabra.
	ENTRY:universidad
	ENTRY:alumn|o
	El símbolo “|” separa la raíz y la terminación 
bas – introduce la raíz. Si coincide con el mostrado en
	ENTRY, se pone = 
	ENTRY:universidad bas:=
	ENTRY:alumn|o
	bas:=  (ART, masculino) 
	ENTRY:el 
	bas:= bas:la  	(ART, femenino) 

`Siendo`
![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-09%20a%20las%2017.57.41%202.png)

pag. 49

Ejemplos:
ENTRY:cuatro 
	bas:= har:NUM 

ENTRY:el
	bas:= har:ART,m,sg
	bas:la har:ART,f,sg
	bas:los har:ART,m,pl
	bas:las har:ART,f,pl 

Muchas veces estas descripciones no son compactas
**5 tipos de objetos estandar** nos permiten hacer la descripción más compacta

1. Listas de desinencias: end1, end2, … 2. Formatos: f1, f2, …
2. Plantillas: t1, t2, …
3. Alternancias: alt1, alt2,… 
4. Máscaras: m1, m2… 

EJEMPLO: entrada sin compactar
ENTRY:año
bas:= har:S,m, end:’#’sg,‘s’pl 
> dos terminaciones # -> signular ; s -> plural  
esta información caracteriza a casi todos los sustantivos de las palabras

para compactar y reutilizar las terminaciones compartidas, hacemos una lista:
`end:2 [nombres terminados en vocal] ‘#'sg,'s'pl`

Luego podemos decir que la terminación pertenece a la lista 2

ENTRY:año
bas:= har:S,m,end:2 

Para todos los sustantivos, masculinos, creamos la lista formato tipo 1 `f:001`
f:001 [ídolo, libro] har:S,m,end:2 

OJO!!
- MUCHO 
	- puede ser adverbio 
	- puede ser adjetivo
	- son palabras distintas. Mucho1 (adjetivo) y Mucho2 (adverbio)

> Si la palabra es ambigua , el analizador tiene que devolver todas las variantes  

En un texto, una palabra solo funciona de una variante concreta.

Para interpretar una frase, para cada palabra ambigua, hay que determinar 


### Desambiguador morfológico
Programa que determina que variante es correcta, mirando el contexto
Ahora se utiliza ML con métodos estadísticos

**POS tagging**

En inglés es fundamental, porque la ambigüedad es mayor.
`Gas pump prices rose last time oil stocks fell` -> Todas las palabras son ambiguas entre sustantivo y verbo.
Y hay una palabra que puede

Adjetivo -> The last group
Adverbio -> He came last

2*2*2*2*4*2*2*2*2 = 1024 variantes

El método más simple es elegir la categoría más frecuente
El nivel actual, se consigue +90% de éxito

### POS tagging

La probabilidad de que estas palabras , tengan estas categorías sea máxima. Se usa la **Regla de Bayes**

Se evaluán las categorías más sencillas.
- Bigramas P(Ci|Ci-1)
- Trigramas P(Ci|Ci-2Ci-1)

Para la primera palabra no se puede evalúar , por eso se introduce la palabra ficticia CERO (vacío)

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-09%20a%20las%2018.22.40%202.png)


![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-09%20a%20las%2018.25.16%202.png)



# a17-04 Modelos de representación sintáctica
igor
20191009

## Índice
1. ¿Qué estudia la sintaxis? 
2. Relaciones entre palabras 
3. Un fenómeno sintáctico notable 
4. Estructuras de constituyentes 
5. Estructuras de dependencias 
6. ¿Cómo construir la estructura de dependencias? 
7. Sintaxis y Procesamiento de Lenguaje Natural PLN: parsing 

## Sintaxis
Organización de la oración.
Cada palabra tiene una forma. La morfología analiza las palabras sueltas.
La sintaxis estudia la estructura que forman las palabras

> Estudia las oraciones y sus partes  

- Gramática: 
	- especificación de las estructuras correctas de la lengua
	- **Lingüística descriptiva** se concentra en esta tarea
- Técnicas de parsing y generación: 
	- los algoritmos que permiten descubrir la estructura de una oración conforme a la gramática (parsing)  o construir una oración dada su estructura sintáctica (generación). 
		- - Programa de análisis
			- texto -> estructura
		- y de síntesis
			- estructura -> texto
	- **Lingüística computacional**

### Oración
- Unidad mínima del discurso que describe alguna situación, que tiene conexión al tiempo a la modalidad
	- La chica bonita
		- es independiente a la realidad y por eso no es una oración
	- La chica es bonita
		- es oración, tiene un vínculo al tiempo y la modalidad
- El hablante dice que esto tiene lugar

*”Prosódicamente”* :  delimitadas por pausas

### Tipos de relaciones
- Subordinación 
	- subordinación no son equitativas
		- una subordinante y subordinada
		- “ ~Libro~ interesante” -> equivalente a libro y no es equivalente a interesante
		- la subordinada puede ser omitida
- coordinación
	- equitativos
	- ~pablo y pedro~ están trabajando
	- pablo ~canta y baila~

“ ~Libro~ interesante” -> equivalente a libro y no es equivalente a interesante 
La palabra es la principal (subordinante) porque toda la frase , se comporta como libro. Se puede reemplazar con la palabra libro. Se pierde una parte de información.
no se puede decir si es importante o no.

~Leer~ libros: la principal es leer , es equivalente a leer


## Funciones sintácticas VS roles semánticos
> IMPORTANTE !!!  
El gobierno ha mejorado la infraestructura 

La infraestructura se ha mejorado 

> El rol semántico no es el sujeto  

- Rol **agente**: cuando esta entidad hace algo. Activo.
	- ~El gobierno~ ha mejorado la infraestructura
- Rol **paciente**: entidad pasiva que ha sido sometida a la mejora
	- ~La infraestructura~ se ha mejorado

Ambos son sujetos, pero tienen roles semánticos distintos


El gobierno ha mejorado ~la infraestructura~
~La infraestructura~ se ha mejorado

Funciones sintácticas	distintas. Objeto directo y sujeto.
Pero tienen el mismo rol semántico 


—————— Página 9 





# a17-05 Sintaxis: Análisis Sintáctico Parsing
- Igor
- 20191023
- 01 - Modelos de representación de los contenidos-2-Sintaxis.pdf : Pag 73

## Análisis Sintáctico Parsing
El parsing es un proceso que construye las estructuras sintácticas de las oraciones. 
El parser tiene a la entrada una estructura morfológica de la oración (desambiguada o no) 
Existen dos aproximaciones principales:
1. aproximación basada en ~reglas~
2. aproximación basada en ~aprendizaje automático~ 

1. Hacer las fronteras entre las palabras
	- abreviaciones
	- términos multipalabra
	- el problema de tokenización 
	- **POS Tagging - Part of speech tagging**: Programas para solucionar la desambigüación morfológica


## Aprendizaje automático. Análisis sintáctico basado en aprendizaje automático
Técnicas basadas en la inferencia estadística de los años 80.
- Inspirado por el reconocimiento de voz
- motivado por las debilidades de métodos gramaticales o heurísticas

Sus resultados son más difíciles de explicar. No XIA.

- Se utilizan en corpus de textos anotados
	- cada oración sea analizada sintácticamente

Lo más difícil es resolver la ambigüedad. Por es es mejor obtener un listado de resultados ordenados por su probabilidad.

## Algoritmo MaltParser (J.Nivre)
Mejor analizador para la generación de estructuras de dependencias

3 tipos de operaciones elementales
- La estructura es la secuencia de estas operaciones elementales
- Modelo de rasgos: 
- Clasificador -> estados a operaciones elementales

`w0` es una raíz artificial es añadido por comodidad, padre de la palabra raíz
Es más fácil considerar la palabra raíz si todas las palabras tienen un padre.

∫ = 
ß = Buffer de palabras j>k
A = conjunto de arcos de la frase y ß 
∫|i es un stack con la cabeza i y la cola ∫
j|ß es un buffer con la cola 

### Stack-based transition system
S= (C,Tcs,Ct) donde
- C conjunto de todas las configuraciones
- T conjunto de transiciones entre las configuraciones
- cs es la configuración inicial : ()=()
- ct es la configuración final (∫)

### El parsing de la frase
- Empieza con 
	- la raíz artificial 0 en el stack ∫
	- todas las palabras w1..wn en el buffer ß
	- conjunto vacío de los arcos
- Termina cuando:
	- el buffer es vacío
- transiciones de 2 tipos
	- LEFT-ARC -> enlace de j a i 
		- `(∫|i,j|ß,A) -> (∫,j|ß,AU{j,l,i})`
		- Generamos relación del buffer al stack y retiramos la palabra del stack.
	- RIGHT-ARC -> relación de i a j
		- `(∫|i,j|ß,A) -> (∫,i|ß,AU{j,l,i})`
		- Generamos relación del stack al buffer “”y retiramos la palabra del stack””
	- SHIFT
		- `(∫|i,j|ß,A) -> (∫|i,ß,A)`
		- coger el siguiente carácter y moverlo al stack
- precondiciones
	- LEFT-ARC: 
	- RIGHT-ARC: 

EJEMPLO
ROOT Economic news have little effect on financial markets.

ROOT 0 -> 3 have
have 3 -> 2 news
news 2 -> 1 Economic
have 3 -> 5 effect
effect 5 -> 4 little
effect 5 -> 6 on
on 6 -> 8 markets
markets 8 -> 7 financial
have 3 -> 9 .

[STACK] <- -> [BUFFER]    = Ax

Al final de los SHIFT, Left-Arc y Right-Arc se consigue un árbol

- Las transiciones no son determinísticas. El Shift se hace cuando no hay más posibilidades.
	- En ocasiones se pueden tomar 2 caminos a la vez
	- Las configuraciones son ambiguas.
- En el momento que hay variantes, se consulta el **Oracle**

### Oracle = Decisor codificado como un Clasificador de ML
> Oracle = Decisor codificado como un Clasificador de ML  

- permite generar un grafo ~proyectivo~
	- estructura proyectiva , no se cruzan los arcos, y la raíz no es cubierta por ningún arco
		- Caracteriza la mayor parte de oraciones
		- Los parsers estadísticos solo trabajan con las oraciones proyectivas 
- en tiempo lineal, (muy rápido)
- cualquier grafo proyectivo pude ser generado
- Es aproximado, no 100%, la precisión es bastante buena si se usan modelos de rasgos basado en historia y ML

## Aprendizaje Automático
Problema de clasificación puro.
Conjunto de elementos a clasificar: VECTORES DE RASGOS  (configuraciones caracterizadas).
El clasificador para cada configuración con sus rasgos tiene que decir cual es la transición siguiente
- Datos para entrenamiento `(F(c), t)`
	- `F(c)` -> configuración c representado por el modelo de rasgos
	- `t` -> transición correcta desde c

### Métodos de ML (AA) utilizados en este enfoque
Cualquier clasificador se puede utilizar
Los más usados son:
- Support Vector Machines : SVM con LIBSvm 
- Memory-based learning (MBL)
	- Aprendizaje es simplemente el almacenamiento de experiencias en la memoria
	- para resolver …

### Malt parser
Alternativa de transiciones 
- Se genera un grafo de depedencias
- Oracle es generado con ML (AA)
	- genera un parser dado un treebank
	- parser data-driven, basado en los datos

Funciona en dos modos:
- Modo de entrenamiento: 
	- coge un training set y deriva los datos de entrenamiento
	- se puede reconstruir la estructura de transiciones
- Modo de parsing: 
	- utiliza el clasificador para analizar  oraciones nuevas

## Modelo de rasgos
Cualquier modelo de rasgos.
Los mejores resultados se obtienen con los rasgos más sencillos:
- 6 rasgos part-of-speech (dos palabras superiores de stack y cuatro palabras del buffer)
- 3 rasgos de dependencias: la palabra superior de stack y sus dependientes de derecha y de izquierda y el mas izquierdo dependiente de la siguiente palabra del stack
- 4 rasgos léxicos (palabra concreta que tenemos en la frase):
	- forma de la primera palabra del stack
	- forma del padre
	- 2 siguientes palabras del buffer
- Se puede esperar el número de rasgos léxicos
	- cuando el treebank, se puede aumentar el número de rasgos léxicos

> No es difícil pasar del corpus   
Parser de dependencias para varias docenas de lenguas.

# Un analizador sintáctico basado en reglas (el sistema ETAP)
- conocimiento lingüístico
- el algoritmo que aplica este conocimiento y descubre su estructura sintáctica

## Estructura sintáctica correcta
- Requisitos globales
	- un árbol de dependencias
		- nodos: estructuras morfológicas de palabras
		- arcos: relaciones de dependencias
		- nodo que no tiene arcos entrantes
		- los demás nodos tienen solo un arco entrante
		- no hay ciclos de dependencias
	- proyectividad (salvo
	- de ningún nodo sale más de una relación repetible
		- relaciones repetibles:  de una palabra salen dos relaciones del mismo tipo r. Entonces r es repetible
- Requisitos locales
	- todas las palabras con requisitos sintácticos deben cumplirse
		- por ejemplo, las palabras con argumentos obligatorios
	- cada arco tiene que corresponder con alguna regla de la gramática

> Los arcos se generan por alguna regla  

## ALGORITMO basado en reglas
Conocimiento del analizador, está distribuido entre dos fuentes
1. Conjunto de reglas
2. Diccionario
	- información relevante para el análisis sintáctico
		- argumentos …

Reglas sintácticas que establecen estas relaciones
1. **CHECK** : Restricciones/Condiciones de las reglas
	- formulas lógicas de 1er orden
	- deben ser complejas y específicas. Estrictas, para no generar demasiadas relaciones erróneas.
	- Las reglas puede que no puede comprobar globalmente, solo parcialmente, porque todavía no hemos analizado toda la oración. Tendremos incógnitas.
		- Una regla bloquea las siguientes
	- **Lineales** -> Inmediatamente
		- la palabra tiene este rasgo o no
		- la palabra está a la derecha
	- **No lineales** -> hay que esperar
		- requerimientos sintácticos
			- subordinaciones, tienen x hijos
2. **DO** :  para llegar aquí deben cumplirse todas las del CHECK
	- 

> Equivalente a un IF THEN  
Pasos
1. Se hace un conjunto de relaciones potenciales. Todas las relaciones correctas + incorrectas (de más).
	- El check aplica las ~reglas lineales~ para generar el conjunto de relaciones potenciales
		- al aplicarse todas las reglas, entonces se han generado todas las relaciones. 
2. Detectar y eliminar las hipótesis erróneas
	- Filtro, comprobamos las ~reglas no lineales~
		- la palabra tiene este hijo?
		- si no se cumple, se elimina la relación
		- si se cumple, la hipótesis/relación potencial continua.
			- esto no significa que la relación sea correcta
3. Backtracking
	- Durante el filtrado y eliminación, al elegir un
	- Se vuelve atrás para validar

EJEMPLO `PAG: 80`
> The general made an interesting remark  
- Ambigüedad morfológica y léxica
	- general -> adjetivo o Sustantivo
	- remark -> verbo o sustantivo
- reglas de pre-sintaxis 
	- adjetivo y artículo + (V/S) -> solo podemos ser un sustantivo y no un verbo

Si una palabra tiene solo una regla entrante, entonces seguro que es verdadera. Todas las palabras necesitan un padre.

## Evaluación de los parsers y métricas
Es difícil comparar distintos parsers
Y el mismo parser en diferentes momentos

Métricas:
- Labeled Attachment Score (LAS) : Padre correcto y el nombre
- Unlabeled Attachment Score (UAS): Padre correcto
	- hemos podido acertar o fallar con el label

Los mejores parsers consiguen un 
- LAS del 90%
- UAS del 

## Definiciones
- POS -> información (sujeto, verbo) y rasgos morfológicos
- **TreeBank** (denominado también como Corpus parseado o más ampliamente Penn **Treebank**) es un corpus lingüístico en el que cada frase ha sido parseada, es decir anotada con su estructura sintáctica.
- 

# a17-05 Sintaxis: Subordinación - coordinación

Diferencia entre funciones sintácticas y roles semánticos (agente - paciente)

Pueden tener la misma función sintáctica (sujeto) pero diferentes roles semánticos. Y viceversa

## Funciones sintácticas
* predicado( ~Juan~ duerme) 
* sujeto(Juan ~duerme~ ) 
* complemento directo (Juan lee el libro) 
* complemento indirecto (Juan da el libro a María) 
* complemento circunstancial(Vendré el sábado) 
* determinante(estos años) 
* modificador (árbol verde) 


## Roles semánticos
* agente(Juan lee) 
* paciente(Juan construye una casa) 
* experimentador (A Juan le gustan matemáticas) 
* tema (A Juan le gustan matemáticas) 
* recipiente (Juan da un libro a Pablo) 
* beneficiario (Juan da un libro a Pablo para su hermana) 

## Argumentos vs Adjuntos
- Argumento
	- algo para que el predicado sea completo.
	- expresa el contenido principal - posee el esqueleto
		- quién, hizo qué 
		- no se incluyen los complementos circunstanciales
	- 


> Lo importante es representar correctamente los argumentos  

## Tipos de relaciones
 Resumiendo, hay 4 grupos de relaciones sintácticas:
* Relaciones de subordinación
	* Relaciones argumentativas: Juan duerme, comió una 
manzana, método del cálculo 
	- Relaciones que conectan los adjuntos (modificativas): vino ayer, libro interesante, muy aburrido 
	- Relaciones auxiliares: he leído, ~~veinte tres~~, las chicas  
* Relaciones de coordinación: Juan y María, baila y canta, pequeño pero inteligente

Los predicados tienen miembros.
verbos, sujetos

- argumentos de Besar
	- sujeto con labios -> una persona
		- los labios son participantes, pero no es argumento porque no se conecta en el texto
	- CD -> algo o alguien
	- 


### Resumen
para todos los predicados encontrar los argumentos - predicados que hay en la frase

## Fenómeno sintáctico notable: concordancia
Algunas Concuerdan con otras
Concordancia en
- género y número
	- adjetivos y sustantivos
- número y persona
	- verbo y sujeto

Ausencia de concordancia en persona
- las mujeres [3ª] sois [2ª] muy complicadas
- las mujeres [3ª] somos [1ª] muy complicadas

La concordancia no implica siempre la coincidencia de los valores
En ruso por ejemplo, los números hasta 5 llevan el sujeto en genitivo singular, en vez de plural

### Representar estructuras sintácticas : 1. Constituyentes
Muestran como la oración se divide en partes.
De dependencias muestran cómo se conectan entre sí.

### Representar estructuras sintácticas : 2. Dependencias
Estructuras de Dependencias

`Vino uno de los chicos`



# Poyectividad
como se manifiesta la no proyectividad
en la frase no proyecta, habrá un cruce de flechas

## repetible vs no repetible


> los verbos impersonales no tiene ningún argumento  

La caída continua en el precio de las acciones es el motivo de la dimisión de el presidente de la compañía

Precio tiene dos argumentos, aunque solo esté expresado uno.

## Síntaxis y PLN : parsing
Parsing , análisis sintáctico

### Algoritmo basado en el conocimiento

### Análisis sintáctico (parsing)
- El parsing es un proceso que construye las estructuras sintácticas de las oraciones.
- El parser tiene a la entrada una estructura morfológica de la oración (desambiguada o no)
- Existen dos aproximaciones principales:
	- aproximación basada en reglas
	- aproximación basada en aprendizaje automático







# a17-06 Modelos de representación de contenidos: representación semántica 
- Igor Boguslavsky
- 20191030
- `Tema 2. Representación de contenidos/Modelos de representacion del contenidos-3 Semantica.pdf`

## El significado del texto 
- Significado lingüístico
	* Unidades del lenguaje 
	* Fusión de los significados de las unidades en el significado del todo el texto 
- Significado pragmático
	- situación comunicativa,
	- conocimiento compartido por los hablantes
	- relaciones interpersonales
	- información del contexto 


## Representación semántica convencional (“shallow”) 
Shallow = Representaciones más superficiales.
Distintos tipos de anotación: Información sobre nombres de personas, geográficos, organizaciones. No están incluidos en los diccionarios normales.
- Anotación de palabras
	- Entidades nombradas 
		- personas, geográficos, productos, compañías
		- no están en diccionarios
	- Números de sentido
		- diferentes significados 
		- “aquí está usada como el sentido nº 3 en nuestro diccionario”
	- Conceptos ontológicos 
		- Objetos extra-lingüísticos
		- a cada palabra se le asigna un objeto de la ontología
- Anotación de vínculos entre las palabras
	- Argumentos (FameNet)
	- Roles semánticos (VerbNet)

EJEMPLO
`Messi marcó un gol`

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-30%20a%20las%2017.57.37%202.png)

Hay muchos enfoques para construir representaciones semántica más profundas.
Muchos están basados en la lógica de primer orden.
1. Lógica de primer orden 
2. Discourse Representation Structures 
3. Marcos y guiones 
4. Universal Networking Language 

## 1. Lógica de primer orden - LPO
Complicado pero atractivo
Existen muchos motores de inferencia.
Es muy expresivo.

En frases complicadas, necesitamos lógica de 2º orden.

### Limitaciones
- No es decidiste
	- no hay algoritmo que pueda decir si es válido o no
- No soporta razonamiento no-monótono. 
	- no admite excepciones
- No soporta cuantificadores
	- la mayoría de los perros tienen un rabo

Fragmentos buenos computacionalmente:
- Lógica descriptiva. ALE, ALC, SHIQ, OWL DL (Decidibles de LPO)

Relaciones anafóricas: palabras diferentes pero el objeto es el mismo. Coreferentes.
Por ejemplo: Pronombres.

## 2. Discourse Representation Structures 
Creadas para representar las relaciones anafóricas dentro de la lógica de primer orden (LPO).

El granjero compró un burro y él lo golpea.

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-30%20a%20las%2018.13.04%202.png)

## 3. Marcos y guiones : FrameNet
FrameNet hecho para el inglés.
- **Marco semántico**: Situación generalizada para una misma situación.
	- Juan vendió su coche a Alfonso
	- Alfonso compro un coche de Juan
- tiene diccionarios

### Marco para pedir
OntoSem 

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-30%20a%20las%2018.18.32%202.png)


### Guiones == Scripts
TIRO — GOL
Gol es un tiro, pero un tiro no siempre es GOL
Guión de gol:

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-30%20a%20las%2018.21.48%202.png)



## UNL - Universal Networking Language 
### Origen
Nació en el año 96 en la universidad de ONU en Tokio.
Solo tiene becarios y doctorandos que trabajan en temas de ámbito global.
Creado por Hiroshi Uchida, autor de TA ATLAS
15 grupos para cubrir 15 idiomas principales.
El español fue invitado de la UPM por Cardeñosa.

### Objetivos
Desarrollar un lenguaje común, semántico, universal, independiente de las lenguas concretas para resolver:
- Comunicación multilingüe
* Búsqueda multilingüe
* Resumen multilingüe
* Generación multilingüe
	* Producción de documentación/instrucciones en muchas lenguas 
	* No es lo mismo que la traducción.
	* Pasar de una representación única/desambiguada y abstracta -> generar a múltiples idiomas.

### Diferencia entre UNL y Traducción automática
La traducción intenta conectar/relacionar cada lengua con el resto de lenguajes.
Para n lenguas , complejidad `n*(n-1)`
	Pocas lenguas
	traducciones de baja calidad
Interlingua es una lengua artificial, y todas las lenguas se conectan a esta., complejidad `n`
	estrategia de interlingua
	análisis semiautomático
		desambiguación tenía que resolverse con la ayuda del usuario
![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-30%20a%20las%2018.39.46%202.png)

DOS SISTEMAS:
	* Lenguaje formal para representar el sentido 
	* Deconverter: UNL -> NL 
	* Enconverter: NL -> UNL 
	* Deconverter + Enconverter = Language Server 
	* El sistema UNL = una red de los servidores de lenguas 

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-30%20a%20las%2018.42.47%202.png)

### ¿Por qué no usar un LN existente como el inglés como interlingüa ?
Porque habría que resolver esta desambiguación dos veces para codificar y descodificar este idioma. Y se insertarían más ruido y más ambigüedad que traducir directamente entre dos idiomas.

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-10-30%20a%20las%2018.47.00%202.png)


### ¿Como construir una interlingua? 
* Palabras - Problema léxico
* Un modo de conectarlas (sintaxis)  - problema sintáctico 

### Resolver el problema léxico
Universal Words: dos enfoques 
1. Correspondencia 1-1 entre las unidades semánticas y léxicas para cada idioma
	1. habrá tantas palabras como significados hay un el Lenguaje natural
	2. ventaja
		1. la correspondencia entre las dos unidades es tradicional
	3. Desventaja
		1. sentidos léxicos de diferentes idiomas no coinciden
		2. casarse en ruso , zhenitsa y vychodit zamush
			1. esto generaría una lista gigante, para coger todas las 
			2. e introduciría mucha complejidad para detectar los matices
				1. como arroz en malayo o nieve en eskimal
2. **primitivos semánticos**: pequeño grupo de primitivos conceptuales que se combinan para formar sentidos más grandes de palabras
	1. Ingerir + 

Desventaja : Demasiado complicado

`pag 39`



# a17-06 Sintaxis (Resumen)
- Igor
- 20191030
- `Tema 2. Representación de contenidos/01 - Modelos de representacion de los contenidos-2-Sintaxis.pdf`

Dos formas de representar la estructura sintáctica
1. Secuencia de Constituyentes “recursivos”
2. Representación de dependencias. Árbol de dependencias
	1. no conecta palabras en grupos, 
	2. solo representa las relaciones entre palabras

Relaciones entre palabras
1. Subordinación - coordinación

- Función sintáctica
	- sujetos, complementos, 
- Roles semánticos
	- agente - paciente

- Predicados + Argumentos = Esqueleto de la oración
	- Argumentos
		- preposiciones
			- casarse **con**, preguntar **a** , depender **de**
		- pedir y preguntar 
			- 3 argumentos : dos personas + preposición
			- no son similares de vista a nivel de expresión
			- el 3er argumento 
				- en ambos casos puede ser sustantivo
				- en preguntar la frase necesita que sea interrogativa (una pregunta)
				- en pedir necesita la conjunción `que`
					- para introducir una oración subordinada
					- qué podría ser pronombre: que reemplaza kotorii

- concordancia entre dos palabras
	- categoría gramatical: género , número, tiempo
		- adjetivos y nombres
		- uno se elige en función de otro
		- normalmente son iguales, pero no es imprescindible 

Que1 : Conjunción
Que2 :  pronombre

- Veo que estás cansada.
	- qué subordina a la siguiente oración
- Veo a la chica que estás cansada.
	- que está subordinado por estás

### DEMO conectándose al ordenador de la academia de ciencias

SISTEMA `ETAP-3`
UNL : lenguaje semántico interlingüe. (la práctica la haremos con este lenguaje).
Ontologías + Inferencias

- Dos ventanas
	- input
	- output
- Botones
	- árbol de dependencias
	- Opción interactiva
		- Ambigüedad : (léxico)palabras , (semántico )estructuras, 
		- ayuda a resolver las ambigüedades de forma dinámica.
			- se para y pregunta al usuario
- Funciones
	- Traducción
	- Paráfrasis 



# a17-07 UNL
- Igor
- 20191106
- `Tema 2. Representación de contenidos/Modelos de representacion del contenidos-3 Semantica.pdf` pag 49

# ¿Qué se hace en UNL?
Tiene que superar el problema de añadir traducciones entre 2 idiomas sin meter más ruido / incertidumbre.

Estos requisitos


## Estrategia UNL 
- **UW** = Universal Word
- **icl** = incluida en la clase de … || is kind of 
- **iof** = instance of. 
- **equ** = igual, equivalente, sinónimo ( no se pone una palabra universal, solo una etiqueta)
- **ant** = igual, equivalente, antónimo
- **pof** = part of
	- month(pof>year)
	- roof(pof>house)
- **agt** = agente
- **fld** = field , campo, dominio (matemáticas)
- **com** : componente
	- util par adjetivos y adverbios

* UNL  

* Sentidos léxicos de cada lengua se representan por medio de las UWs. 
* Si el sentido léxico no tiene equivalente en inglés, hay que encontrar la palabra inglesa mas cercana con el sentido mas general y restringir su sentido con una **restricción**. 
	* No equivalencia de palabras entre distintos idiomas
	* Si una palabra en Español tienen múltiples significados, entonces tendremos que crear una palabra universal para cada significado.
	* Si no se pueden tener palabras diferentes -> cogeremos una palabra más genérica y la limitaremos en su significado.
	* EJEMPLO 1
		* Esquina -> Corner (icl>place,com>exterior)
		* Rincón -> Corner (icl>place,com>interior)
	* Ejemplo 2
		* pez -> fish(icl>living_thing)
		* pescado -> fish(icl>food)
	* Ejemplo 3
		* ruso -> inglés -> español -> UNL
		* zhenitsa -> marry -> casarse -> marry(agt>male)
		* vychodit zamuzh -> marry -> casarse -> marry(agt>female)
		* de español a ruso habría una desambiguación 
		* en UNL hay 3 palabras marry(agt>person) ,  marry(agt>male), marry(agt>female)

## Expresión UNL 
* Expresión UNL es un hipergrafo orientado 
	* **Nodos** - ~Universal Words~ (UW) 
	* **Arcos** – ~relaciones semánticas~ que conectan dos UWs 
	* **Atributos** - ~información suplementaria~ asignada a las UWs 

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-11-06%20a%20las%2017.43.45%202.png)

Hipernodos -> Nodo compuesto, 
	- subgrafo que emite relaciones como si fuera un nodo 
	- tiene sus propios atributos
	- puede contener otros hipernodos más pequeños

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-11-06%20a%20las%2017.50.38%202.png)


`UW -> Headword + (restrictions)`

Headword : Es una palabra inglesa.  En forma de lema (infinitivo, singular, etc)

`Headword: puede ser una frase inglesa (multi-word headword)`
EJEMPLO:
Buscar -> look_for
nutria -> fur_seal 

`Headword = palabra no inglesa `
- paella
- devanagari(=escritura de lenguas de India)
- kvas (=bebida rusa) 

## Tres funciones de restricciones
	
- Función ontológica:
	- Conecta su clase natural (**hperónimo**): ~icl~
	- Conecta una UW que denota un objeto individualizado con el concepto del cual es una instancia: **iof**
	- conecta una UW con su sinónimo: **equ**
- Función semántica: restringe el significado
- Función argumental: indica el patrón de argumentos
	- la UW tiene que indicar el número de argumentos
	- y cuales son
	- EJEMPLO
		- gift(agt>uw, obj>uw, rec>uw)
			- la clase semántica uw es la más amplia de todas , puede ser cualquier cosa.
			- NOMBRE DE LA RELACIÓN SEMÁNTICA
				- agente
				- objeto
				- recipiente
			- CLASE SEMÁNTICA 


Jerarquía general de conceptos
- UW
	- verb 
	- thing
	- adj
	- adv

## Desambiguación
![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-11-06%20a%20las%2018.07.36%202.png)

## Verbos en UNL
3 clases de verbos en UNL
- (icl>do): acciones y actividades con iniciador
	- he include su nombre en la lista
- (icl>occur): acontecimientos y procesos iniciados por una fuerza exterior
	- 
- (icl>be): situaciones estáticas - estados, propiedades, relaciones
	- la lista incluye su nombre
	- 


## Ejercicios
- el niño sabe contar hasta 50
	- contar -> acción
	- saber -> estado
- cuenta con buenas recomendaciones
	- estado
- cuéntame lo que ocurrió
	- acción
- puedes contar conmigo en este asunto
	- contar: estado
	- puedes: estado

### clases de sustantivos 
![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-11-06%20a%20las%2018.16.39%202.png)

## Restricciones semánticas: dos funciones
Hay varias palabras en inglés
En inglés no hay una palabra. -> Genérico + Restricciones.

* Separar el sentido de la UW del resto de sentidos que la headword puede tener en inglés: 
* handicraft(icl>concrete_thing):
	* *México es un gran productor de artesanía*
* – handicraft(icl>activity)
	* *La artesanía es un trabajo muy duro*
* Construir un concepto nuevo (no existente en inglés) 
	* esquina, rincón, pescado ….


> OJO !!  
## MUY IMPORTANTE!
- Las restricciones semánticas deben distinguir el sentido de UW del resto de sentidos relevantes de la headword. 
- No deben ser aplicables a más de un sentido. 
- Deben ser fácilmente comprensibles. 

EJEMPLO
- INCORRECTO: operator(icl>thing) no es suficiente, porque no distingue sus significados
- CORRECTO:
	- operator(icl>human)
	- operator(icl>abstract_thing, fld>mathematics)
	- hay que elegir la propiedad más específica que podamos

## Restricciones: relaciones útiles para desambiguación
- equ(=sinónimo)
	- wood(equ>forest), plane(equ>airplane)
- pof(=parte de)
	- month(icl>time_period, pof>year)
	- month(icl>time_period, iof>unit)
		- iof -> elemento único, no es un subconjunto
	- gramo(icl>, iof>unit)

## Útil para relaciones difíciles. Desacmbiguaciones
- **com** : componente
	- A(com>B) = B es un componente importante del sentido A

EJEMPLO
(a) sensational(icl>good>adj)
(b) sensational(icl>adj,com>interest) 

## Restricciones Argumentales
Estructura argumental
Conectan UWs en el grafo UNL y el rol del argumento.

## Relaciones argumentales: agt
LEER desde la página 84.




# Práctica
Hasta final de noviembre.

Traducir a UNL con UW solo para los significados que aparece en el texto y asegurarnos que las distingue entre el resto de significados.
Ninguna UW puede ser ambigua. Tiene que desambiguar distintos significados del headword

No hace falta poner las etiquetas de las relaciones. agt o obj . Es suficiente con poner los argumentos arg1, arg2, sin distinguir su rol.


1. Parte1 : Construir UW para el texto
	1. elegir texto de 300 palabras en español
	2. hacer una lista de palabras singnificativas sin repeticiones.
		1. solo verbos, sustantivos, adjetivos, adverbios. SIN PRONOMBRES
	3. Hacer las UWs para estas palabras. Solo para el significado del texto
	4. icl/iof
		1. Para elegir el icl podemos usar: wordnetweb.pinceton.edu/perl/webwn
			1. buscar la palabra en inglés
			2. allí aparecerán “sinónimos”, y la jerarquía dentro de los  direct hypernym. Hiperónimos. (ICL)
		2. si la palabra no está en wordnet, habrá que inventarlo
		3. para verbos elegir entre las 3 categorías (do, occur, be)
		4. Headword: tiene que ser el lema. (lo que aparece en el diccionario)
		5. Poner todos los argumentos, aunque no aparezcan en el texto
			1. Describir el concepto
		6. Clases semánticas
			1. see(icl>perceive, arg1> animal, arg2> ~functional_thing~)
			2. clase a la que pertenecen los argumentos fuera del contexto.
2. Parte2: Hacer grafos para las oraciones de este texto
	1. Grafos entero de UNL.  solo e headwords (sin restricciones)
		1. estudiar las relaciones semánticas. UW con relaciones.
			1. obj(want, Juan)
			2. obj(want, participate)
			3. obj(participate, congress)
			4. plc(congress, Madrid)
- [ ] enviar 30 de noviembre por email (iboguslavsky@fi.upm.es)


![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-11-06%20a%20las%2018.42.56%202.png)

**Entregar la práctica por email.**


# a17-08 Recursos lingüísticos diccionarios y corpus

- Igor Boguslavsky
- 20191113
- `Tema 3. Recursos lingüísticos/Recursos linguisticos.pdf`


## Recursos para los humanos
- RAE
	- origin, significado, rasgos gramaticales, ejemplos de uso, locuciones idiomáticas
- Corpus de referencia del Español Actual (CREA)
	- corpus más grande 200 millones de palabras

## ¿Qué datos están reclamados de RL por las aplicaciones de PLN?

- Formas de palabras (mesa, mesas - está ,estuvo, estará)
- El significado de palabra
- palabras derivadas
	- derivación formal y semántica
		- formal -> raíz
		- semántica -> no tiene por qué partir de la misma raíz
			- enseñar, profesor, alumno, materia (son derivados semánticos)
	- verbo, agente, paciente, objeto
	- profesor - enseñar
	- Inventar, invento, inventor
	- leer, lector 
	- Madrid, madrileño
- palabras relacionadas (sinónimos, clase/subclase, parte/todo)
- equivalentes en otras lenguas
- varias propiedades de palabras (rasgos sintácticos, semánticos)
- combinación de palabras posibles
- texto sin etiquetar (raw text)
- texto etiquetado con la información relevante

## Aplicaciones que necesitan estos datos: Desambiguación gramatical
- ama - ¿Sustantivo o verbo?
- feliz - ¿masculino y femenino?
- gas pum prices rose last time oil stocks fell (todas las palabras son ambiguas)

ML aprendizaje automático con un corpus etiquetado (modelos de markov, arboles de decisión) para determinar la 


## Desambiguación léxica (WSD) - Word Sense desambiguation

Cabo : tierra en el mar, grado militar
Correr tiene 45 sentidos.
IA completo - categoría más alta de dificultad en problemas de Inteligencia Artificial

- Métodos de ML
	- basado en conocimiento VS basado en corpus
	- supervisado vs no supervisado
- conocimiento -> recursos léxicos externos (diccionario externo)
	- no muy usado 
- basado en corpus : utiliza un corpus etiquetado o no
	- corpus etiquetado -> clasificación
	- corpus no etiquetado -> clustering

## Recuperación de información
- Expansión de consultas
	- expandir las consultas con otras palabras para aumentar la cobertura de la búsqueda

## Traducción automática
Necesita mucha más información

Sistemas basados en conocimiento
	- Diccionario morfológico
	- sintáctico
	- semántico

Sistemas basados en aprendizaje automático 
	- no necesita diccionarios
	- corpus bilingüe alineado (para hacer un modelo de traducción)
		- mejor si son idénticos
		- si son parecidos se puede sacar un buen resultado
		- aunque usemos novelas traducidas, las frases no serán idénticas
		- hay que buscar la correspondencia entre frases y palabras.
	- corpus monolingüe para hacer un modelo de la lengua destino

Recursos estructurados
	- Tesauros
	- Diccionarios electrónicos
	- Ontologías
	- Motfologicos

No estructurados sin etiquetar
	- British national corpus 100M
	- wall street journal 30M
	- Gigaword corpus (2B)
	- CREA (español)
	- Brigham young (100M)
	- Corpus nacional de Ruso (360M)

No estructurados : corpus estructurados
	- rasgos gramaticales (part of speech)
	- lemas
	- estruturas  sintácticas
	- sentido léxico
		- treebank
	- correferencia
		- dos palabras referencian al mismo objeto del mundo
		- nombre y pronombre (Juan / él)
		- donald trump / presidente de estados unidos
	- actos de habla
		- información pragmática
		- qué quiere hacer el hablante con este tema
		- petición , amenaza, ironía
	- rasgos estilísticos
		- estilo elevado, coloquial …
	- otros (research specific)

- brown corpus (rasgos morfológicos)
- penn treebank (inglés , estructuras sintácticas, constituyentes)
- syntasrus (ruso , estructuras sintácticas)
- ** framnet (corpus etiquetados con marcos argumentos + los marcos en sí)**
	- marco de compra y venta
		- hay muchas palabras que determinan
		- fijamos los participantes
			- quien compra, quien vende, lo que cuesta
	- 
- **semcor (sentidos de wordnet)**
	- series de sinónimos y sus relaciones
- propbank (roles semánticos de verbos)
- nombank (roles semánticos de los sustantivos)


## Recursos Estructurados
### TESAURO
El más antiguo, mucho antes que los ordenadores.
- El primero: Roget’s International Thesaurus (250K palabras en 6 clases y 1000 categorías). Organizados semánticamente.
	- Es útil para los autores que buscan una palabra específica que quieren una palabra muy concreta y sabemos a qué categoría pertenece. (color X)
	- Establecen las relaciones entre distintos términos
		- Sinónimo: bonito - bello
		- Antónimo: bonito - feo
		- Hiperónimo: Coche - vehículo

[SKOS: Tesauro de la UNESCO](http://skos.um.es/unescothes/)

### Diccionarios electrónicos
En papel convertidos a electrónico (machine-readable diccionarios)
- collins english dictionary

- desde 1990: WordNet - recurso léxico más usado
	- red semántica de conceptos
		- sinónimos + relaciones
	- diccionario computacional

### WordNet
existe en formato RDF , web semántica y recursos lingüísticos enlazados
uso gratuito
- desarrollada en Princeton
- series de sinónimos representan conceptos
- wordnet 3.0: 155K palabras organizadas


Wordnet de español -> para uso no comercial gratuito

### EuroWordNet
1994-1999 -> Holandés, Italiano, Español, Alemán, Francés, Checo y Estonio
Están enlazadas con el WordNet de Inglés (sirve como interlingua)

## Ontologías
están destinadas para modelar los conocimientos sobre un dominio real o imaginario
descripción de los conceptos y relaciones que pueden formalmente existir para un agente o comunidad de agentes en este dominio
definición más aceptada : “**representación formal y explícita de la conceptualización compartida**”
- define conceptos, relaciones entre ellos y otras situaciones relevantes para modelar un dominio
- las definiciones formales de los elementos de la ontología (clases, relaciones atributos) es lo que proporciona el significado a estos elementos y las restricciones formales de su uso

### Aplicaciones de la ontología

Las ontologías se usan en la web semántica , vocabularios conceptuales con los que se pueda:
- intercambiar datos entre sistemas
- proporcionar servicios pregunta-respuesta
- publicar las bases de conocimiento reutilizabas
- ofrecer servicios para facilitar interoperabilidad entre sistemas y bases de datos heterogéneas

Aplicaciones exitosas: interoperabilidad de bases de datos , búsqueda cruzada en las bases de datos, integración de servicios web.

### Elementos de la ontología
- Instancias (instances, individuals)
	- Elementos del nivel más bajo
	- pueden ser concretos (personas, edificios, planetas) o abstractos (números, palabras)
- Conceptos: clases que incluyen instancias, otras clases o combinaciones de unas y otras
- Atributos: caracterizan clases o instancias
- Relaciones: caracterizan vínculos entre las clases o instancias

Cada concepto 


- Instancia de la clase FootballPlayer
	- hasName: Iker_Casillas
	- hasNickname: El_Santo
	- hasBirthdate: 20XX-XX-XX

Red de conceptos. No es un árbol.

cada clase puede ser subclase de distintas clases

Persona: nombre, nacimiento, …
AgenteDeportivo: tipo de deporte, entrenador
Futbolista: Subclase(persona) + Subclase(agenteDeportivo) + otras propiedades
Equipo: Subclase(AgenteDeportivo)

Cuanto más abajo en la jerarquía -> más propiedades tiene


## SUMO : Suggested Peer Merged Ontology
- ontología formal escrita en lógica de primer orden
	- no solo la red de conceptos
	- también axiomas y reglas en lógica
- open source
- conectada en wordnet 3.0
- tiene librerías
- Hecho en KIF ~ similar a LISP

20K términos

### Ejemplo de reglas

![](a17%20Ingenieri%CC%81a%20Lingu%CC%88i%CC%81stica/Captura%20de%20pantalla%202019-11-13%20a%20las%2018.29.47%202.png)


## SemCor
Corpus más grande etiquetado con los significados
Se utiliza para entrenar desambiguadores léxicos

## SynTagRus
corpus ruso con : lemas, rasgos morfológicos, estructuras sintácticas de todas las frases, sentidos léxicos, funciones léxicos
50K oraciones
semiautomática con el parser ETAP
[Национальный корпус русского языка](http://ruscorpora.ru/new/)
se utiliza para entrenar parsers estadísticos y para verificar el parser ETAP

### Corpus genérico vs especializado
Corpus genéricos
difíciles de hacer y que estén balanceados
Específicos
mucho más sencillo y rápido de hacer

### Dinámico VS Estático
Foto estática en un momento dado
fácil de controlar el balance del contenido
Puede ser limitada al pasar tiempo 

Corpus dinámico


### Representatividad 
Número de palabras no es lo más importante
Qué ámbito queremos cubrir
Hay que elegir una muestra que incluya la variabilidad de la población

### Muestreo aleatorio
1. identificar grupos y subgrupos dentro de la población 
	1. géneros, prosa, ficción , medicina …


### Tamaño del corpus
grande mejor, hasta que se estabilice
La adición de textos no genera nuevos fenómenos

### Recoger un corpus oral
Recoger muestras naturales
- no se puede grabar las conversaciones de manera oculta.
- Paradoja del observador: la presencia del grabador afecta el comportamiento

### Recoger corpus escrito
Problema de autorización
copyright 


 






# a17-09 Recuperación de información

- Carseñosa
- 20191120
- ``

### Introducción
El único sistema de traducción barato es interlingua , tiene un coste de 2n.
Conocimiento enciclopédico
- [ ] práctica: clasificador documental (antes de navidad)

En estos dos días vamos 

Recuperación de documentos, no datos.

## Qué podemos hacer con documentos?
- Buscar documentos
- Clasificar
	- clasificar para encontrarlos mejor

### CLASIFICACIÓN
como los clasificamos? Como sabemos que es relevante.

como lo representamos?
SALTON inventó el VSM (Vector Space Model) . De los más usados y 
Si añades un documento hay que recalcular todos los 
`tf-idf`

### Análisis del discurso
Cuando los textos son muy largos se analizan por partes.
No es lo mismo un documento de 5 páginas que uno de 20.

### Tesauros son términos, no son conceptos
La ventaja es que los tesauros están formalizados internacionalmente (ISO). Tanto para mono ligüe como multilingüe
Los generan los Profesionales documentalistas


- Tienen pocas relaciones
	- TE
	- TG
	- Use 
	- TR
		- 	zumos y frutas

Para recuperación de información.
[Information retrieval - Wikipedia](https://en.wikipedia.org/wiki/Information_retrieval)

### Recursos
- Libro : Ricardo Baeza Yates
	- Estado del arte de IR: http://people.ischool.berkeley.edu/~hearst/irbook/print/chap10.pdf
- [Introduction to Information Retrieval](https://nlp.stanford.edu/IR-book/)
- [CS 276: Information Retrieval and Web Search](http://web.stanford.edu/class/cs276/)

### Buscadores
Para hacer buenos buscadores corporativos - hacen falta documentalistas profesionales. que comprueben 


- QUERY EXPANSION: Requiere un **Tesauro**.
	- Línea de investigación
	- Costoso de construir, pero máxima 
- USER RELEVANCE FEEDBACK
	- Que seleccione el usuario un documento y buscamos documentos similares
	- lanzamos el documento entero como una query
	- el más barato
	- Identifica el más relevante
- (hay más métodos)

Lo que hemos hecho es lanzar la bolsa de palabras (query expandida).

Por criterios de frecuencia, localización, etc. Sacamos los glosarios representativos de una temática.

Y comparamos los glosarios.
Las  palabras tienen que estar mínimamente relacionadas.
Para comparar glosarios, usaremos redes de términos (term nets)
Mirar si dos términos están relacionados:
	- Distancia: aparecen siempre pegados
	- Relevancia?


## Suponemos 
Generalmente se hacen por barrido, quitando las palabras vacías.
No entramos a términos nets. (Por qué unos términos deben estar relacionados con otras palabras)
Públicos solo están el de la UNESCO , CIENCIA
Entre 3 o 5K, palabras. 25 niveles. Clavas todo el vocabulario.
el trabajo equivalente entre 2 documentalistas más de un año


### PRECISIÓN - COBERTURA
- Precisión: acertar
- Cobertura: que se expandan demasiado



Básicamente hay 3 modelos de similaridad:
- Frecuencia. Booleano



> Ontology learning  

PNL, anáforas y elipsis.
Resolver anáforas en la representación de la interlingua.




## Conferencias
- TREC: [Text REtrieval Conference (TREC) Home Page](https://trec.nist.gov/)
- MUC: Message Understanding Conference ([Message Understanding Conference - Wikipedia](https://en.wikipedia.org/wiki/Message_Understanding_Conference))
	- cada dos años se propone un problema y se presentan las soluciones.
- Hay congresos de control of language

## Dos tipos de análisis semántico:
El que está cerca del concepto -> Ontología
El que está cerca de la lengua -> Interlingua (UNL)
	Sistemas de representaciones. Marcos - Redes semánticas

Saber cuando un documento dice lo mismo en otra lengua, está sin resolver.

El systrans ([SYSTRAN Translate](https://translate.systran.net/translationTools/text)) es el sistema que usa la unión europea. Para garantizar que todas las  cada día.
Los traductores iban a capturar inglés controlado, lo pones en el systrans.
Tiene fallos de 1 en 10K palabras

Traducción diaria de español 12M€ al año.



## Práctica
Se trata de diseñar y hacer un sistema que clasifique en 3 temas determinados, claramente distintos. 
Deportes, Salud y política (Recomendación)

Coger 20 temas de cada tema. Elegidos a mano.
Extraer el **Glosario**:  Vocabulario representativo de cada documento y conjunto de documentos.

Hacer un sistema capaz de en función 

Prueba de concepto.

Y contarlo bien como un informe.
Aplicando qué técnica.

El próximo día nos enseñará la práctica.

Son noticias cortas.