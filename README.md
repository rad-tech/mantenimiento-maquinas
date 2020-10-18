# Estimación inicial de un proyecto de desarrollo de software.

## 1. Introducción.
La idea de realizar este trabajo surge después de la asistencia virtual a conferencias y charlas de algunas comunidades latinas de desarrolladores que encontré en [Twitter](https://twitter.com), en las que con frecuencia se realiza la pregunta **¿Cómo estimo un proyecto?** Hay videos y artículos (muy buenos) que tratan del tema, pero en ninguno se desarrolla un ejercicio completo, y por lo tanto, considero que la pregunta todavía no tiene respuesta (al menos que yo sepa).<br>

Mi intención es desarrollar las diferentes actividades que se requieren para **hacer una estimación inicial (de tiempo y costo) de un proyecto**, que sirva como ejemplo completo y práctico para un **freelancer** (que generalmente trabaja solo).<br>

Este trabajo se basa en el **modelo en Cascada**, ¿por qué?, por las herramientas utilizadas. Basado en mi experiencia, los proyectos de desarrollo de software son siempre para ayer, con fuertes restricciones de tiempo y costo y mucha incertidumbre en cuanto a requerimientos. Después de una estimación inicial podemos determinar si el desarrollo del software se dirige por el modelo en Cascada o de manera ágil con SCRUM, por ejemplo.

No estoy casado con ninguna metodología, si algo de una te sirve en otra, úsalo, nadie te va a meter a la cárcel por eso, el objetivo es tener un sóftware que satisface los requerimientos del cliente, dentro del tiempo y presupuesto establecidos (*jaja, ésta es la teoría académica*). Y recuerda, **ésta es una estimación inicial basada en los conocimientos actuales** que tienes del proyecto en cuestión, **deja esto bien claro al cliente**, muchos toman esta estimación como el costo definitivo del proyecto.

**Hay que poder definir (por el bien de Cliente y del Desarrollador) cuándo un producto está terminado y cuándo el alcance a variado y hay que cobrar más y ocupar más tiempo para hacerlo**.

## 2. Herramientas utilizadas.

1. [OSRMT 1.8](https://sourceforge.net/projects/osrmt/)<br>
   Open Source Requirements Management Tools, una aplicación de escritorio que permite definir Capacidades (Features), Requerimientos, Diseño, Implementación y Casos de prueba, basado en Cascada.<br>
   Existe una versión web [nimble](https://sourceforge.net/projects/nimble/) que soporta Cascada y Ágil, pero es más complejo de instalar y configurar, por lo que no lo usaré aquí.

2. [StarUML 3.2.2 (evaluation edition)](http://staruml.io/)<br>
   Aplicación de escritorio que permite crear diagramas y modelos UML 2.0.

3. [ProjectLibre 1.9.2 (community edition)](https://www.projectlibre.com/)<br>
   Aplicación de escritorio que permite realizar planeación y administración de proyectos basados en cascada.

## 3. Entrevista inicial con usuario.
Me encontré en [Youtube](https://youtube.com) un video en el que se explica una forma de realizar un **plan de mantenimiento preventivo de maquinaria**, tan bien desarrollado, que se me ocurrió usarlo como ejemplo de una entrevista inicial con un usuario ficticio que requiere de un software que le permita realizar y ejecutar el plan y te contrata para que hagas el desarrollo. Tiene suficientes elementos para mostrar los diferentes aspectos a considerar en un desarrollo de software.

Antes de continuar te invito a que veas el siguiente video [7 PASOS PARA REALIZAR UN PROGRAMA DE MANTENIMIENTO | ISO 9001](https://www.youtube.com/watch?v=umnJt1e9lWM)

Te propongo un reto, estima el tiempo y costo de desarrollo del software para éste cliente, a ojo de pájaro, sin ningún análisis como el que vamos a desarrollar aquí, anótalo. Ahora, haz el ejercicio completo y vé cuanto tiempo y costo obtienes. Tal vez te sorprendas de lo barato que los estabas dejando.

### 3.1 Notas de la entrevista inicial.
Estas son mis notas obtenidas durante la entrevista inicial.

```
ISO-9001

1. identificación de máquinas, asignando un código
	a) código de proceso PRoducción, LoGistica, CAlidad, ManTenimiento
	a.1) subproceso opcional
	b) código por ser una máquina: MaQuina, Seguimiento y Medición
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
	b) actividades de manto. realizadas por operador o por personal de mantenimiento

6. Crear ficha de mantenimiento correctivo
	Datos: mismos datos que mantenimiento preventivo
	       Comentarios acerca de falla de la máquina
	       Persona que reporta
	       Fecha del reporte
	       Mantenimiento realizado
	       Fecha de entrega de la máquina
	       Responsable del manteniminento

7. Crear carpeta de mantenimiento por máquina

Manual de la máquina
```

## 4. Identificación de cosas que quedan fuera del alcance del proyecto.
Aqui pon cosas que identifiques y que el cliente no ha mencionado, es muy probable que los haya dado por hecho, y cuando presentes la propuesta (o antes, si es posible), pregunta al cliente si quiere incluirlas en el proyecto (entonces se convertiran en capacidades y requerimientos).

1. Administración de usuarios
2. Administración de localidades

## 5. Requerimientos no funcionales.
Despliegue - Aplicación web en intranet

### 6. Requerimientos funcionales.

### 6.1 Características (Features).

### 6.2 Requerimientos funcionales.

## 7. Priorización

## 8. Riesgos.
El análisis de riesgos es una parte muy importante, porque si identificas un riesgo de impacto medio o alto que no pueda ser eliminado, tal vez no deberías continuar con la ejecución del proyecto.

Inicialmente todos los riesgos tienen prioridad alta, en la presentación de la propuesta (o antes si es posible), se aclara la probabilidad de ocurrencia y se determina su impacto, modificando su estado.

En el archivo **mm-analisis_riesgos.ods** (Libre Office) presento el análisis correspondiente.

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

## 9. Estimación de tiempo y costos.
Recuerda, **esta es una estimación inicial**, en circunstancias de **alta incertidumbre** ya que sólo has tenido una entrevista con el cliente, y debe ser actualizado conforme avanza el proyecto, debido principalmente a cambios en el alcance y los requerimientos.

Calcula costos para la implementación de las cosas que quedan fuera del alcance del proyecto y la resolución de los riesgos, para que sepas cuánto más va a costar el proyecto en caso de ser incluidas, así también podrás informar inmediatamente el costo extra, cuando el cliente te diga que sí quiere incluir algo que propones.

Incluye **TODAS** las actividades a realizar durante el proyecto, presentaciones, juntas, lecturas de documentos propios del cliente, investigación y pruebas de API o WSDL, instalación y configuración de servidores de aplicaciones o bases de datos, módulos no especificados por el cliente pero sabes que tienes que hacerlos (menús, configuración de la aplicación, ayuda contextual, control de acceso) etc.

Por supuesto, incluye el tiempo que te lleva preparar la propuesta inicial.

Para estimar tiempo para hacer algo, considera lo siguiente: a) sabes como hacerlo y los has hecho antes, b) no lo has hecho, pero sabes como se hace, c) no tienes idea de como se hace.

En el archihvo **mm-estimacion.pod** (ProjectLibre) presento la estructura de desglose de trabajo y estimación de tiempo y costos.

### 9.1 Costos fijos
#### Energía eléctrica, teléfono, internet.
El importe mensual de cada uno de estos conceptos divídelo entre 30.4, este es el importe diario que pagas, cárgalo al proyecto, por los días que le dediques.

#### Amortización de equipos (computadoras, impresoras).
A estos equipos, contablemente (en México) se les calcula una vida útil de dos años. Divide el valor de compra entre 24 y tendrás la depreciación mensual de tu equipo. Cárgalo al proyecto, por los meses que le dediques.

#### Licencias de software.
Incluye la compra de software y los pagos mensuales/anuales que hagas a GitHub, Heroku, Notion y todo el software que uses para hacer tu trabajo. Igual, calcula el importe mensual y cárgalo al proyecto, por los días que le dediques.

## 9. Propuesta
En el archivo **mm-propuesta.odt** (Libre Office) te muestro un ejemplo de propuesta, que, una vez aceptada, llevará a la firma de un contrato. 

## Apéndice 1 - Agilidad
Aún cuando tomé un curso de **Scrum Master** y he leído varios libros y visto decenas de videos, todavía no encuentro respuestas a lo siguiente (por eso, siendo honesto, no me certifiqué, como todos mis compañeros de curso):

a) **la experimentación** - apenas tienes tiempo para terminar, casi siempre se deja el código como salió a la primera.

b) **el falla pronto** - asociado a la experimentación, ¿tienes tiempo de fallar? 

c) **bienvenidos los cambios** - en verdad ¿con cuánta rapidez puedes responder a los cambios? Aun con SOLID, Design Patterns, Arquitectura de software, etc. ¿Cuántas veces aceptas cambiar algo?

d) **MVP** - para mí, lo que tiene valor para el cliente, tiene dependencias, y hay que desarrollar esas dependencias antes de poder darle algo de valor.

e) **estimaciones por puntos** - que no se convierten en tiempo! Entonces ¿cómo sabes cuántos Sprints vas a necesitar?

f) **estimaciones realizadas por un equipo que todavía no existe** durante una estimación inicial.

Con estas dudas ya entendí lo que es el mindset ágil, no es sólo repetir palabras, es algo mucho más complejo.

Obviamente necesito participar en un proyecto ágil, o una formateada de cerebro :)

## Apéndice 2 - Microadministración
No caigas en la trampa de la Microadministración, te vas a ahorcar tú mismo. Microadministrar es registrar tantas cosas, que te lleva más tiempo hacerlo, que lo que te lleva construir el software. El registro al minuto, de qué haces es muy frecuente en las empresas de consultoría, en donde tienes que justificar tu tiempo con bitácoras. A tu cliente le importa el software, no tu bitácora, y si acaso te la pide, **aclarale que le va a costar y el proyecto tomara mas tiempo para completarse**.



**eof**