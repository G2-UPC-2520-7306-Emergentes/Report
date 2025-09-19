# Capítulo II: Requirements Elicitation & Analysis

## 2.1 Competidores

#### IBM Food Trust
**Qué hace:** Plataforma empresarial de trazabilidad y transparencia para alimentos; integra productores, procesadores, retailers y consumidores.  
**Cómo funciona:** Incluye módulos que permiten registrar cada etapa del lote (desde cosecha hasta venta), gestionar certificados, generar reportes verificables, y mostrar al consumidor final el historial completo del producto al escanear un código QR.  
**Por qué nos importa:** Porque demuestra que es posible lograr trazabilidad extremo a extremo con tiempos de rastreo muy cortos, lo cual valida la viabilidad de nuestro pasaporte digital por lote con blockchain.

#### VeChain ToolChain
**Qué hace:** Servicio de trazabilidad que conecta blockchain, IoT y códigos QR/NFC para registrar eventos en la cadena de suministro, permitiendo a marcas y agricultores certificar origen, calidad y autenticidad del producto.  
**Cómo funciona:** Permite capturar datos del campo, incorporar certificaciones digitales, registrar eventos en blockchain, proporcionar herramientas de verificación al consumidor, y realizar auditorías sobre condiciones de transporte o almacenamiento.  
**Por qué nos importa:** Es un buen referente de cómo manejar el equilibrio entre seguridad, costo y experiencia del usuario, especialmente en entornos donde la cadena productiva es extensa.

#### Connecting Food (LiveAudit / LiveTrack / LiveScan)
**Qué hace:** Suite centrada en trazabilidad alimentaria con auditoría continua y visibilidad, permitiendo que los lotes sean rastreados, verificados contra estándares de calidad, y mostrados al consumidor mediante QR.  
**Cómo funciona:** Compara automáticamente los datos del lote con certificaciones o reglas de calidad, alerta cuando hay discrepancias, permite seguimiento completo del lote y ofrece al usuario final un historial claro con certificados, fotos o registros de inspecciones.  
**Por qué nos importa:** Añade una capa de compliance muy valiosa (verificación constante de afirmaciones como "orgánico" o denominación de origen), lo que puede diferenciar a FoodChain si lo integramos desde el inicio.

## 2.2 Análisis competitivo

A continuación, se presenta la tabla de competidores para analizar cada punto específico de algunos referentes globales en **trazabilidad alimentaria basada en blockchain**. Con esto alinearemos la propuesta de **FoodChain** al valor que nuestro segmento objetivo (productores, logística, procesadores, retailers y consumidores) realmente requiere.


| **Competitive Analysis Landscape** |  |
| --- | --- |
| **¿Por qué llevar a cabo este análisis?** | **Definir con evidencia cómo FoodChain se posiciona frente a soluciones consolidadas (IBM Food Trust, VeChain ToolChain, Connecting Food) en: alcance de trazabilidad, integridad y auditoría, velocidad de rastreo, facilidad de integración y adecuación al mercado LATAM.** |
|  | **Objetivo: priorizar funcionalidades del MVP, drivers arquitectónicos (rendimiento, seguridad, escalabilidad) y tácticas comerciales B2B/SaaS, manteniendo la consulta gratuita para el consumidor.** |

| ***Competidor*** |  | FoodChain (Startup) | IBM Food Trust | VeChain ToolChain | Connecting Food |
| --- | --- | --- | -- | -- | -- |
| ***Logo*** |  | ![foodchaing.jpeg](../assets/img/foodchaing.jpeg)| ![IBM.jpeg](../assets/img/IBM.jpeg) | ![vechaing.jpeg](../assets/img/vechaing.jpeg) | ![connecting.png](../assets/img/connecting.png) |
| ***Perfil*** | Overview | Plataforma **SaaS** de **trazabilidad alimentaria** con **pasaporte digital por lote** (QR/NFC). Cada evento (cosecha, transporte, procesamiento, empaque) queda **registrado** y anclado en **blockchain**; aplicaciones móviles y web para registrar y auditar; el **consumidor** escanea **QR** y ve historia, mapa de ruta, fechas y **certificados**. Enfoque en **América Latina** con servicio gratuito para el consumidor. | Plataforma empresarial de trazabilidad multi-actor con módulos **Trace**, **Consumer**, **Documents** e **Insights**; probada en grandes retailers y sus redes de proveedores; reducción del tiempo de rastreo de **días a segundos** en casos emblemáticos. | Plataforma **blockchain-as-a-service** sobre **VeChainThor** con **QR/NFC** e **IoT**; adoptada por retail para exponer al consumidor origen, rutas y resultados de inspecciones por **lote**. | Suite de **trazabilidad con auditoría digital continua** por lote (**LiveAudit/LiveTrack/LiveScan**); verifica especificaciones en tiempo real y muestra al consumidor la historia **batch-level** vía QR. |
|  | ***Ventaja competitiva – ¿Qué valor ofrece a los clientes?*** | **Transparencia de extremo a extremo** con **registro inmutable**, **validación de certificaciones** en cadena y **gestión de crisis** (recall por lote) en minutos; **UX simple** (QR) para el **consumidor** y acompañamiento a **productores** de LATAM. | **Madurez y escala**; módulos integrales para trazabilidad, certificados y analítica; referencia operativa de rastreo “en segundos”. | **Ecosistema** con SDK/QR/NFC e integración IoT; enfoque de **transparencia al consumidor** con despliegues en retail. | **Compliance continuo** con alertas tempranas; alto valor para asegurar **claims** (orgánico, DO, libre de X) y reducir retiros. |
| ***Perfil de Marketing*** | ***Mercado objetivo*** | **Productores** (B2B pagantes) y **consumidor final** (consulta gratuita). | Grandes **retailers/fabricantes** y su red de **proveedores**; también orientado a compartir datos con **consumidores** vía módulo Consumer. | **Retail y marcas** con foco en categorías frescas/de riesgo y **consumidores** que escanean para ver datos del lote. | **Marcas/procesadores** que requieren **auditoría por lote** y **consumidores** que escanean QR para ver la historia real del producto. |
|  | ***Estrategias de marketing*** | **Pilotos** con productores, co-branding con **QR** al consumidor, narrativa de **confianza/seguridad** y **suscripción B2B**; consumidor **gratis**. | Venta **enterprise**, alianzas con retailers e integradores; guías de adopción por categoría. | Partnerships con retailers/consultoras; comunicación de **transparencia** al consumidor y casos por vertical. | Casos de éxito en **auditoría continua** y reducción de recalls; mensajes a **Calidad/QA** y prueba de **claims**. |
| ***Perfil de Producto*** | ***Productos & Servicios*** | Apps móviles/web para registrar eventos de lote; **API** y contratos/“anclaje” en blockchain; tablero de **auditoría** y **página QR** para el consumidor (historia, mapa, certificados). | **Trace/Consumer/Documents/Insights**: *track & trace*, certificados y analítica cercana al tiempo real. | **ToolChain** con SDK + QR/NFC/IoT; registro on-chain y portales de verificación para consumidor. | **LiveAudit** (auditoría continua), **LiveTrack** (trazabilidad por lote), **LiveScan** (vista consumidor vía QR). |
|  | ***Precios & Costos*** | **SaaS B2B** por suscripción (productores y marcas registran productos); **consumidor gratis**. | Suscripción **enterprise** por módulos/escala. | **BaaS** con costos operativos/on-chain según uso e integración. | **SaaS** por volumen/auditorías/QR, con soporte de integración. |
|  | ***Canales de distribución (Web y/o Móvil)*** | Web y apps móviles. | Web y apps móviles. | Web y apps móviles. | Web y apps móviles. |
| ***Análisis SWOT*** | ***Fortalezas*** | **Pasaporte digital por lote**, registro **inmutable**, **validación de certificaciones**, **recall eficiente**, UX de **escaneo QR** y foco en **productores** y **consumidor** en LATAM. | Escala global, confianza de grandes marcas, módulos integrales y rastreo **en segundos**. | Ecosistema con herramientas listas, adopción en retail y **exposición directa** al consumidor. | Auditoría continua y alertas, transparencia **batch-level** y énfasis en cumplimiento de calidad. |
|  | ***Debilidades*** | **Marca nueva** y necesidad de **onboarding** multi-actor; requiere tracción y casos de referencia. | Barrera de entrada para pymes; posible rigidez de personalización. | Percepción de cadena **pública** en entornos regulados; dependencia de tarifas on-chain/gobernanza. | Menor foco en LATAM; dependencia de **calidad de datos** de proveedores. |
|  | ***Oportunidades*** | Regulaciones de trazabilidad en **LATAM**, diferenciación de marca mediante QR, interés del **consumidor** por origen y **certificaciones**. | Expansión sectorial/geográfica y presión por seguridad alimentaria. | Extender categorías y adopción en retail; integración con IoT. | Mayor presión regulatoria sobre **claims** y demanda de auditoría continua. |
|  | ***Amenazas*** | Adopción lenta en pymes, cambios regulatorios, presión de precios y competencia de suites globales. | Competencia de otras suites especializadas y cambios regulatorios. | Volatilidad de percepción sobre blockchain pública y barreras regulatorias. | Fricción de adopción multi-actor si la **calidad de datos** es heterogénea. |

## 2.3 Estrategias y tácticas frente a competidores

A continuación, la **Matriz FODA y C.A.M.E** específica para **FoodChain** (trazabilidad alimentaria con blockchain + QR/NFC, modelo SaaS B2B para productores; consulta gratuita para el consumidor).  
Interpretación de acciones:
- **Explotar/Mantener** = usar la fortaleza para capturar la oportunidad.
- **Afrontar/Mantener** = usar la fortaleza para defendernos de la amenaza.
- **Corregir/Explotar** = resolver la debilidad aprovechando la oportunidad.
- **Corregir/Afrontar** = mitigar la debilidad para resistir la amenaza.

| **MATRIZ FODA y C.A.M.E** | **Oportunidades: crecimiento de exigencias de trazabilidad en LATAM; interés del consumidor por origen/certificaciones; adopción de QR/NFC; digitalización agro y acuerdos con retailers locales.** | **Amenazas: resistencia al cambio y calidad de datos heterogénea; presión de suites globales; sensibilidad a costos; cambios regulatorios y percepción escéptica de “blockchain”.** |
|---|---|---|
| **Fortalezas: pasaporte digital por lote; registro inmutable en blockchain; validación de certificaciones; recall por lote en minutos; UX de escaneo QR; foco LATAM.** | **Explotar/Mantener**  \n- Lanzar **pilotos con productores** y supermercados (lotes reales) midiendo *time-to-trace* y *time-to-recall*; publicar métricas en casos de éxito.  \n- **Co-branding con QR** en góndola: historia del producto, mapa y certificados para elevar confianza del consumidor.  \n- Paquetes **SaaS por niveles** (micro, pyme, enterprise) y **onboarding guiado** para acelerar adopción.  \n- Integrar **sellos/certificaciones** (orgánico, DO, comercio justo) en el pasaporte digital para diferenciar marca. | **Afrontar/Mantener**  \n- **Gobernanza de datos** y acuerdos de rol/responsabilidad por actor; **SLA/SLO** de consulta (p.ej., p95 ≤ 3 s) y disponibilidad.  \n- **Validaciones en origen** (formularios con reglas, fotos georreferenciadas, firmas) y **auditoría** de cambios para mejorar calidad de datos.  \n- **Guías regulatorias** y plantillas de cumplimiento (etiquetado, privacidad, interoperabilidad) para reducir fricción legal.  \n- Mensajería clara: “blockchain como **prueba de integridad**”, no como cripto; foco en **seguridad alimentaria y confianza**. |
| **Debilidades: marca nueva; sin casos masivos; dependencia del onboarding multi-actor; recursos limitados frente a competidores globales.** | **Corregir/Explotar**  \n- Programa de **Design Partners** (3–5 productores ancla) a cambio de precio preferente y *roadmap* compartido.  \n- **Kits de despliegue**: plantillas de datos por cultivo, manuales de captura, video-demo para personal operativo.  \n- **Integraciones ligeras** (API/CSV) y conectores con ERP/WMS para reducir costo de entrada.  \n- Métricas de **ROI**: reducción de días de investigación a minutos; impacto en **ventas por confianza** (escaneos/visitas a página QR). | **Corregir/Afrontar**  \n- **Plan de adopción por etapas** (productor → procesador → retail) con hitos medibles y soporte remoto.  \n- **Pricing transparente** y TCO comparativo frente a suites globales; opción de **piloto** de 60–90 días.  \n- **Acuerdos con cámaras/consorcios** agro y universidades para credibilidad y acceso a red.  \n- **Backups y exportación** (evitar lock-in), y política de salida para confianza de clientes. |

## 2.4 Entrevistas

Para asegurar que **FoodChain** responda a necesidades reales, se realizarán **entrevistas breves y semiestructuradas** a dos actores clave:

- **Productores**: quienes registrarán la información de cada lote en la plataforma para garantizar trazabilidad y certificaciones.
- **Consumidores finales**: quienes escanearán el QR/NFC para conocer origen, ruta y certificaciones del producto.

Estas entrevistas permitirán:
- Identificar requerimientos funcionales y de experiencia de usuario.
- Conocer hábitos de uso de tecnología y nivel de confianza en la cadena alimentaria.
- Generar insumos para artefactos como **User Personas**, **User Journey Maps** y **Empathy Maps**.

Los hallazgos alimentarán la definición del **MVP** y de la arquitectura de FoodChain, asegurando que la solución sea clara, segura y útil para ambos segmentos.

### 2.4.1 Diseño de entrevistas

Para conocer el perfil básico de cada participante se incluirán las siguientes preguntas demográficas, diferenciando a los dos públicos clave de **FoodChain**:

#### Segmento objetivo #1: Productores

**Preguntas demográficas:**
- ¿Cuál es su nombre?
- ¿Cuál es su edad?
- ¿En qué región o localidad se encuentra su centro de producción?
- ¿A qué tipo de cultivo o actividad alimentaria se dedica?
- ¿Cuántos años de experiencia tiene en la producción y distribución de alimentos?
- ¿Cuántas personas conforman su equipo de trabajo?

#### Segmento objetivo #2: Consumidor final

**Preguntas demográficas:**
- ¿Cuál es tu nombre?
- ¿Cuál es tu edad?
- ¿Dónde vives?
- ¿A qué te dedicas?
- ¿Con qué frecuencia compras productos alimenticios frescos o procesados?
- ¿Sueles preferir productos con certificaciones como orgánico o comercio justo?



### 2.2.2. Registro de entrevistas


### 2.2.3. Análisis de entrevistas


## 2.3. Needfinding

En esta sección presentamos los artefactos clave que representan las necesidades, motivaciones y puntos de dolor de nuestros usuarios, tales como los perfiles de User Personas, la User Task Matrix, los User Journey Maps, el Empathy Mapping y el As-Is Scenario Mapping. Estos elementos son fundamentales para definir soluciones de diseño centradas en el usuario y asegurar que las decisiones de producto se basen en una comprensión profunda de los comportamientos y expectativas reales.

### 2.3.1. User Personas

En esta sección describimos la construcción de las fichas de User Persona para nuestros segmentos objetivo, enfocándonos en las características, comportamientos, motivaciones y retos clave de productores y consumidores dentro del ecosistema FoodChain. Consideramos aspectos demográficos y psicográficos, así como el nivel de competencia tecnológica, las necesidades de trazabilidad y transparencia, y las condiciones específicas de conectividad y uso.

###### Figura *
*User persona de nuestro segmento de Productores*

 <img src="/assets/img/UserPersonaCarlos.png" alt="UP1" width="400" height="850">

###### Figura *
*User persona de nuestro segmento de Usuarios Finales*

 <img src="/assets/img/UserPersonaMaria.png" alt="UP2" width="400" height="850">

### 2.3.2. User Task Matrix

En esta sección presentamos el User Task Matrix, una herramienta que sintetiza las acciones clave que nuestros User Personas (Productores y Usuarios finales) ejecutan para alcanzar sus objetivos con respecto a la trazabilidad alimentaria, independientemente de la existencia de una solución digital. 

Cada fila representa una tarea específica, mientras que las columnas reflejan la frecuencia e importancia con la que cada segmento ejecuta dichas tareas. Hemos mantenido el enfoque en tareas reales que reflejan el comportamiento orgánico de los usuarios, evitando confundir funcionalidades del software con tareas del usuario.

###### Tabla X

*User Task Matrix para los segmentos objetivos de FoodChain*

<table style="text-align: center; width: 100%;">
  <thead>
    <tr>
      <th rowspan="2">Tareas</th>
      <th colspan="2">Usuarios Finales (Consumidores)</th>
      <th colspan="2">Productores (Pequeños/Medianos)</th>
    </tr>
    <tr>
      <th>Frecuencia</th>
      <th>Importancia</th>
      <th>Frecuencia</th>
      <th>Importancia</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Escanear código QR para acceder a la historia del producto</td>
      <td>Often</td>
      <td>High</td>
      <td>Rarely</td>
      <td>Low</td>
    </tr>
    <tr>
      <td>Visualizar mapa con la ruta logística del producto</td>
      <td>Often</td>
      <td>High</td>
      <td>Rarely</td>
      <td>Low</td>
    </tr>
    <tr>
      <td>Ver certificados y documentación adjunta (orgánico, comercio justo, análisis)</td>
      <td>Often</td>
      <td>High</td>
      <td>Sometimes</td>
      <td>High</td>
    </tr>
    <tr>
      <td>Consultar perfil del productor (origen, prácticas, fechas clave)</td>
      <td>Sometimes</td>
      <td>Medium</td>
      <td>Rarely</td>
      <td>Medium</td>
    </tr>
    <tr>
      <td>Registrar eventos del lote</td>
      <td>Never</td>
      <td>Low</td>
      <td>Always</td>
      <td>High</td>
    </tr>
    <tr>
      <td>Generar/emitir etiquetas QR o identificadores por lote</td>
      <td>Never</td>
      <td>Low</td>
      <td>Often</td>
      <td>High</td>
    </tr>
    <tr>
      <td>Integrar datos externos (certificados, análisis de laboratorio, sensores IoT)</td>
      <td>Never</td>
      <td>Low</td>
      <td>Sometimes</td>
      <td>High</td>
    </tr>
    <tr>
      <td>Acceder a los registros del propio lote para control/gestión</td>
      <td>Never</td>
      <td>Low</td>
      <td>Often</td>
      <td>High</td>
    </tr>
    <tr>
      <td>Interoperar / sincronizar datos con sistemas existentes (ERP, certificadoras)</td>
      <td>Never</td>
      <td>Low</td>
      <td>Sometimes</td>
      <td>Medium</td>
    </tr>
    <tr>
      <td>Tomar decisión de compra basada en la información de trazabilidad</td>
      <td>Often</td>
      <td>High</td>
      <td>Never</td>
      <td>Low</td>
    </tr>
  </tbody>
</table>


***Análisis comparativo de tareas: Usuarios finales (consumidores) vs. Productores**

**Tareas de mayor frecuencia e importancia en ambos perfiles**

Tanto los **usuarios finales** como los **productores** coinciden en ciertas tareas clave que son realizadas con alta frecuencia y valoradas como altamente importantes en el contexto de la trazabilidad alimentaria:

- **Acceder a la historia del producto (escaneo de QR).**  
  - *Consumidores:* acción frecuente y de alto impacto en la decisión de compra.  
  - *Productores:* menos frecuente, pero clave porque valida el registro que ellos generan.

- **Verificación de certificaciones y documentación adjunta.**  
  - Ambos perfiles consideran esta tarea de alta importancia: los consumidores para decidir y los productores para aportar evidencia de calidad.

- **Registrar y consultar eventos del lote.**  
  - *Productores:* prioritaria (registro continuo y base de la trazabilidad).  
  - *Consumidores:* dependen de que estos registros existan para confiar en el producto (importancia alta aunque no registren).



**Principales diferencias**

- **Dirección de la interacción**  
  - *Consumidores:* realizan acciones de verificación y decisión (escaneo, mapa, lectura de certificados).  
  - *Productores:* ejecutan acciones operativas y administrativas (registrar eventos, generar QR, subir certificados).

- **Frecuencia operativa**  
  - *Productores:* registros y gestión de lotes de forma recurrente (Always/Often).  
  - *Consumidores:* acciones puntuales en el punto de compra o cuando necesitan verificar (Often/Sometimes).

- **Requerimientos técnicos y de usabilidad**  
  - *Productores:* necesitan flujos de **registro rápido**, soporte **offline** y sincronización con sistemas externos.  
  - *Consumidores:* necesitan respuestas **instantáneas**, vistas resumidas y señales claras de confianza (badges, certificados visibles, mapa).

- **Propósito y motivadores**  
  - *Productores:* documentar y probar origen para obtener mejor precio y acceso al mercado.  
  - *Consumidores:* verificar y decidir para garantizar seguridad, calidad y, en ocasiones, pagar un premium por trazabilidad.



**Coincidencias destacadas**

- Ambos perfiles comparten la **prioridad por la confianza**: registros verificables son valorados por razones complementarias.
- La **verificación de certificaciones** aumenta la confianza del consumidor y el valor comercial del productor.
- Las **notificaciones críticas** son útiles para ambos: consumidores (recalls, información) y productores (gestión operativa).
- La **interoperabilidad** con certificadoras y ERPs beneficia principalmente a productores, pero mejora indirectamente la credibilidad percibida por consumidores.




### 2.3.3. User Journey Mapping

En esta sección presentamos los User Journey Maps As-Is para cada uno de nuestros User Personas, ilustrando el recorrido completo que realizan actualmente para verificar la trazabilidad y autenticidad de los productos alimentarios, desde la identificación de la necesidad hasta la toma de decisión de compra informada. Iniciaremos con una descripción general del viaje end-to-end, resaltando los momentos clave de descubrimiento, interacción y evaluación, así como los principales puntos de dolor y oportunidades para optimizar la experiencia. Luego, mostraremos los diagramas elaborados en la herramienta correspondiente, vinculando cada mapa con el User Persona respectivo para evidenciar cómo sus metas, frustraciones y comportamientos influyen en cada fase del proceso.

###### Figura *
*User Journey map de nuestro segmento de Productores*

 <img src="/assets/img/JourneyMapCarlos.png" alt="USM1" width="400" height="850">

###### Figura *
*User Journey map de nuestro segmento de Usuarios Finales*

 <img src="/assets/img/JourneyMapMaria.png" alt="USM2" width="400" height="850">

### 2.3.4. Empathy Mapping

En esta sección presentamos los Empathy Maps desarrollados para nuestros dos User Personas: el Productor (caficultor) y el Usuario Final (consumidor consciente). Cada mapa organiza la información en torno a seis dimensiones clave: qué ve, dice, hace, escucha, piensa y siente el usuario.

A partir de este análisis, identificamos sus principales frustraciones y obstáculos (Pains), así como sus motivaciones y expectativas (Gains). Esto nos ayuda a comprender mejor su experiencia frente a la trazabilidad alimentaria y a diseñar soluciones más acordes a sus necesidades reales.

###### Figura *
*Empathy map de nuestro segmento de Productores*

 <img src="/assets/img/EmpathyMapCarlos.png" alt="EP1" width="400" height="850">

###### Figura *
*Empathy map de nuestro segmento de Usuarios Finales*

 <img src="/assets/img/EmpathyMapMaria.png" alt="EP2" width="400" height="850">


### 2.3.5. As-is Scenario Mapping

El As‑Is Scenario Mapping es una herramienta clave para analizar cómo interactúan actualmente nuestros usuarios con procesos relacionados a la trazabilidad alimentaria. En esta sección se descompone paso a paso la experiencia real tanto del Productor como del Usuario Final, desde sus acciones cotidianas hasta sus pensamientos y emociones durante el proceso.

Cada escenario se estructura en torno a cuatro dimensiones principales:

- Phases (Fases del proceso)

- Doing (Qué hace el usuario)

- Thinking (Qué piensa en cada paso)

- Feeling (Qué emociones experimenta)

Este enfoque nos permite detectar con claridad puntos de dolor, frustraciones, necesidades no resueltas y áreas de oportunidad, incluso antes de plantear soluciones digitales.

###### Figura *
*As-Is Scenario Mapping de nuestro segmento de Productores*

 <img src="/assets/img/As-IsScenarioMapCarlos.png" alt="AI2" width="400" height="850">

###### Figura *
*As-Is Scenario Mapping de nuestro segmento de Usuarios Finales*

 <img src="/assets/img/As-IsScenarioMapMaria.png" alt="AI2" width="400" height="850">

## 2.4. Ubiquitous Language

