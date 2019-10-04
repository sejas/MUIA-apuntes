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



