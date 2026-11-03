# Ideas de proyecto 

## Índice
1. Idea 1 — ...
2. Idea 2 — ...
3. Idea 3 — Detección de fraude bancario con IA

## Idea 1 — ...
(contenido)

## Idea 2 — ...
(contenido)

## Idea 3 — Detección de fraude bancario con IA
Detección y prevención del fraude bancario mediante Inteligencia Artificial

Autor: Daniel y Eduardo

Problema

El fraude en transferencias es uno de los problemas más costosos del sector bancario. Los sistemas tradicionales fallan por dos lados opuestos: dejan pasar fraude que, visto de forma aislada, 
parece normal (falsos negativos), y bloquean a clientes legítimos (falsos positivos), lo que genera quejas y pérdida de confianza. Se suma una autenticación anticuada —tarjetas de coordenadas 
y claves de firma— incómoda y fácil de robar mediante engaño. El reto no es solo detectar fraude, sino hacerlo sin molestar al cliente honesto.

Usuarios
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

Técnicas y tecnología

Python con Pandas (procesado), Scikit-learn (modelos de clasificación para la capa del emisor) y una librería de grafos (NetworkX) para la capa del receptor. Como reto técnico, 
los datos están muy desbalanceados (el fraude es una fracción mínima), por lo que se usarán técnicas específicas y métricas adecuadas (precisión y exhaustividad), no el porcentaje de acierto global.

Viabilidad

Alta. Se apoya en datos públicos ya disponibles y en técnicas abordables dentro del máster. Se plantea por fases: prototipo que clasifica transacciones por riesgo → panel de visualización para analistas → camino hacia una integración real. Combina dos técnicas complementarias (clasificación + grafos), lo que aporta profundidad sin salirse de lo realizable.

Riesgos
Datos desbalanceados: exige un tratamiento cuidadoso para que el modelo no "aprenda" a decir siempre que no hay fraude.
La capa del emisor (detectar manipulación) es la más difícil; se plantea como un conjunto de señales de comportamiento, no como una certeza.
Ajuste de umbrales: dónde se pone la frontera entre permitir, avisar y bloquear condiciona todo el sistema.
Biometría: requiere contemplar un método alternativo para quien no pueda usarla y cuidar la privacidad del dato biométrico.
