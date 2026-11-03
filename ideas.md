# Ideas de proyecto 

## Índice
1. Idea 1 — ...
2. Idea 2 — Mantenimiento predictivo mediante IA
3. Idea 3 — Detección de fraude bancario con IA

## Idea 1 — ...
(contenido)

## Idea 2 — Mantenimiento predictivo mediante IA
Mantenimiento predictivo que permita anticipar posibles fallos enmáquinas y equipos industriales

Autor: Antonio y Pamela

### Descripción

Desarrollo de un sistema de mantenimiento predictivo que permita anticipar posibles fallos en máquinas y equipos industriales mediante el análisis de datos de funcionamiento.

El sistema utilizará información procedente de sensores —como temperatura, vibración, presión, consumo energético y horas de funcionamiento— junto con el historial de averías y mantenimientos
realizados. Mediante modelos de Machine Learning y técnicas de detección de anomalías, la plataforma identificará comportamientos inusuales y estimará el riesgo de fallo de los equipos. 
A partir de estos resultados, generará alertas para que los responsables de mantenimiento puedan intervenir antes de que se produzca una avería grave.

La solución incluirá un dashboard para supervisar el estado de las máquinas, consultar su historial y priorizar las intervenciones según el riesgo y el impacto potencial de cada fallo.

### Problema

En muchas instalaciones industriales, el mantenimiento se basa principalmente en dos estrategias:

- Mantenimiento correctivo: reparar la máquina después de que se averíe.
- Mantenimiento preventivo: realizar revisiones periódicas según un calendario establecido.

El mantenimiento correctivo puede ocasionar paradas imprevistas, pérdidas de producción y reparaciones costosas. Por su parte, el preventivo puede generar intervenciones innecesarias, ya que
una máquina puede estar en buen estado cuando le corresponde una revisión. Además, los datos generados por sensores e historiales de mantenimiento no siempre se aprovechan para anticipar 
fallos o identificar patrones que permitan mejorar la planificación.

### Usuarios

- Principal: responsables de mantenimiento industrial, ingenieros de mantenimiento y técnicos de
planta.
- Secundario: responsables de producción, operaciones, calidad y dirección industrial.
- Empresas objetivo: fábricas, plantas de producción, empresas energéticas, instalaciones logísticas y organizaciones que dependen de maquinaria crítica para operar.

### Solución actual

Las empresas suelen combinar planes de mantenimiento preventivo, inspecciones técnicas, sistemas de gestión del mantenimiento informatizado (CMMS) y plataformas de monitorización industrial.
Algunas utilizan soluciones como IBM Máximo, SAP EAM o sistemas especializados de monitorización de equipos.
Estas herramientas pueden registrar averías, programar revisiones y supervisar variables de funcionamiento. Sin embargo, no todas las organizaciones disponen de modelos predictivos 
personalizados o aprovechan sus datos históricos para anticipar fallos.
La propuesta sería incorporar una capa de análisis predictivo que transforme los datos operativos en alertas de riesgo y recomendaciones de mantenimiento.

### Valor

- Reducción de las paradas imprevistas, anticipando posibles averías.
- Disminución de los costes de reparación, al detectar problemas antes de que se agraven.
- Mejora de la planificación del mantenimiento, priorizando las máquinas que necesitan atención.
- Aumento de la disponibilidad de los equipos y de la continuidad de la producción.
- Optimización de los recursos técnicos y de los repuestos, evitando intervenciones innecesarias.
- Mejora de la seguridad operativa, cuando la detección temprana permite prevenir fallos con consecuencias peligrosas.

## Idea 3 — Detección de fraude bancario con IA
Detección y prevención del fraude bancario mediante Inteligencia Artificial

Autor: Daniel y Eduardo

### Problema

El fraude en transferencias es uno de los problemas más costosos del sector bancario. Los sistemas tradicionales fallan por dos lados opuestos: dejan pasar fraude que, visto de forma aislada, 
parece normal (falsos negativos), y bloquean a clientes legítimos (falsos positivos), lo que genera quejas y pérdida de confianza. Se suma una autenticación anticuada —tarjetas de coordenadas 
y claves de firma— incómoda y fácil de robar mediante engaño. El reto no es solo detectar fraude, sino hacerlo sin molestar al cliente honesto.

### Usuarios

Banco / entidad financiera: reduce pérdidas económicas y bloqueos innecesarios.
Analista antifraude: revisa las operaciones marcadas y entiende el motivo de cada decisión.
Cliente final: más seguridad ante estafas y menos fricción en sus operaciones legítimas.
Propuesta de producto

Sistema que analiza cada transferencia en tiempo real desde sus dos extremos y decide si permitir, avisar o bloquear:

Capa 1 — El emisor: detecta si el comportamiento es raro para esa persona concreta (destinatario nuevo, importe inusual, hora extraña, prisas, desvío de su patrón histórico), como señal de que puede estar siendo manipulado mediante una estafa.
Capa 2 — El receptor: construye un grafo de transacciones para identificar cuentas mula, que reciben dinero de muchas víctimas y lo reenvían rápido para borrar el rastro.
Decisión: ambas capas se combinan en una puntuación de riesgo → permitir / avisar / bloquear.
Confirmación por biometría: cuando una operación es dudosa, se confirma con huella o cara desde el móvil, en lugar de tarjeta de coordenadas o clave de firma. Más seguro y más cómodo.
Datos y acceso

Se trabajaría con datasets públicos de transacciones que simulan transferencias entre cuentas identificadas (emisor y receptor), necesarios para construir el grafo: por ejemplo PaySim o IBM AML (AMLSim). 
Para la capa de comportamiento también sirve el dataset de Credit Card Fraud Detection de Kaggle. Son datos abiertos y descargables, sin información personal real, lo que garantiza el acceso a una muestra desde el inicio.

### Técnicas y tecnología

Python con Pandas (procesado), Scikit-learn (modelos de clasificación para la capa del emisor) y una librería de grafos (NetworkX) para la capa del receptor. Como reto técnico, 
los datos están muy desbalanceados (el fraude es una fracción mínima), por lo que se usarán técnicas específicas y métricas adecuadas (precisión y exhaustividad), no el porcentaje de acierto global.

### Viabilidad

Alta. Se apoya en datos públicos ya disponibles y en técnicas abordables dentro del máster. Se plantea por fases: prototipo que clasifica transacciones por riesgo → panel de visualización para analistas → camino hacia una integración real. Combina dos técnicas complementarias (clasificación + grafos), lo que aporta profundidad sin salirse de lo realizable.

### Riesgos
Datos desbalanceados: exige un tratamiento cuidadoso para que el modelo no "aprenda" a decir siempre que no hay fraude.
La capa del emisor (detectar manipulación) es la más difícil; se plantea como un conjunto de señales de comportamiento, no como una certeza.
Ajuste de umbrales: dónde se pone la frontera entre permitir, avisar y bloquear condiciona todo el sistema.
Biometría: requiere contemplar un método alternativo para quien no pueda usarla y cuidar la privacidad del dato biométrico.
