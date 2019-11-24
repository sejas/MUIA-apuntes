# a-12 Ingeniería Ontológica

# a12-00 Hands on for next week
11 de Noviembre 15:00 pm

Modelar ciertos datos. 
Universidades, CV, Descripciones de grados. En RDF.

Para la semana que viene modelo conceptual en papel, nada en powerpoint.
- Subclase D y Parte D, relaciones NArias. 
- Conocimiento disjunto.
Grupo de biología computacional.
Modelar un ejemplo

1. Relaciones en verde

Próxima clase en competencia
Trabajo en parejas

1. Escribir 20 líneas de este tipo que estén modernizando lo que hemos hecho con dibujo
	1. its a ~drug~
	2. its **name** is vemurafenib
	3. **formula**: C23H18
	4. **Exact mass**: 489
	5. is *efficient for* the melanoma
	6. *interaction inhibition with* CYP1A2 and 
	7. *interaction induction with* CYP3A4
2. Rehacer el dibujo del otro día en papel

- Rojo atributos
- Azul conceptos / clases
- Verde relaciones
- Morado para las instancias

- Leer capítulo 1 Ontological Engineering 


# Reusar
Construir nuevas aplicaciones ensamblando componentes ya construidos

# Compartir
Compartir es cuando diferentes aplicaciones usan algunos recursos.

Parte general -> Ontología
Parte específica  -> Conocimiento “especializado” para resolver nuestro problema.



Empezar a ensamblar 


1. Ontologías -> para ahorrar tiempo en el modelado 
2. Métodos de solución de problemas

- Ontologías
	- **Términos** básicos y **relaciones** que definen el vocabulario
		- parte de, disyunción,
	- Conceptualización
		- a translation
	- 3. Estructura jerárquica que define el domino. Skeletal foundation. Base de conocimiento
		- sub clase de, permite herencia
		- Toward distributed use of large-scale ontologies
	- **4. Describe el modelo que hay detrás de una base de conocimiento.**
	- 5. Es una conceptualización compartida, explícita específico y formal
		- un modelo abstracto y simplificado
		- Formal
			- Machine-readable: RDF, OWL
		- Explícito
			- conceptos, relación de propiedades, funciones , constantes axiomas que son explícitamente definidos
		- Compartido
			- conocimiento consensual
		- Conceptualización
			- modelo abstracto y simplificado de un fenómeno en el mundo que nosotros queremos representar.


# Distinguir el modelo de Tbox
## Nivel de conocimiento
Ontologías
- Tbox
- Abox

## Nivel de datos


Función : Se determina por los conceptos
	Madre de será una función. Porque una persona solo tiene una madre

Word net


- **Ontological Commitment** : El campo 

## Formatos de ontologías
- Lista plana de términos
- Diagrama para humanos SIOC ontology
- Protégé
- …

La máquina va a ver uris que serán relacionarles 
- Portal de datos de la biblioteca nacional
	- 3M de registros a RDF
	- elasticsearch

> No inventéis ningún término nuevo.  
> Utilizad uris ya existentes en otras ontologías  
> 	  

Clases -> ifastandards.info
	geo.linkeddata.es/ontology/Municipio
	xmlns.com/foaf/0.1/Organization
	dbpedia
	De dónde vamos a coger los términos?
	Habrá que inventar algunos, pero 
Instancias -> 


PLN
	GATE -> Inglés
	Feeling -> Español ([FreeLing 4.1 - Demonstration](http://nlp.lsi.upc.edu/freeling/demo/demo.php))



![](a-12%20Ingenieri%CC%81a%20Ontolo%CC%81gica/Captura%20de%20pantalla%202019-11-05%20a%20las%2018.28.40%202.png)

- **Top level ontology**: Ontología en la que se clasifica todo lo que existe en el universo