**Detección de Agentes automatizados en redes sociales**

```
Julián Santiago Flórez Castañeda
Camila Andrea Peña Caballero
Samuel Kalell Zuñiga Molina
```
```
Seminario de Investigación
```
```
Diego Armando García García
```
```
Universidad EAN
Ingeniería de Sistemas
Bogotá D.C.
2026
```

## Tabla de Contenidos


- Resumen
- Introducción
- Planteamiento del problema
- Justificación
   - Conveniencia
   - Relevancia social y tecnológica
   - Implicaciones prácticas
   - Valor teórico
   - Utilidad metodológica
- Objetivos
   - Objetivo general
   - Objetivos específicos
- Marco teórico
   - Agentes automatizados
   - Inteligencia artificial
   - Inteligencia artificial aplicada a agentes automatizados
   - Redes sociales
   - Inteligencia artificial en redes sociales
   - Inmersión
   - Autenticidad digital
   - Suplantación de identidad
   - Métodos de detección de cuentas automatizadas
   - X como plataforma de interacción digital
- Metodología
   - Enfoque de la investigación
   - Población y muestra
   - Técnicas de recolección de datos
   - Variables de estudio
   - Variables de análisis:
   - Procesamiento de datos
   - Instrumentos
   - Procedimiento
- Referencias


## Resumen

El uso creciente de agentes automatizados impulsados por inteligencia artificial en redes
sociales ha generado desafíos importantes para la autenticidad de la interacción digital y la
confiabilidad de las métricas de participación. En la plataforma X (antes Twitter), estos
sistemas automatizados o semiautomatizados pueden producir contenido, responder a usuarios
y participar en conversaciones de manera similar a cuentas humanas, lo que dificulta su
identificación y favorece la distorsión de métricas como la inmersión.

El presente estudio desarrolla un enfoque para la identificación de cuentas automatizadas en
redes sociales mediante el análisis combinado de características conductuales, temporales y
lingüísticas, y evalúa su impacto en los niveles de interacción asociados a las publicaciones
con las que participan. En lugar de recolectar datos directamente desde la API de X, la
investigación se basa en un dataset académico (colección de 2017) que contiene cuentas
etiquetadas como genuinas/tradicionales y como spam/bots.

A partir de este conjunto de datos histórico se extraerán rasgos conductuales, temporales y
lingüísticos, se entrenarán y evaluarán modelos de clasificación supervisada y no supervisada,
y se compararán las métricas de inmersión entre ambos tipos de cuentas. Se reconocen
limitaciones relacionadas con la antigüedad y posible sesgo de etiquetado del dataset, las cuales
se abordan mediante análisis de sensibilidad y validación en submuestras. Los resultados
aportarán evidencia sobre patrones discriminativos de cuentas automatizadas en la muestra
2017 y criterios útiles para su detección bajo condiciones similares de datos históricos.

**Palabras clave** : agentes automatizados, dataset 2017, cuentas spam, redes sociales,
inteligencia artificial, inmersión, análisis de datos


## Introducción

En los últimos años, las redes sociales se han consolidado como espacios centrales para la
comunicación, la formación de opinión pública y la difusión de información, razón por la
cual su funcionamiento y gobernanza se han convertido en un tema de interés académico y
social. Diversos estudios han mostrado que las decisiones de diseño algorítmico y las
dinámicas de interacción en plataformas como X (antes Twitter) afectan qué contenidos se
visibilizan, cómo se organiza el debate público y qué tipo de mensajes reciben más atención y
compromiso por parte de los usuarios (Ferrara et al., 2016; Gauthier et al., 2026; Ng &
Carley, 2025).

En este contexto, los denominados agentes automatizados sociales han adquirido un papel cada
vez más relevante. Estos sistemas automatizados o semiautomatizados son capaces de producir
contenido, interactuar con usuarios humanos y participar en conversaciones en línea, imitando
en gran medida el comportamiento de personas reales (Cresci et al., 2025; Ferrara et al., 2016;
Rodič, 2025). La creciente disponibilidad de modelos de lenguaje avanzados ha incrementado
la capacidad de estos agentes automatizados para generar textos coherentes y contextualmente
apropiados, reduciendo la diferencia perceptible entre mensajes humanos y automatizados
(Bender et al., 2021).

La expansión de estos agentes plantea un problema relevante para la autenticidad de la
interacción digital y para la calidad del espacio público en línea. Investigaciones recientes han
evidenciado que los agentes automatizados participan en campañas coordinadas de
desinformación, amplifican etiquetas y narrativas polarizantes y contribuyen a la difusión de
contenidos de baja credibilidad (Suarez-Lledo et al., 2025). Al mismo tiempo, se ha
demostrado que los patrones de actividad de cuentas automatizadas pueden distorsionar
métricas de inmersión, inflando artificialmente la visibilidad y la aparente popularidad de
determinadas publicaciones (Corsi et al., 2024; Milli et al., 2025).

Frente a este escenario, una línea de trabajo importante se ha centrado en la detección de
agentes automatizados mediante el análisis de características conductuales, temporales y
lingüísticas. Revisiones recientes muestran que se han propuesto múltiples enfoques que
combinan información sobre frecuencia y regularidad de publicación, redes de interacción y
rasgos del contenido textual, utilizando desde modelos clásicos de clasificación hasta
arquitecturas profundas más complejas (Cresci, 2020; Javed et al., 2024; Rodič, 2025). Sin


embargo, aún persisten desafíos relacionados con la capacidad de estos métodos para adaptarse
a la evolución de los agentes automatizados, al uso de modelos de lenguaje de última
generación y a la necesidad de comprender de manera más precisa su impacto sobre las
métricas de interacción y la percepción de autenticidad.

Por las restricciones de acceso a la API de X, esta investigación trabaja con un dataset provisto
por el profesor, correspondiente a una recolección realizada en 2017 que contiene cuentas
etiquetadas como humanas y como spam/bots. Este enfoque de análisis secundario permite
evaluar patrones conductuales, temporales y lingüísticos en una muestra etiquetada, aunque
limita la generalización de los resultados a cambios posteriores de la plataforma y a nuevas
técnicas de automatización. En consecuencia, el estudio se centrará en caracterizar y clasificar
las cuentas dentro del contexto temporal del dataset y en discutir la aplicabilidad de los
hallazgos a entornos actuales.

## Planteamiento del problema

El aumento de cuentas automatizadas en redes sociales representa un desafío para la
autenticidad de las interacciones digitales (Ferrara et al., 2016; Cresci, 2020). Estas cuentas
pueden operar de manera continua, generar grandes volúmenes de contenido y participar
activamente en discusiones públicas, imitando patrones de comportamiento típicamente
asociados a usuarios humanos (Ng & Carley, 2025).

El problema radica en que estos comportamientos automatizados pueden confundirse con
actividad humana, afectando la forma en que los usuarios perciben la información, la relevancia
de los mensajes y la interacción dentro de la plataforma (Cresci et al., 2025). Asimismo, los
agentes automatizados pueden alterar métricas de inmersión, distorsionando la representación
de la actividad social y generando popularidad y apoyo artificial a ciertos contenidos (Corsi
et al., 2024; Milli et al., 2025).

Por lo tanto, surge la necesidad de establecer criterios claros y sistemáticos que permitan
identificar cuentas automatizadas y evaluar su impacto en el ecosistema digital, teniendo en
cuenta las limitaciones de la evidencia disponible. En este contexto, la presente investigación
se plantea la siguiente pregunta: ¿Cómo identificar cuentas automatizadas en redes sociales
mediante criterios conductuales, temporales y lingüísticos usando un dataset etiquetado de
2017, y cuál es su impacto en el nivel de inmersión dentro de la plataforma en esa muestra
histórica?


## Justificación

Esta investigación se justifica porque busca analizar un fenómeno cada vez más frecuente en
redes sociales: la participación de agentes automatizados y semiautomatizados que aparentan
ser personas reales y conviven con cuentas humanas en los mismos espacios de interacción.
Estudios recientes han mostrado que una proporción significativa de la actividad en
plataformas como X procede de cuentas automatizadas, cuyos patrones de comportamiento
difieren de manera sistemática de los de los usuarios humanos. Comprender este
comportamiento es fundamental para entender cómo se construyen hoy las conversaciones
digitales y qué tan auténticas son las interacciones en una plataforma como X, especialmente
en un contexto donde la automatización y la inteligencia artificial se utilizan cada vez más para
intervenir en el espacio público en línea (Corsi et al., 2024; Ferrara et al., 2016).

### Conveniencia

El uso del dataset entregado por el profesor facilita el acceso a datos etiquetados y reduce la
dependencia de permisos o cuotas de API que actualmente limitan la recolección directa desde
X. Este enfoque es conveniente para aplicar técnicas de clasificación supervisada y evaluación
comparativa sobre instancias ya marcadas, acelerando la fase de experimentación y validación
metodológica. Además, el tema se relaciona directamente con el uso cotidiano de redes sociales
por parte de estudiantes, investigadores y la sociedad en general, lo que favorece su
comprensión y discusión en el contexto académico y contribuye a la formación en áreas como
ciencia de datos, inteligencia artificial y seguridad en entornos digitales.

### Relevancia social y tecnológica

La investigación tiene relevancia social porque la suplantación de humanos mediante agentes
automatizados basados en inteligencia artificial puede influir directamente en la formación de
la opinión pública, en la percepción de apoyo a determinadas ideas y en la difusión de
información en plataformas como X, donde se ha documentado la participación de cuentas
automatizadas en campañas coordinadas y en la amplificación de contenidos problemáticos.
Desde el punto de vista tecnológico, el estudio es relevante porque analiza el impacto del
avance reciente de la inteligencia artificial y de los modelos de lenguaje en la comunicación
digital y en el diseño de sistemas automatizados dentro de las redes sociales, en un contexto en
el que la literatura sobre detección de agentes automatizados y caracterización de sus patrones
de comportamiento muestra la necesidad de enfoques más robustos y actualizados para


identificar y mitigar los riesgos asociados a su actividad a gran escala (Chergarova et al., 2025;
Corsi et al., 2024; Javed et al., 2024; Suarez-Lledo et al., 2025).

### Implicaciones prácticas

Los resultados de esta investigación pueden ser útiles para identificar patrones de
comportamiento, actividad temporal y uso del lenguaje que faciliten el reconocimiento de
agentes automatizados o semiautomatizados en la plataforma X. A partir de estos patrones, es
posible proponer criterios y herramientas que ayuden a investigadores, plataformas digitales y,
en menor medida, a usuarios avanzados a distinguir con mayor precisión entre interacciones
humanas y automatizadas, lo que contribuye a mejorar la transparencia de las dinámicas de
inmersión en torno a determinados contenidos y a reducir la influencia de actividades
artificiales en la percepción de popularidad y apoyo dentro de las redes sociales.

### Valor teórico

El estudio aporta valor teórico al ampliar el conocimiento sobre la evolución del uso de agentes
automatizados y sistemas de inteligencia artificial en redes sociales, especialmente al
considerar los cambios ocurridos a partir de 2020 con la adopción masiva de modelos de
lenguaje avanzados. Al describir y comparar patrones de comportamiento, actividad temporal
y uso del lenguaje de cuentas humanas y automatizadas, así como su relación con distintos
niveles de inmersión, esta investigación contribuye a la discusión académica sobre
automatización, interacción digital y comportamiento en línea, ofreciendo un marco conceptual
y empírico que puede servir de base para futuros estudios orientados a la detección y análisis
de agentes automatizados en entornos sociales digitales.

### Utilidad metodológica

Desde el punto de vista metodológico, la investigación permite aplicar y combinar criterios
conductuales, temporales y lingüísticos para el análisis de cuentas en redes sociales, integrando
en un mismo enfoque dimensiones que suelen estudiarse de forma separada en la
caracterización de la actividad en plataformas como X. Esta articulación de distintos tipos de
rasgos, orientada específicamente a la identificación de agentes automatizados y al estudio de
su relación con la inmersión, puede servir como referencia para futuros estudios que busquen
analizar fenómenos similares de automatización y suplantación de identidad digital en entornos
sociales en línea, así como para el diseño y evaluación de nuevos métodos de detección basados
en análisis de comportamiento, tiempo y lenguaje (Javed et al., 2024; Rodič, 2025).


## Objetivos

### Objetivo general

Desarrollar un enfoque para la identificación de agentes automatizados en redes sociales
basado en características conductuales, temporales y lingüísticas, y analizar su influencia en
las métricas de inmersión.

### Objetivos específicos

1. Identificar patrones de comportamiento que diferencien cuentas humanas de cuentas
    automatizadas.
2. Definir características temporales asociadas a la actividad de agentes automatizados.
3. Analizar patrones lingüísticos presentes en publicaciones automatizadas.
4. Comparar el nivel de inmersión entre cuentas humanas y agentes automatizados.
5. Evaluar la efectividad de los criterios definidos para la clasificación de cuentas.

## Marco teórico

### Agentes automatizados

Un agente automatizado es un sistema digital que opera en una plataforma mediante distintos
niveles de automatización, con capacidad para ejecutar acciones de forma programada o
semiautónoma. Estos se apoyan en algoritmos o en Inteligencia Artificial para imitar
comportamientos humanos e interactuar con otros usuarios. Sus interacciones pueden parecer
auténticas, aunque sean procesos automatizados. (Cresci, 2020)

### Inteligencia artificial

Un agente inteligente, frecuentemente identificado como una instancia de inteligencia artificial
(IA), es una entidad autónoma capaz de percibir su entorno mediante sensores y actuar sobre
él mediante actuadores, dirigiendo su comportamiento hacia el logro de objetivos específicos.
En el campo de la IA, los agentes inteligentes se vinculan conceptualmente con los agentes
estudiados en economía, y distintas versiones de este paradigma se investigan en disciplinas
como las ciencias cognitivas, la ética, la filosofía de la razón práctica, así como en diversos
modelos sociocognitivos interdisciplinarios y en simulaciones sociales computacionales.
(Garófalo et al., 2020)

### Inteligencia artificial aplicada a agentes automatizados

La aplicación de la Inteligencia Artificial en Agentes Automatizados permite que estos
sistemas procesen información, respondan de manera autónoma y simulen una interacción más


cercana a la humana, lo que evidencia su utilidad en entornos donde la automatización y el
manejo del lenguaje son fundamentales. (Gordon Graell, 2023)

### Redes sociales

Las redes sociales son plataformas digitales formadas por comunidades de usuarios que se
conectan con otras personas, grupos u organizaciones para comunicarse, compartir información
y generar interacción en tiempo real. Se reconocen variedades de redes sociales, como
Instagram, Snapchat, X (antes Twitter), TikTok, etc. (Cristina, 1993)

### Inteligencia artificial en redes sociales

La Inteligencia Artificial aplicada a redes sociales consiste en el uso de algoritmos y técnicas
de aprendizaje automático y procesamiento de lenguaje natural para automatizar procesos,
analizar datos masivos, personalizar la experiencia del usuario y mejorar la seguridad y calidad
del contenido compartido en las plataformas. (Fadón et al., 2024)

### Inmersión

Aunque el término _inmersión_ originalmente alude a la experiencia de estar sumergido en el
agua, en este contexto se entiende como la sensación de desplazamiento perceptivo desde el
entorno real hacia un entorno no real. Esto provoca que la persona que interactúa con un móvil
o dispositivo electrónico concentre su atención en una experiencia que, aunque no pertenece al
mundo físico, es asumida subjetivamente como real. (Armenteros, M., & Fernández, M., 2011).

### Autenticidad digital

La autenticidad en redes sociales se entiende como el grado de coherencia, consistencia y
correspondencia entre la identidad que una persona proyecta en línea y aquello que realmente
desea comunicar. No solo implica mantener una presencia reconocible y alineada con ciertos
rasgos, valores o intereses. Se opone a la falsedad, la manipulación o la construcción deliberada
de imágenes artificiales que sean posibles de modificar, exagerar o fabricar identidades para
responder a expectativas sociales, estéticas o comerciales. (De Catalunya, 2015)

### Suplantación de identidad

La suplantación de identidad es una forma de delito digital en la que un tercero se apropia o
utiliza ilegítimamente la identidad de otra persona en entornos en línea, con el fin de engañar,
manipular o causar perjuicios, lo que convierte este fenómeno en un problema creciente para
la seguridad y la confianza en el ecosistema digital. (Lara et al., 2024)


### Métodos de detección de cuentas automatizadas

Los métodos de detección de cuentas automatizadas son procedimientos computacionales y
analíticos orientados a identificar cuentas que presentan comportamiento automatizado o
coordinado en plataformas sociales. Estos métodos emplean información del perfil del usuario,
del contenido publicado, de la actividad temporal, de las interacciones sociales y de la
estructura de la red para clasificar cuentas como humanas o automatizadas, utilizando técnicas
como machine learning, deep learning, análisis conductual, análisis de grafos y enfoques
multimodales. (Rodič, B., 2025).

### X como plataforma de interacción digital

X, conocida anteriormente como Twitter, es una plataforma de microblogueo y red social en
la que los usuarios pueden publicar mensajes breves, imágenes y videos, interactuar mediante
respuestas, “me gusta” y republicaciones, y seguir cuentas para conformar un flujo de
información personalizado. La plataforma se ha consolidado como uno de los espacios más
relevantes para la difusión rápida de información y la participación en conversaciones
públicas en tiempo real, lo que la convierte en un entorno especialmente propicio para
estudiar el comportamiento de cuentas humanas y de agentes automatizados, así como su
impacto en los niveles de inmersión asociados a diversos contenidos (Gómez & García
Torres, 2010).

## Metodología

### Enfoque de la investigación

El estudio se plantea desde un enfoque cuantitativo, ya que trabaja con datos medibles y
observables derivados directamente de la actividad en plataformas de redes sociales. El diseño
es no experimental, puesto que no se manipulan variables ni se interviene en el comportamiento
de las cuentas; en cambio, se observan y registran los datos tal como ocurren en el entorno
digital. A partir de este enfoque, la investigación es a la vez descriptiva y correlacional: por un
lado, busca caracterizar los patrones que diferencian cuentas humanas de agentes
automatizados y, por otro, analiza cómo dichas características se relacionan con el nivel de
inmersión dentro de la plataforma.

**_Diseño de la investigación_**

El estudio es de tipo transversal, dado que los datos se recolectan en un único momento del
tiempo y no a lo largo de diferentes periodos o cohortes. Se analizan cuentas reales existentes


en la plataforma X sin conformar grupos de control ni aplicar ningún tipo de intervención
experimental. El diseño contempla la comparación de dos tipos de cuentas:

- Cuentas humanas
- Cuentas automatizadas o semiautomatizadas (agentes automatizados)

Esta comparación permite identificar patrones diferenciales de comportamiento, actividad
temporal y uso del lenguaje entre ambos tipos de cuentas, así como su relación con métricas de
inmersión (Nguyen et al., 2024).

### Población y muestra

La población está compuesta por cuentas públicas originalmente activas en la plataforma X en

2017. Muestra: subconjunto provisto en el dataset entregado por el profesor, compuesto por
cuentas etiquetadas como humanas y cuentas etiquetadas como spam/bots. La selección no es
probabilística: depende de la composición del dataset original y de criterios de inclusión usados
en la recolección de 2017 (por ejemplo, nivel mínimo de actividad o disponibilidad de
publicaciones). Se excluirán cuentas con metadatos insuficientes para el cálculo de rasgos
conductuales, temporales o lingüísticos.

Se excluirán cuentas privadas o con información insuficiente para el análisis de características
conductuales, temporales y lingüísticas.

### Técnicas de recolección de datos

Dado que los datos fueron provistos, la fase de recolección consistirá en la verificación y
documentación del dataset: revisión de columnas disponibles, tipos de variables, recuentos
por etiqueta, y verificación del estado de seudonimización. No se realizará nueva recolección
desde la API; en su lugar, se procederá con un análisis secundario que respete las condiciones
éticas y legales bajo las cuales se compartió el dataset.

### Variables de estudio

```
Variable independiente:
```
- Tipo de cuenta: humana o agente automatizado
**Variable dependiente:**
- Nivel de inmersión (total de interacciones: respuestas, "me gusta" y compartidos)

### Variables de análisis:

```
Dimensión Variables
```

```
Conductuales Frecuencia de publicación; relación entre publicaciones y respuestas;
nivel de actividad general
Temporales Intervalos entre publicaciones; regularidad en los horarios de actividad;
actividad continua sin interrupciones
Lingüísticas Variación en el lenguaje; repetición de estructuras textuales; coherencia
y consistencia del contenido
```
La combinación de estas tres dimensiones de análisis sigue el enfoque propuesto en la literatura
reciente sobre detección de agentes automatizados, que señala que ninguna dimensión por sí
sola es suficiente para la identificación de cuentas automatizadas. (Alzahrani et al., 2025)

### Procesamiento de datos

Los datos recolectados serán sometidos a las siguientes etapas de preprocesamiento:

1. Limpieza: eliminación de ruido, datos duplicados e información irrelevante.
2. Normalización: estandarización de formatos (fechas, textos, identificadores).
3. Tokenización: segmentación del texto en unidades mínimas de análisis (palabras, n-
    gramas).
4. Extracción de características: cálculo de rasgos conductuales, temporales y lingüísticos
    a partir de los datos procesados.

Este proceso transforma los datos en bruto en información estructurada y utilizable para el
análisis, siguiendo prácticas estándar en investigación con datos de redes sociales (Nguyen
et al., 2024).

**_Técnicas de análisis_**

Para el análisis de los datos se emplearán las siguientes técnicas:

- Clasificación supervisada: para distinguir agentes automatizados de cuentas humanas a
    partir de los rasgos extraídos. Se evaluarán modelos como árboles de decisión,
    máquinas de soporte vectorial (SVM) u otros clasificadores según la distribución de los
    datos (Nguyen et al., 2024).
- Agrupamiento (clustering): para identificar grupos con patrones similares de
    comportamiento, sin necesidad de etiquetas previas, lo que permite detectar estructuras
    latentes en los datos (Gangula & Rega, 2024).


- Análisis estadístico descriptivo y correlacional: para comparar niveles de inmersión
    entre cuentas humanas y agentes automatizados, e identificar relaciones entre las
    variables de análisis y el nivel de interacción.

El desempeño de los modelos de clasificación será evaluado mediante métricas estándar:
precisión (precision), sensibilidad (recall) y exactitud (accuracy).

### Instrumentos

Para el desarrollo del estudio se utilizarán las siguientes herramientas:

- Python y R como lenguajes principales para la recolección, procesamiento y análisis de
    datos.
- Scripts de recolección de datos vía API de X.
- Librerías especializadas de procesamiento de texto y análisis de lenguaje natural (por
    ejemplo, NLTK, spaCy o equivalentes).
- Software de análisis estadístico y visualización de datos.

Estas herramientas permiten automatizar tanto la recolección como el análisis de la
información, garantizando reproducibilidad y escalabilidad del proceso.

### Procedimiento

El proceso se desarrollará en las siguientes etapas secuenciales:

1. Recolección de datos públicos desde la plataforma X.
2. Limpieza, filtrado y seudonimización de la información.
3. Extracción de características conductuales, temporales y lingüísticas.
4. Clasificación de cuentas mediante técnicas supervisadas y de agrupamiento.
5. Análisis del nivel de inmersión por tipo de cuenta.
6. Interpretación de resultados y elaboración de conclusiones.

En todo el proceso se utilizará únicamente información pública, omitiendo cualquier dato
personal o sensible, en cumplimiento de las condiciones de uso de la plataforma y de los
principios éticos aplicables a la investigación con datos digitales.


## Referencias

```
Alzahrani, O., Beale, R., & Hendley, B. (2025). Bots Don’t Sit Still: A
Longitudinal Study of Bot Behaviour Change, Temporal Drift, and
Feature-Structure Evolution. http://arxiv.org/abs/2512.
Armenteros, M., & Fernández, M. (2011). Inmersión, presencia y flow.
Contratexto, (19), 165-177.
Bender, E. M., Gebru, T., McMillan-Major, A., & Shmitchell, S. (2021). On
the dangers of stochastic parrots: Can language models be too big?
FAccT 2021 - Proceedings of the 2021 ACM Conference on Fairness,
Accountability, and Transparency, 610–623.
https://doi.org/10.1145/3442188.
Chergarova, V., Tomeo, M., Albataineh, E., Mutale, W., Scarpino, J. J., &
Morgan, H. (2025). Using artificial intelligence (AI) to spread
misinformation and fake content within social media posts. Issues in
Information Systems, 26(4), 322–331.
https://doi.org/10.48009/4_iis_2025_
```

Corsi, G., Marino, B., & Wong, W. (2024). The spread of synthetic media on
X. Harvard Kennedy School Misinformation Review, 5(3).
https://doi.org/10.37016/mr- 2020 - 140

Cresci, S. (2020). A decade of social bot detection. Communications of the
ACM, 63(10), 72–83. https://doi.org/10.1145/

Cresci, S., Yang, K. C., Spognardi, A., Di Pietro, R., Menczer, F., &
Petrocchi, M. (2025). Demystifying Misconceptions in Social Bots
Research. Social Science Computer Review.
https://doi.org/10.1177/

Cristina, V. Q. (1993). _Redes sociales: Un concepto con importantes
implicaciones en la intervención comunitaria - ProQuest_.
https://www.proquest.com/openview/28b49b6763e96e8dfef335de125cf
e4/1?pq-origsite=gscholar&cbl=

De Catalunya, U. O. (2015). ¿Autenticidad o autopromoción en las redes
sociales?
https://comein.uoc.edu/divulgacio/comein/es/numero49/articles/Article-
Gemma-San-Cornelio.html

Fadón, J. a. R., Cristófol, F. J., & Agudo, D. P. (2024). _IA: motor de cambio
en El Español y sus redes sociales_. Dialnet.
https://dialnet.unirioja.es/servlet/articulo?codigo=

Ferrara, E., Varol, O., Davis, C., Menczer, F., & Flammini, A. (2016). The rise
of social bots. Communications of the ACM, 59(7), 96–104.
https://doi.org/10.1145/

Gangula, R., & Rega, S. (2024). Enhanced Detection of Social Bots on Online
Platforms using SemiSupervised K-Means Clustering. Journal of Sensors,
IoT & Health Sciences, 2(1), 17–27.
https://doi.org/10.69996/jsihs.

Garófalo, J. a. C., Salazar, J. a. V., Guevara, C. a. S., & Chisag, Á. G. R.
(2020). _Inteligencia artificial, sistemas inteligentes, agentes inteligentes_.
Dialnet. https://dialnet.unirioja.es/servlet/articulo?codigo=

Gauthier, G., Hodler, R., Widmer, P., & Zhuravskaya, E. (2026). The political
effects of X’s feed algorithm. Nature. https://doi.org/10.1038/s41586-
026 - 10098 - 2

Gómez, L. M., & García Torres, C. (2010). Twitter. Colombian Journal of
Anestesiology, 38(4), 539–540.
[http://www.scielo.org.co/scielo.php?script=sci_arttext&pid=S0120-](http://www.scielo.org.co/scielo.php?script=sci_arttext&pid=S0120-)
33472010000400011&lng=en&nrm=iso&tlng=es


Gordon Graell, R. D. (2023). _Vista de chatbots e inteligencia artificial:_
https://revistas.up.ac.pa/index.php/antataura/article/view/3930/

Información sobre las API de X. (s/f). Recuperado el 19 de abril de 2026, de
https://help.x.com/es/rules-and-policies/x-api

Javed, D., Jhanjhi, N. Z., Khan, N. A., Ray, S. K., Mazroa, A. Al, Ashfaq, F.,
& Das, S. R. (2024). Towards the future of bot detection: A
comprehensive taxonomical review and challenges on Twitter/X.
Computer Networks, 254. https://doi.org/10.1016/j.comnet.2024.

Lara, R. a. M., Benavides, J. O. B., Orbea, J. C. M., Vivero, G. N., & Angulo,
R. M. M. (2024). Estrategias innovadoras para mitigar la suplantación de
identidad en redes sociales. _Revista Científica Multidisciplinar G-
nerando_ , _5_ (1), 544–561. https://doi.org/10.60100/rcmg.v5i1.

Milli, S., Carroll, M., Wang, Y., Pandey, S., Zhao, S., & Dragan, A. D. (2025).
Engagement, user satisfaction, and the amplification of divisive content
on social media. PNAS Nexus, 4(3).
https://doi.org/10.1093/pnasnexus/pgaf

Ng, L. H. X., & Carley, K. M. (2025). A global comparison of social media
bot and human characteristics. Scientific Reports, 15(1).
https://doi.org/10.1038/s41598- 025 - 96372 - 1

Nguyen, H.-D., Nguyen, D. Q., Nguyen, C.-D., To, P. T., Nguyen, D. H.,
Nguyen-Gia, H., Tran, L. H., Tran, A. Q., Dang-Hieu, A., Nguyen-Duc,
A., & Quan, T. (2024). Supervised learning models for social bot
detection: Literature review and benchmark. Expert Systems with
Applications, 238, 122217.
https://doi.org/https://doi.org/10.1016/j.eswa.2023.

Rodič, B. (2025). Social Media Bot Detection Research: Review of Literature.
https://arxiv.org/pdf/2503.

Suarez-Lledo, V., Ortega-Martin, E., Carretero-Bravo, J., Ramos-Fiol, B., &
Alvarez-Galvez, J. (2025). Unraveling the Use of Disinformation
Hashtags by Social Bots During the COVID-19 Pandemic: Social
Networks Analysis. JMIR Infodemiology, 5.
https://doi.org/10.2196/


