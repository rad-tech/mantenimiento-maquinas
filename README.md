# Estimación inicial de un proyecto de desarrollo de software. (English version? see Readme_en.md)
**Work in progress (90%)**

## 1. Introducción.
La idea de realizar este trabajo surge después de la asistencia virtual a conferencias y charlas de algunas comunidades latinas de desarrolladores que encontré en [Twitter](https://twitter.com), en las que con frecuencia se realiza la pregunta **¿Cómo estimo un proyecto?** Hay videos y artículos (muy buenos) que tratan del tema, pero en ninguno se desarrolla un ejercicio completo, y por lo tanto, considero que la pregunta todavía no tiene respuesta (al menos que yo sepa).<br>

Mi intención es desarrollar las diferentes actividades que se requieren para **hacer una estimación inicial (de tiempo y costo) de un proyecto**, que sirva como ejemplo completo y práctico para un **freelancer** (que generalmente trabaja solo).<br>

Este trabajo se basa en el **modelo en Cascada**, ¿por qué?, por las herramientas utilizadas. Basado en mi experiencia, los proyectos de desarrollo de software son siempre para ayer, con fuertes restricciones de tiempo y costo y mucha incertidumbre en cuanto a requerimientos. Después de una estimación inicial podemos determinar si el desarrollo del software se dirige por el modelo en Cascada o de manera ágil con SCRUM, por ejemplo.

No estoy casado con ninguna metodología, si algo de una te sirve en otra, úsalo, nadie te va a meter a la cárcel por eso, el objetivo es tener un sóftware que satisface los requerimientos del cliente, dentro del tiempo y presupuesto establecidos (*jaja, ésta es la teoría académica*). Y recuerda, **ésta es una estimación inicial basada en los conocimientos actuales** que tienes del proyecto en cuestión, **deja esto bien claro al cliente**, muchos toman esta estimación como el costo definitivo del proyecto.

**Hay que poder definir (por el bien del Cliente y del Desarrollador) cuándo un producto está terminado y cuándo el alcance a variado y hay que cobrar más y ocupar más tiempo para hacerlo**.

## 2. Herramientas utilizadas.

1. [OSRMT 1.8](https://sourceforge.net/projects/osrmt/)<br>
   Open Source Requirements Management Tools, una aplicación de escritorio que permite definir Capacidades (Features), Requerimientos, Diseño, Implementación y Casos de prueba, basado en Cascada.<br>
   Existe una versión web [nimble](https://sourceforge.net/projects/nimble/) que soporta Cascada y Ágil, pero es más complejo de instalar y configurar, por lo que no lo usaré aquí.

2. [StarUML 3.2.2 (evaluation edition)](http://staruml.io/)<br>
   Aplicación de escritorio que permite crear diagramas y modelos UML 2.0.

3. [ProjectLibre 1.9.2 (community edition)](https://www.projectlibre.com/)<br>
   Aplicación de escritorio que permite realizar planeación y administración de proyectos basados en cascada.

4. [LibreOffice](https://www.libreoffice.org/discover/libreoffice/)<br>
   Aplicaciones para Hojas de cálculo y procesamiento de texto, entre otras.

**Aunque no instales las herramientas utilizadas, podrás revisar archivos de imágen o pdf creados para este propósito (vé el Apendice A3.2).**

## 3. Entrevista inicial con usuario.
Me encontré en [Youtube](https://youtube.com) un video en el que se explica una forma de realizar un **plan de mantenimiento preventivo de maquinaria**, tan bien desarrollado, que se me ocurrió usarlo como ejemplo de una entrevista inicial con un usuario ficticio que requiere de un software que le permita realizar y ejecutar el plan y te contrata para que hagas el desarrollo. Tiene suficientes elementos para mostrar los diferentes aspectos a considerar en un proyecto de desarrollo de software.

Antes de continuar te invito a que veas el siguiente video [7 PASOS PARA REALIZAR UN PROGRAMA DE MANTENIMIENTO | ISO 9001](https://www.youtube.com/watch?v=umnJt1e9lWM)

*Te propongo un reto, estima el tiempo y costo de desarrollo del software para éste cliente, a ojo de pájaro, sin ningún análisis como el que vamos a desarrollar aquí, anótalo. Ahora, haz el ejercicio completo y vé cuanto tiempo y costo obtienes. Tal vez te sorprendas de la diferencia.*

El proceso de estimación es iterativo, no se realiza una tarea y luego otra. Se van construyendo todos los elementos poco a poco ya que están muy interrelacionados. Mientras defines un Requerimiento funcional, se te ocurre un posible riesgo, o algo que estaría fuera del alcance. Cuando estás estimando, te das cuenta que te falta un Requerimiento o una Definición o un Requerimiento no funcional, etc.

**La estimación la comienzo determinando las funcionalidades y los requerimientos asociados a ellas. Necesito además definir las pruebas de aceptación, qué cosas parecen estar fuera del alcance, así como definiciones (todo esto en OSRMT). Junto con esto voy identificando riesgos (hoja de cálculo), y el modelo de dominio (staruml). Se puede ir armando la estrucura de trabajo (ProjectLibre), pero prefiero, una vez tengo todo definido en OSRMT, exportar los datos a un archivo CSV, agrupar y ordenar y luego pegar la lista en ProjectLibre, para hacer las estimaciones de tiempo y costo.**

¿Has escuchado de **Parálisis del Análisis**? Es un error cometido en el que nunca comienzas a trabajar realmente, porque nunca terminas de analizar. Lleva tu análisis a un detalle razonable, en el que te sientas cómodo y te permita hacer una estimación realista.

### 3.1 Notas de la entrevista inicial.
Estas son mis notas obtenidas durante la entrevista inicial.

```
ISO-9001

1. Identificación de máquinas, asignando un código
	a) código de proceso PRoducción, LoGistica, CAlidad, ManTenimiento
	a.1) subproceso opcional
	b) código por ser una máquina: MaQuina, equipo de Seguimiento y Medición
	c) consecutivo por tipo de máquina: Estampadora-01, Laser-02
	d) consecutivo por cantidad: secuencial

2. Listado de máquinas:
	Datos: Máquina, Código (paso 1), Marca, Modelo, No. de serie, [Ubicación,] Estado [Activa, Mantenimiento]

3. Identificar las máquinas:
	a) Etiquetado (adherible), Marcado (pintura)
	Datos: Nombre de máquina, código

4. Crear plan de mantenimiento preventivo
	a) Periodicidad: Diario, Semanal, Quincenal, Mensual, Bimestral, Trimestral, Semestral, Anual
	b) formato: mm-formato-plan_manto.png

5. Crear ficha de mantenimiento preventivo (individual por máquina - mm-formato-ficha_manto.png)
	a) archivar ficha cada vez que se realiza mantenimiento
	b) actividades de mantenimiento. realizadas por operador o por personal de mantenimiento

6. Crear ficha de mantenimiento correctivo
	Datos: mismos datos que mantenimiento preventivo
	       Comentarios acerca de falla de la máquina
	       Persona que reporta
	       Fecha del reporte
	       Mantenimiento realizado
	       Fecha de entrega de la máquina
	       Responsable del manteniminento

7. Crear carpeta de mantenimiento por máquina

Manual de usuario de la máquina
```
Cada uno de los números en la lista anterior será una Capacidad del sistema.

## 4. Identificación de cosas que quedan fuera del alcance del proyecto.
Aqui pon cosas que identifiques y que el cliente no ha mencionado, es muy probable que los haya dado por hecho, y cuando presentes la propuesta (o antes, si es posible), pregunta al cliente si quiere incluirlas en el proyecto (entonces se convertiran en capacidades y requerimientos).

## 5. Requerimientos no funcionales.
Utiliza la clasificación **FURPS+** (yo utilizo los mnemónicos indicados). Normalmente, los requerimientos no funcionales se orientan al sistema completo más que a Capacidades individuales.

TIPO|DESCRIPCION|MNEMONICO
-|-|-
**Usability**	|	fUrps - Usabilidad	|	USA  
Human factors	|		|	HFA  
Aesthetics	|		|	AES  
UI consistency	|		|	UIC  
Context Help	|		|	CHP  
Wizard	|		|	WIZ  
User documentation	|		|	DOC  
Traning material	|		|	TRA  

TIPO|DESCRIPCION|MNEMONICO
-|-|-
**Reliability**|	fuRps - Confiabilidad	|	REL  
Frecuency of failure	|		|	FRF  
Severity of failure	|		|	SVF  
Recoverability	|		|	REC  
Predicatability	|		|	PRE  
Accuracy	|		|	ACC  
MTBF	|		|	MTBF 

TIPO|DESCRIPCION|MNEMONICO
-|-|-
**Performance**	|	furPs - Rendimiento	|	PER  
Speed	|		|	SPD  
Efficiency	|		|	EFF  
Availability	|		|	AVA  
Accuracy	|		|	ACCU 
Throughput	|		|	THR  
Response time	|		|	RSP  
Recovery time	|		|	RCT  
Resource usage	|		|	RSU  

TIPO|DESCRIPCION|MNEMONICO
-|-|-
**Supportability**	|	furpS - Factores durante/despues implementación	|	SUP  
Testability	|	Mocks	|	TST  
Extensibility	|		|	EXT  
Adaptability	|		|	ADP  
Maintainability	|		|	MAI  
Compatibility	|	Web, Cliente, SO, Servidor	|	COM  
Configurability	|		|	CNF  
Serviceability	|	parches	|	SRV  
Instalability	|	setup	|	INS  
Localizability	|	I18N	|	LOC  
Scalability	|		|	SCA  

TIPO|DESCRIPCION|MNEMONICO
-|-|-
**Design**	|	MVC, N capas, OOP, Estructurado, Distribuido	|	DES  
**Implementation**	|	Estandards, Frameworks, Lenguaje, Entorno de operacion	|	IMP  
**Interface**	|	Web services, Protocolos, Formatos de archivo	|	INT  
**Physical**	|	Hardware	|	PHY  

### 6. Características y Requerimientos funcionales.

### 6.1 Características (Features).

TIPO|DESCRIPCION|MNEMONICO
-|-|-
Feature	|	Característica	|	FEA
Out of scope	|	Cosas fuera del alcance del proyecto	|	OOS  
Definition	|	Una definición para Diccionario de datos	|	DEF  
Fact	|	Hecho	|	FAC  
Law	|	Ley	|	LAW  
Policy	|	Politica empresarial	|	POL  
SLA	|	Service Level Agreement	|	SLA  
Rule	|	Regla	|	RUL  
Assumption	|	Suposición	|	ASS  

### 6.2 Requerimientos funcionales.

TIPO|DESCRIPCION|MNEMONICO
-|-|-
**Requirement**	|	Functional requirement	|	FUN  
**Security**	|	Seguridad, es un requerimiento funcional	|	SEC  

### 6.3 Productos finales (entregables/outcomes).
TIPO|DESCRIPCION|MNEMONICO
-|-|-
Prod-Screen	|	Pantalla	|	PSCR 
Prod-Report	|	Reporte	|	PREP 
Prod-Process	|	Procesamiento de datos	|	PPRO 
Prod-Artifact	|	Archivo PDF, CSV, Documento	|	PART 
Prod-Service	|	SOAP, Rest	|	PSER 

### 6.4 Trazabilidad.
La trazabilidad establece una relación entre artefactos, que comienza en Capacidades que se traducen a Requerimientos, que dan origen a Diseños que se Implementan y deben Probarse. Facilita el análisis de impacto cuando se solicita un cambio, así como la identificación del orígen de un artefacto (justificación de por qué existe).

### 6.5 Dependencia.
Es la relación que existe entre artefactos, que permite identificar qué va antes de qué, o qué tiene que haberse hecho antes de considerar algo como terminado. Se representa por una matríz de dependencias y es útil para realizar la priorización (no puedes construir un techo si no tienes paredes que lo soporten). Esta tarea se realiza cuando empiezas a diseñar el sistema, no tiene caso hacerlo para la estimación inicial.

## 7. Modelo de Dominio.
Es muy importante, ya que te permite identificar actores, objetos (entidades), relaciones y dependencias entre objetos, etc. En base a él podrás determinar la complejidad de cada requerimiento funcional, operaciones a realizar, atributos por objetos, etc.

**mm-dominio.mdj** (StarUML)

Las clases con color de fondo blanco son las identificadas en la entrevista inicial. Las clases con fondo azul, corresponden a cosas que están fuera del alcance actualmente. Las clases con fondo amarillo son copias de la original (blanco), las uso para evitar cruces de líneas en el modelo.

## 8. Priorización.
Los requerimientos iniciales formarán parte de la versión 1.0, a partir de ahí se irán agregando más módulos (los que estan fuera de alcance, si el cliente los acepta) o nuevos requerimientos. Después de la propuesta inicial, deberá determinarse la prioridad de cada uno de las capacidades a desarrollar.

## 9. Riesgos.
El análisis de riesgos es una parte muy importante, porque si identificas un riesgo de impacto medio o alto que no pueda ser eliminado, tal vez no deberías continuar con la ejecución del proyecto.

Inicialmente todos los riesgos tienen prioridad alta, en la presentación de la propuesta (o antes si es posible), se aclara la probabilidad de ocurrencia y se determina su impacto, modificando su estado y las acciones a implementar.

En el archivo **mm-analisis_riesgos.ods** (Libre Office) presento el análisis correspondiente. Los riesgos deberán monitorearse durante el desarrollo del software, pues su estatus puede cambiar, además de surgir nuevos.

Probabilidad|Significado
-|-
0|El riesgo no puede ocurrir
100|El riesgo es seguro que ocurra

Impacto|Significado
-|-
0|La ocurrencia del riesgo no afecta al proyecto.
100|La ocurrencia/no mitigación del riesgo puede impedir el éxito del proyecto.

Respuesta|Significado
-|-
Evitar|Tomar acciones para eliminar la causa o los efectos del riesgo.
Transferir|Transferir el riesgo a un tercero.
Mitigar|Tomar acciones para disminuir la probabilidad de ocurrencia o impacto del riesgo.
Aceptar|No se toman acciones hasta que el riesgo ocurre.

## 10. Estimación de tiempo y costos.
Recuerda, **esta es una estimación inicial**, en circunstancias de **alta incertidumbre** ya que sólo has tenido una entrevista con el cliente, y debe ser actualizado conforme avanza el proyecto, debido principalmente a cambios en el alcance y los requerimientos.

Calcula costos para la implementación de las cosas que quedan fuera del alcance del proyecto y la resolución de los riesgos, para que sepas cuánto más va a costar el proyecto en caso de ser incluidas, así también podrás informar inmediatamente el costo extra, cuando el cliente te diga que sí quiere incluir algo que propones.

Incluye **TODAS** las actividades a realizar durante el proyecto, presentaciones, juntas, lecturas de documentos propios del cliente, investigación y pruebas de API o WSDL, instalación y configuración de servidores de aplicaciones o bases de datos, cotizaciones, capacitación de usuarios, redacción de manuales, módulos no especificados por el cliente pero sabes que tienes que hacerlos (menús, configuración de la aplicación, ayuda contextual, control de acceso) etc. **Recuerda que en México existe la Ley de Protección de Datos Personales en Posesión de Particulares**, si guardas datos de los usuarios, debes apegarte esta ley.

Hay ocasiones en que tendrás que importar datos ya existentes al nuevo sistema, pueden estar en CSV, Base de datos, TXT. Estima el tiempo de proceso ETL para importarlos al nuevo sistema. Necesitarás validar la integridad de los datos.

¿Tienes que aprender algo nuevo? Estima tiempo, no el costo, a menos que sea un conocimiento específico para este cliente.

Por supuesto, incluye el tiempo que te lleva preparar la propuesta inicial.

Para estimar tiempo para hacer algo, considera lo siguiente: <br>
a) Sabes como hacerlo y los has hecho antes, <br>
b) No lo has hecho, pero sabes como se hace, <br>
c) No tienes idea de como se hace.

En el archihvo **mm-estimacion.pod** (ProjectLibre) presento la estructura de desglose de trabajo y estimación de tiempo y costos.

### 10.1 Costos fijos.

#### 10.1.1 Energía eléctrica, teléfono, internet, renta de oficina.
El importe mensual de cada uno de estos conceptos divídelo entre 30.4, este es el importe diario que pagas, cárgalo al proyecto, por los días que le dediques.

#### 10.1.2 Amortización de equipos (computadoras, impresoras).
A estos equipos, contablemente (en México) se les calcula una vida útil de dos años. Divide el valor de compra entre 24 y tendrás la depreciación mensual de tu equipo. Cárgalo al proyecto, por los meses que le dediques.

#### 10.1.3 Licencias de software.
Incluye la compra de licencias software y los pagos de suscripciones mensuales/anuales que hagas a GitHub, Heroku, mailtrap, Notion y todo el software que uses para hacer tu trabajo. Igual, calcula el importe mensual y cárgalo al proyecto, por los meses que le dediques.

#### 10.1.4 Utilidad
Determina el porcentaje de utilidad que quieres obtener e inclúyelo en los costos.

## 11. Propuesta
En el archivo **mm-propuesta.odt** (Libre Office) te muestro un ejemplo de propuesta, que, una vez aceptada, llevará a la firma de un contrato. 

## Apéndice 1 - Agilidad
Aún cuando tomé un curso de **Scrum Master** y he leído varios libros y visto decenas de videos, todavía no encuentro respuestas a lo siguiente (por eso, siendo honesto, no me certifiqué, como todos mis compañeros de curso):

a) **la experimentación** - apenas tienes tiempo para terminar, casi siempre se deja el código como salió a la primera.

b) **el falla pronto** - asociado a la experimentación, ¿tienes tiempo de fallar? 

c) **bienvenidos los cambios** - en verdad ¿con cuánta rapidez puedes responder a los cambios? Aun con SOLID, Design Patterns, Arquitectura de software, etc. ¿Cuántas veces aceptas cambiar algo?

d) **MVP** - para mí, lo que tiene valor para el cliente, tiene dependencias, y hay que desarrollar esas dependencias antes de poder darle algo de valor.

e) **estimaciones por puntos** - que no equivalen a tiempo! Entonces ¿cómo sabes cuántos Sprints vas a necesitar?

f) **estimaciones realizadas por un equipo que todavía no existe** durante una estimación inicial.

Con estas dudas ya entendí lo que es el mindset ágil, no es sólo repetir palabras, es algo mucho más complejo.

Obviamente necesito participar en un proyecto ágil, o una formateada de cerebro :)

## Apéndice 2 - Microadministración.
No caigas en la trampa de la Microadministración, te vas a ahorcar tú mismo. Microadministrar es registrar tantas cosas, que te lleva más tiempo hacerlo, que lo que te lleva construir el software. El registro al minuto, de qué haces es muy frecuente en las empresas de consultoría, en donde tienes que justificar tu tiempo con bitácoras. A tu cliente le importa el software, no tu bitácora, y si acaso te la pide, **aclarale que le va a costar y el proyecto tomara mas tiempo para completarse**.


## Apéndice 3 - Recursos.

### A3.1 Herramientas.
[OSRMT 1.8](https://sourceforge.net/projects/osrmt/)

[ProjectLibre](https://sourceforge.net/projects/projectlibre/)

[ProjectLibre Tutorial](https://www.youtube.com/watch?v=9xwR4JCBaIU&feature=youtu.be)

[StarUML](http://staruml.io/)

[LibreOffice](https://www.libreoffice.org/discover/libreoffice/)

[mdbtools](https://github.com/mdbtools/mdbtools) ```sudo apt-get install mdbtools``` para extraer la tabla *ARTIFACT* de *starter.mdb*
```mdb-export starter.mdb artifact >requerimientos.csv```

### A3.2 Archivos del análisis.

En la carpeta análisis:<br>
1. *mm-formato-ficha_manto.png* Imágen del formato de Ficha de mantenimiento usado por el cliente.<br>
2. *mm-formato-plan_manto.png* Imágen del formato de Plan de mantenimiento usado por el cliente.<br>
3. *starter.mdb* Base de datos Access usada por OSRMT, contiene las listas de Capacidades, Requerimientos y Pruebas de aceptación.<br>
4. *mm-requerimientos.csv* Lista de Capacidades y Requerimientos extraídos de *starter.mdb*.<br>
5. *mm-dominio.jpg* Imágen del diagrama e dominio. Corresponde a *mm-dominio.mdj* de StarUML.<br>
6. *mm-analisis_riesgos.pdf* Archivo pdf el análisis de riesgos. Corresponde a *mm-analisis_riesgos.ods* de LibreOffice.<br>
7. *mm-estimacion.pdf* Archivo pdf del cálculo de tiempo y costos. Corresponde a *mm-estimacion.pod* de ProjectLibre.<br>
8. *mm-propuesta.pdf* Archivo pdf de la propuesta inicial. Corresponde a *mm-propuesta.odt* de LibreOffice.<br>

### A3.3 Libros:
1. OpenProj The open source solution for managing your projects, Lisa A. Bucki
2. Mastering Non-Functional Requirements, Sameer Paradkar, Packt Publishing
3. SWEBOK 3.0 IEEE Computer Society
4. BABOK 3.0, International Institute of Business Analysis
5. PMBOK 5th edition, Project Management Institute, Inc.
6. Practice Standard for Project Risk Management, Project Management Institute, Inc.
7. Practice Standard for Work Breakdown Structures 2nd Edition, Project Management Institute, Inc.
8. Practice Standard for Project Estimating, Project Management Institute, Inc.
9. Análisis y diseño de sistemas 8a edición, Kendall & Kendall, Pearson
10. Ingeniería de software 9a edición, Sommerville, Pearson
11. El Lenguaje Unificado de Modelado (UML 2.0), Grady Booch James Rumbaugh, Ivar Jacobson, Addison Wesley
12. El Lenguaje Unificado de Modelado - Manual de referencia (UML 2.0), Grady Booch James Rumbaugh, Ivar Jacobson, Addison Wesley

### A3.4 Videos relacionados:
1. Laura Ribas. [Cómo poner el precio correcto a tus productos/servicios](https://www.youtube.com/watch?v=2Lg14wmlQwI&feature=youtu.be)
2. Hector De León. [¿Cuánto cobrar como programador freelance? Ejemplo paso a paso](https://www.youtube.com/watch?v=UrocE07Bev4)
3. Hector De León. [¿Cómo cobrar un proyecto de software?](https://www.youtube.com/watch?v=sdAiDJt-1lA)
4. Fernando Herrera. [Cuánto cobrar por un trabajo](https://www.youtube.com/watch?v=Dc0PgJm3KA0&feature=youtu.be)
5. Rodolfo Borja. [Calcular el costo por hora](https://www.youtube.com/watch?v=2Ogj2Wp6TGU)
6. Rodolfo Borja. [Cómo estimar las horas de un proyecto](https://www.youtube.com/watch?v=xo_HFjYkgS8)
7. Rodolfo Borja. [Cómo hacer la propuesta de un proyecto](https://rborja.net/como-hacer-una-propuesta-de-software/)


**eof**
