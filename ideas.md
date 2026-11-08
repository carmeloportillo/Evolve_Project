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
# Detección y prevención del fraude bancario mediante Inteligencia Artificial

**Autor:** Daniel y Eduardo

## Descripción

Prototipo de Data Science que analiza transferencias bancarias para **generar alertas revisables** que ayuden a un analista antifraude a priorizar qué operaciones investigar. A diferencia de un enfoque clásico basado en reglas fijas, estudia cada operación desde sus dos extremos: el comportamiento de quien envía el dinero y la posición de la cuenta que lo recibe dentro de la red de transacciones.

Mediante modelos de Machine Learning y análisis de grafos, el sistema estima el riesgo de cada transferencia y entrega una lista priorizada de alertas con el motivo de cada una. El alcance es deliberadamente realista: el sistema **señala operaciones para revisión humana**, no bloquea pagos ni decide en tiempo real. Incluiría, como evolución, un dashboard para que el analista supervise las alertas y consulte el grafo de cuentas.

## Problema

El fraude en transferencias es uno de los problemas más costosos del sector bancario. Los sistemas tradicionales basados en reglas fijas fallan por dos lados opuestos: dejan pasar fraude que, visto de forma aislada, parece normal (falsos negativos), y marcan a clientes legítimos (falsos positivos), lo que genera quejas y coste de revisión. El reto no es solo detectar fraude, sino **priorizar bien qué revisa el analista**, reduciendo las falsas alarmas sin perder los casos importantes.

## Usuarios

- **Principal:** el analista antifraude de una entidad financiera, que revisa las operaciones marcadas y necesita saber el motivo de cada alerta.
- **Secundario:** la entidad (reduce pérdidas y revisiones innecesarias) y los responsables de riesgo.
- **Beneficiario indirecto:** el cliente final, que sufre menos bloqueos injustos.

## Solución actual

Los bancos combinan reglas fijas (umbrales por importe, listas de destinatarios), sistemas de scoring internos y, en algunos casos, modelos antifraude propios. Estas soluciones registran y bloquean operaciones, pero muchas se basan en reglas que generan muchas falsas alarmas y no aprovechan la estructura de red entre cuentas. La propuesta añade una capa de análisis en dos extremos (comportamiento del emisor + posición del receptor en un grafo) que prioriza mejor las alertas para el analista.

## Fuentes de datos

Para analizar emisor y receptor hace falta datos de transferencias entre cuentas identificadas, con fechas e historial (no transacciones sueltas). Hay que comprobar qué fuente lo permite de verdad, sin dar por hecho que se pueden combinar datasets distintos para cubrir cada capa:

- **A verificar como opción real:** *Elliptic dataset*, grafo real de transacciones etiquetadas (lícito / ilícito), con datos reales, aunque sobre criptoactivos.
- **Como simulación con límites explícitos:** PaySim o IBM AML (AMLSim); sirven para montar el prototipo, pero no acreditan un caso real validable.
- **Descartado para el caso real:** el dataset de tarjetas de Kaggle, porque no permite seguir cuentas emisoras y receptoras.

## MVP

Un sistema que, a partir de un histórico de transferencias, genera alertas revisables ordenadas por riesgo, con el motivo de cada una (comportamiento atípico del emisor + posición sospechosa del receptor en el grafo). La validación clave: comparar las alertas frente a un **baseline de reglas sencillas**, con una **evaluación temporal** (entrenar con un periodo, probar con el siguiente), midiendo con precisión y exhaustividad por el desbalance de los datos.

## Valor

- Menos falsas alarmas y mejor priorización de lo que revisa el analista.
- Detección de estructuras de cuentas mula que un análisis de transacciones sueltas no vería.
- Revisión más rápida y fundamentada, con el motivo de cada alerta.
- Base realista que puede evolucionar hacia un producto bancario real.

## Límites

- Una operación anómala **no demuestra manipulación**: el sistema señala para revisión, no concluye que haya fraude.
- Sin bloqueo automático ni decisión en tiempo real: solo alertas para un humano (queda como evolución futura).
- Biometría fuera del alcance: confirmar la identidad no resuelve el problema, porque el titular puede estar autorizando la transferencia bajo engaño.
- Dependencia de la fuente de datos: sin datos reales trazables, las conclusiones son limitadas y deben declararse.
- Datos muy desbalanceados: exigen tratamiento y métricas cuidadosas.

## Dudas que podemos comprobar

- ¿Existe una fuente real con emisor, receptor, fecha e historial a la que tengamos acceso? 
- ¿Las alertas del modelo mejoran de forma medible frente a un baseline de reglas sencillas en una evaluación temporal?
- ¿Podemos contar con un analista (o alguien que simule ese rol) que valore si las alertas le resultan útiles?
- ¿Con qué antelación y en qué formato le sirve una alerta al analista para que tenga valor real?
