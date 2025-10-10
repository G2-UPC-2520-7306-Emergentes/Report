## **CAPÍTULO VI: SOLUTION UX DESIGN**

En este capítulo se define la propuesta de diseño de la experiencia de usuario (UX) e interfaz de usuario (UI) para el ecosistema de FoodChain. El objetivo es traducir nuestra misión de **restaurar la confianza en la cadena alimentaria** en una experiencia digital coherente, intuitiva y transparente para cada uno de nuestros segmentos objetivo.

Para ello, tomaremos como base los User Stories identificados y las decisiones de arquitectura, asegurando que cada interacción, desde el registro de un lote por parte de un productor hasta el escaneo de un QR por parte de un consumidor, refuerce nuestros valores de **integridad, transparencia y empoderamiento**. La propuesta de diseño abarcará desde las guías de estilo que unifican nuestra identidad visual, hasta la arquitectura de información y los prototipos que materializan la interacción con nuestras aplicaciones y el Landing Page.

### **6.1 Style Guidelines**

En esta sección se establecen las bases visuales y de comunicación que definirán la identidad de FoodChain. El objetivo es crear un repositorio de diseño centralizado y coherente que garantice una experiencia de usuario unificada y profesional en todos nuestros productos digitales. Estas guías aseguran que cada elemento, desde un botón hasta el tono de un mensaje, refleje nuestros valores de transparencia, confianza y seguridad alimentaria.


#### 6.1.1 General Style Guidelines

En esta sección se definen los pilares de la identidad visual y verbal de FoodChain. El propósito es establecer un lenguaje de diseño consistente que comunique nuestros valores fundamentales **transparencia, integridad y confianza** en cada punto de contacto con el usuario. Estas guías servirán como la única fuente de verdad para todo el equipo, garantizando que la experiencia en nuestras plataformas sea coherente, profesional y memorable. Como base para la construcción de nuestros componentes, tomaremos como referencia el Design System **Material Design**, adaptándolo a las necesidades de nuestra marca.

**Branding (Marca)**

![logo.jpeg](../assets/images/logo.jpeg)

El logotipo de FoodChain es la representación visual de nuestra misión, encarnada en un personaje amigable y heroico: un aguacate con capa que protege y garantiza la transparencia de los alimentos. El diseño comunica nuestros valores de la siguiente manera:
* **El Personaje (Aguacate Héroe):** El aguacate representa lo natural, saludable y fresco. Su expresión sonriente y su capa lo convierten en un símbolo de **protección y empoderamiento** para el consumidor, un guardián de la confianza en la cadena alimentaria.
* **La Etiqueta con Código QR:** Es la herramienta del héroe. Simboliza el poder de la información y la tecnología accesible que ofrecemos para desvelar la historia de cada producto con un simple escaneo.
* **La Cadena de Fondo:** Representa de forma sutil y segura la tecnología **blockchain** y los eslabones de la cadena de suministro que nuestra plataforma une y protege de manera inmutable.

El estilo general del logo es accesible, positivo y moderno, lo que nos permite abordar un tema tan complejo como la trazabilidad de una manera que genera confianza y no intimidación.

#### **Typography**

La selección tipográfica se ha definido para garantizar una excelente legibilidad, jerarquía visual y una estética moderna y limpia, alineada con la confianza y accesibilidad que promueve FoodChain.

* **Familia para Títulos y Encabezados: `Inter`**
  Se ha elegido Inter por su gran legibilidad en interfaces de usuario (UI) y su claridad en diferentes tamaños y pesos. Es una fuente moderna y neutra que aporta seriedad y profesionalismo a los títulos.

* **Familia para Cuerpo de Texto y UI: `Roboto`**
  Se ha optado por Roboto por su familiaridad y comodidad de lectura en párrafos largos. Sus formas abiertas y ritmo natural la hacen ideal para presentar información detallada de manera clara y sin fatigar al lector.

A continuación, se detalla la escala tipográfica que se utilizará en toda la plataforma, según las especificaciones definidas:

![tipografia.jpeg](../assets/images/tipografia.jpeg)

#### **Colors**

La paleta de colores se extrae directamente de nuestro logotipo, asegurando una sinergia total entre la marca y la interfaz de usuario. Los colores han sido seleccionados estratégicamente para evocar naturaleza, frescura, energía y confianza, creando una experiencia visual coherente, accesible y atractiva que refuerza la identidad de FoodChain.

**Paleta de Colores Primarios**

Estos son los colores fundamentales que definen nuestra identidad visual y deben ser los más prominentes en el diseño.

* **Primario (`#1A5952`) - Confianza y Estructura:**
  Extraído del fondo del logo, este verde oscuro y profundo comunica seriedad, seguridad y un fuerte vínculo con la naturaleza. Es el pilar de nuestra paleta.
    * **Uso:** Ideal para componentes estructurales como la barra de navegación, footers, fondos de secciones principales y como color de texto principal sobre fondos claros.

![principal.jpeg](../assets/images/principal.jpeg)

* **Secundario - Acción y Energía (`#8BC53F`)**
  Es el color vibrante y amigable de nuestro personaje. Representa frescura, salud y vitalidad. Su función es guiar al usuario y destacar las acciones más importantes.
    * **Uso:** Exclusivamente para los llamados a la acción (CTAs) más importantes, botones primarios, íconos interactivos y elementos que requieran la atención inmediata del usuario.

![secundario1.jpeg](../assets/images/secundario1.jpeg)

**Paleta de Colores Secundarios y de Acento**

Estos colores complementan a los primarios y se utilizan para resaltar información y añadir dinamismo a la interfaz.

* **Acento - Resaltado y Vitalidad (`#A8D164`)**
  El color de la capa de nuestro héroe. Es un verde lima enérgico que sirve para dar énfasis sin competir con el color secundario.
    * **Uso:** Perfecto para resaltar información secundaria, insignias de certificación, etiquetas, barras de progreso y para los estados de `hover` en elementos interactivos.

![secundario2.jpeg](../assets/images/secundario2.jpeg)

* **Detalle Sutil - (`#594F31`)**
  Un tono tierra extraído de la semilla del aguacate. Aporta un toque orgánico y se usa para detalles que no necesitan un alto contraste.
    * **Uso:** Ideal para íconos secundarios, bordes sutiles o texto de menor importancia.

![secundario4.jpeg](../assets/images/secundario4.jpeg)

**Paleta de Colores Neutrales**

Los neutrales proporcionan el lienzo sobre el cual nuestros colores de marca pueden brillar. Son esenciales para la claridad, el espaciado y la legibilidad.

* **Neutro Principal (`#231F20`) - Texto y Contornos:**
  Extraído de los contornos del logo y el QR. Este tono casi negro es el color principal para todo el texto, garantizando la máxima legibilidad y cumpliendo con los estándares de accesibilidad.
    * **Uso:** Cuerpo de texto, títulos, etiquetas y bordes de componentes.

![secundario3.jpeg](../assets/images/secundario3.jpeg)

* **Blanco - Fondo y Espacio (`#FFFFFF`)**
  El blanco puro se utiliza para dar "aire" y limpieza al diseño.
    * **Uso:** Fondos principales de página y fondos de tarjetas (cards) para que el contenido sea el protagonista.

![secundario5.jpeg](../assets/images/secundario5.jpeg)

### Spacing**

El sistema de espaciado de **FoodChain** se fundamenta en una cuadrícula modular de **10 px**, utilizada como guía base para la ubicación, proporción y alineación de todos los elementos visuales.  
Esta estructura asegura uniformidad, equilibrio y legibilidad en las interfaces, manteniendo coherencia entre versiones web y móviles.

#### **Lineamientos de espaciado**
- **Unidad base:** cuadrícula de 10 px (con subdivisiones de 5 px para microajustes).
- **Márgenes internos (padding):** entre 10 px y 30 px según el tipo de componente.
- **Márgenes externos (margin):** entre 20 px y 60 px para bloques principales.
- **Espaciado vertical entre campos y botones:** 20 – 24 px.
- **Separación entre secciones o grupos de contenido:** 50 – 70 px.
- **Alineación:** se emplea *Auto Layout* para mantener distancias proporcionales y consistentes.
- **Sistema de referencia:** el grid de 10 px se aplica en todas las pantallas (1280 px de ancho base) para garantizar una estructura visual clara y escalable.

#### **Justificación**
El uso de una cuadrícula fija permite mantener un ritmo visual uniforme, facilita la lectura de formularios y componentes, y asegura una estética profesional en la interfaz de usuario.

![spacing.jpeg](../assets/images/spacing.jpeg)

> **Figura.** Sistema de espaciado de 10 px aplicado a la pantalla Login del proyecto FoodChain.  
> *Nota.* Captura elaborada en Figma mostrando la cuadrícula 10 px y las distancias de margen entre los componentes principales (inputs, botón y texto) de la interfaz.

![spacing2.jpeg](../assets/images/spacing2.jpeg)

#### **Tono de Comunicación y Lenguaje**

El tono de comunicación de FoodChain debe ser un reflejo directo de nuestra marca: **el guardián confiable y amigable de tus alimentos**. La forma en que nos comunicamos es tan importante como la tecnología que ofrecemos, ya que es el principal vehículo para construir confianza con nuestros usuarios. Por ello, nuestra comunicación será siempre **clara, educativa y tranquilizadora**, adaptando el lenguaje al contexto y al segmento objetivo para maximizar la comprensión y resonancia.

**Personalidad de la Marca**

Nuestra voz se define por tres arquetipos principales que guían todo nuestro contenido:

1.  **Somos el Guía Experto, no el Elitista:** Explicamos conceptos complejos como "blockchain" con autoridad, pero siempre de manera accesible y sencilla. Traducimos la tecnología en beneficios tangibles para el usuario, como "un historial verificado e inalterable". Nuestro objetivo es educar y empoderar, no intimidar con jerga técnica.
2.  **Somos el Guardián Confiable, no el Alarmista:** Nuestra misión es proteger y asegurar. Informamos sobre los riesgos de la industria para dar contexto a nuestra solución, pero nuestro mensaje principal es de empoderamiento, seguridad y tranquilidad. Generamos confianza a través de la transparencia, no del miedo.
3.  **Somos Innovadores con Propósito, no Tecnólogos Abstractos:** Cada característica de nuestra plataforma se presenta en función del problema real que resuelve. Comunicamos el "porqué" de nuestra tecnología, mostrando cómo cada innovación contribuye a una cadena de suministro más justa y segura para todos.

**Adaptación por Segmento**

Reconocemos que nuestros usuarios tienen diferentes necesidades y contextos, por lo que adaptaremos nuestro tono para comunicarnos de la manera más efectiva con cada uno.

* **Hacia el Consumidor (B2C):**
    * **Tono:** Usaremos un tono directo, cercano, sencillo y centrado en el beneficio personal. El lenguaje será visual y evocador, conectando con las emociones del usuario en torno a la salud, la familia y la confianza.
    * **Ejemplo de Copy:** *“¿Quieres saber la historia completa de tu aguacate? Descúbrela desde la huerta hasta tu mesa. Escanea el QR y conoce al héroe que garantiza tu tranquilidad.”*

* **Hacia el Productor y la Empresa (B2B):**
    * **Tono:** El tono será profesional, directo y orientado a resultados. El lenguaje se centrará en conceptos de negocio como eficiencia, mitigación de riesgos, valor de marca y retorno de inversión (ROI).
    * **Ejemplo de Copy:** *“Proteja su marca contra el fraude y optimice la gestión de recalls con nuestra plataforma de trazabilidad inmutable. Convierta la transparencia en su mayor activo competitivo y fortalezca la lealtad de sus clientes.”*

#### 6.1.2 Web, Mobile & Devices Style Guidelines

Este punto muestra cómo se aplican, en pantallas reales, las reglas del 6.1.1.  
Ingredientes heredados: color primario **#8BC53F**, tipografía **Inter**, unidad de espaciado **8 px**.  
El objetivo es **explicar** cada componente y **mostrarlo** con su captura de Figma.

### Catálogo de Componentes (Web)

#### Botones y CTAs

![call2.jpeg](../assets/images/call2.jpeg)

**Uso:** el primario enfatiza la acción principal del flujo; el secundario ofrece una alternativa segura.  
**Estilo primario:** fondo **#8BC53F**, texto Inter Medium 16 px, radio 12 px, padding vertical 12–16 px, sombra sutil; estados hover (↑luminosidad), focus (outline visible), disabled (40% opacidad).  
**Estilo secundario:** fondo verde oscuro **#264533**, texto blanco, mismas proporciones del primario.  
**Accesibilidad:** contraste AA en todos los estados; área mínima clicable 44×44 px; feedback inmediato.

#### Dashboard — KPIs y Gráficos

![graficos.jpeg](../assets/images/graficos.jpeg)

**Propósito:** dar una visión ejecutiva de la operación.  
**Estructura:** tarjetas métricas alineadas a una rejilla de **12 columnas**; módulos de “Activity Overview”, “Lots by Status” y “Recent Events”.  
**Jerarquía:** títulos Inter Bold 24–28 px; cifras principales 28–32 px; descripciones 14–16 px.  
**Color:** neutros claros **#FFFFFF / #E5E8EB** para fondos; acentos en **#8BC53F** para variaciones positivas y rojo suave para negativas.  
**Accesibilidad:** etiquetas textuales en gráficos (no solo color); foco visible en chips de filtro.


#### Detalle del Lote — Trazabilidad

![lotecerrado.jpeg](../assets/images/lotecerrado.jpeg)

**Propósito:** mostrar estado, metadatos y eventos del lote.  
**Estructura:** H1 con nombre del lote, subtítulo con ID/fechas, chip de estado, miniatura del producto y tabla de eventos (Evento, Fecha, Actor, Descripción, Hash).  
**Patrones:** paddings en múltiplos de **8 px**; bordes finos **#E5E8EB**; botón contextual deshabilitado cuando el lote está cerrado.  
**Accesibilidad:** tabla navegable por teclado; encabezados semánticos; contraste AA.

#### Mis Lotes — Tabla de Gestión

![mislotes.jpeg](../assets/images/mislotes.jpeg)

**Propósito:** listar y operar sobre los lotes.  
**Estructura:** columnas por prioridad (Lote, Estado, Fecha de creación, Última actividad, Acciones); paginación al pie.  
**Patrones:** filas con altura suficiente para escaneo; badges de estado con codificación cromática; acciones “Ver detalle | Generar QR | Cerrar lote” alineadas a la derecha.  
**Tipografía:** Inter 14–16 px en celdas; encabezados 12–14 px en semibold.  
**Accesibilidad:** orden de tabulación lógico; roles ARIA en paginación; foco visible en enlaces.

#### Crear Nuevo Lote — Formulario

![nuevolote.jpeg](../assets/images/nuevolote.jpeg)

**Propósito:** alta guiada de lotes con validación inmediata.  
**Estructura:** columna única; campos “Lot Name”, “Farm Name”, “Variety”, “Harvest Date”, “Notes” y área de carga de imagen (drag & drop).  
**Patrones:** labels sobre el campo; placeholders claros; espaciado vertical de **16–24 px**; mensajes de error bajo el campo en rojo suave; CTA “Create Lot” en **#8BC53F** a ancho completo.  
**Accesibilidad:** labels asociados a inputs; ayuda textual junto a color; navegación completa por teclado.

#### Navegación Lateral

![navegacionlateral.jpeg](../assets/images/navegacionlateral.jpeg)

**Propósito:** orientar al usuario entre módulos del sistema.  
**Patrones:** iconos simples, texto Inter 14–16 px, item activo con fondo claro **#E5E8EB** y marcador visual; espaciado interno múltiplo de **8 px**.  
**Estados:** hover con leve cambio de fondo, focus con outline visible, `aria-current="page"` en el activo.  
**Accesibilidad:** objetivos táctiles amplios y orden de foco predecible.

### Reglas transversales aplicadas en todas las vistas (Web)

**Grid:** rejilla de **12 columnas**; unidad de medida y separación basada en **8 px**.  
**Tipografía:** **Inter** en pesos Regular/Medium/Bold; jerarquía seca y consistente.  
**Color:** primario **#8BC53F**; secundarios y neutros **#264533 / #FFFFFF / #E5E8EB**; semántica constante en estados.  
**Microinteracciones:** transiciones de 0.2–0.3 s para hover/focus; feedback instantáneo en envíos y errores.  
**Accesibilidad:** contraste AA, foco visible, áreas mínimas 44×44 px, etiquetas ARIA en controles y tablas.


### Catálogo de Componentes (Mobile)

El diseño de la aplicación móvil de FoodChain se centra en la simplicidad, la rapidez y una experiencia visual intuitiva. El objetivo es que cualquier consumidor pueda verificar la historia de un producto en segundos. Los componentes heredan las guías de estilo generales (colores, tipografía) pero se adaptan a los patrones de interacción nativos de los dispositivos móviles para garantizar una usabilidad óptima.

*(Nota: Las descripciones se basan en los mockups proporcionados para la aplicación móvil, incluyendo las vistas de Escaneo, Trazabilidad y Detalle).*



#### 1. Navegación Inferior (Tab Bar)

**Propósito:** Proporcionar acceso constante y ergonómico a las secciones principales de la aplicación, siguiendo un patrón de diseño nativo y familiar para el usuario móvil.
**Estructura:** Se implementa una barra de pestañas fija en la parte inferior de la pantalla, que contiene los íconos de las secciones principales: "History", "Map", "Companies" y "Help".
**Patrones:**
* Los íconos son de línea, simples y reconocibles para una fácil identificación.
* El ícono de la sección activa se destaca utilizando un relleno sólido, proporcionando un feedback visual claro de la ubicación del usuario.
* El área táctil de cada ítem cumple con las guías de accesibilidad (mínimo 44x44 px) para asegurar una interacción sin errores.

![mobile.jpeg](../assets/images/mobile.jpeg)

#### 2. Botón de Acción Principal (Scan Button)

**Propósito:** Ser el punto de entrada principal y más evidente de la aplicación. Su diseño está pensado para invitar al usuario a la acción fundamental: escanear un producto.
**Estilo:**
* Se materializa como un botón prominente en la pantalla de escaneo, con un texto claro y directo: "Scan QR Code".
* Utiliza un fondo sólido con un degradado sutil de los colores de la marca, lo que le da profundidad y atractivo visual.
* Incluye un ícono de código QR grande y claro, reforzando su propósito. Los bordes son completamente redondeados, dándole una apariencia amigable y moderna.

![mobile1.jpeg](../assets/images/mobile1.jpeg)


#### 3. Línea de Tiempo de Trazabilidad (Timeline)

**Propósito:** Mostrar la historia de un producto de una manera visual, vertical y fácil de digerir en una pantalla pequeña, reemplazando las complejas tablas de datos de la versión web.
**Estructura:**
* Una línea vertical conecta cada evento de la cadena de suministro, creando un flujo narrativo claro.
* Cada evento (ej. "Cosecha completada", "Empaquetado") es un punto en la línea, representado por un ícono temático dentro de un círculo.
* Junto a cada punto, se muestra el nombre del evento, el actor responsable y la fecha, utilizando la jerarquía tipográfica definida (`Inter` para títulos, `Roboto` para detalles) para una legibilidad óptima.

![mobile2.jpeg](../assets/images/mobile2.jpeg)


#### 4. Tarjetas de Información (Info Cards)

**Propósito:** Presentar información detallada de manera agrupada y visualmente ordenada, como en la pantalla de "Empresas Participantes".
**Estilo:**
* Utilizan un fondo blanco con bordes redondeados y una sombra sutil para darles elevación sobre el fondo de la pantalla.
* El contenido se estructura con un espaciado interno generoso. Se usan títulos claros (`Inter`) y texto descriptivo (`Roboto`).
* Componentes como las insignias de "Certificaciones" están diseñados para ser visualmente atractivos y fáciles de identificar.

![mobile3.jpeg](../assets/images/mobile3.jpeg)

### **6.2 Information Architecture**

La Arquitectura de la Información (AI) define la estructura subyacente de nuestro ecosistema digital, asegurando que el contenido esté organizado de manera lógica, sea fácil de encontrar y comprensible para nuestros distintos segmentos de usuario. Para FoodChain, una AI sólida es fundamental para traducir la complejidad de la trazabilidad en una experiencia de usuario clara y transparente, tanto para los productores que gestionan datos como para los consumidores que los consultan.


#### 6.2.1 Organization Systems (Sistemas de Organización)

Los sistemas de organización determinan cómo se agrupa y estructura la información dentro de nuestras plataformas. Hemos adoptado esquemas específicos para cada aplicación, alineados con los objetivos de sus usuarios.

* **Aplicación Web (Productores):** Se emplea un **esquema de organización jerárquico y por temas**. La estructura está diseñada para la gestión de datos, permitiendo al usuario navegar desde un nivel general (el Dashboard) hacia niveles cada vez más específicos (la lista de "Mis Lotes" y, finalmente, el "Detalle del Lote"). Las secciones del menú lateral ("Dashboard", "Mis Lotes", "Reportes") actúan como los temas principales, agrupando la información de manera lógica y predecible para un entorno de trabajo profesional.

* **Aplicación Móvil (Consumidores):** El sistema principal es **secuencial y cronológico**. La pantalla de trazabilidad, que es el corazón de la experiencia del consumidor, presenta la historia del producto como una secuencia de eventos ordenados por fecha, desde el origen hasta el punto de venta. Este enfoque narrativo facilita que el consumidor siga la "historia" del producto de una manera intuitiva y visualmente atractiva.


#### 6.2.2 Labeling Systems (Sistemas de Etiquetado)

El sistema de etiquetado se refiere a la selección de palabras y frases para representar la información. Las etiquetas de FoodChain han sido elegidas para ser claras, consistentes y para hablar el idioma de nuestros usuarios, evitando la jerga técnica innecesaria.

A continuación, se presenta una tabla con las etiquetas más importantes y la justificación de su elección:

| Etiqueta | Plataforma | Justificación |
| :--- | :--- | :--- |
| **Mis Lotes** | Web | Se eligió esta etiqueta porque es clara, directa y genera un sentido de pertenencia para el productor, indicando que son *sus* registros y su área de gestión principal. |
| **Escanear QR** | Mobile | Es una llamada a la acción directa y universalmente entendida que no deja lugar a dudas sobre la función principal de la aplicación para el consumidor. |
| **Historial de Eventos** | Web | Describe de forma precisa el contenido de la tabla de trazabilidad, utilizando un lenguaje profesional adecuado para el entorno de gestión de datos del productor. |
| **Cerrar Lote** | Web | Es una etiqueta de acción clara que indica el final del ciclo de vida de la trazabilidad de un producto, una acción de negocio importante para el productor. |
| **Generar QR** | Web | Indica de manera inequívoca la función de crear el código QR que se asociará físicamente al producto, un paso crucial en el proceso. |


#### 6.2.3 Searching Systems (Sistemas de Búsqueda)

Los sistemas de búsqueda permiten a los usuarios encontrar información específica de manera rápida y eficiente. Para FoodChain, esto es crucial en la aplicación web para la gestión de un gran volumen de datos.

* **Aplicación Web:** En la pantalla de "Mis Lotes", se implementará un sistema de búsqueda robusto que incluirá:
    * Una **barra de búsqueda** prominente en la parte superior de la tabla, que permitirá al productor encontrar un lote específico por su nombre o ID.
    * Un sistema de **filtros avanzados** para visualizar lotes según su "Estado" (Activo, Cerrado, En Revisión) o por un rango de "Fecha de Creación", permitiendo una gestión más eficiente y segmentada de sus registros.

* **Aplicación Móvil:** Dado que el objetivo es la consulta simple, la función de búsqueda se limita a un **listado cronológico en el "Historial"**, donde el usuario puede hacer scroll para encontrar escaneos previos.


#### 6.2.4 SEO Tags and Meta Tags (Etiquetas SEO y Metaetiquetas)

Estas etiquetas son fundamentales para la visibilidad de nuestro **Landing Page** en los motores de búsqueda, permitiendo que potenciales clientes (productores y empresas) nos encuentren.

| Etiqueta | Valor |
| :--- | :--- |
| **Title (Título)** | `FoodChain: Trazabilidad Blockchain para la Industria Alimentaria` |
| **Meta Description (Descripción)** | `Restaura la confianza en tus productos con FoodChain. Nuestra plataforma blockchain ofrece trazabilidad total desde el campo hasta la mesa. ¡Asegura tu cadena de suministro y protege tu marca!` |
| **Keywords (Palabras Clave)** | `trazabilidad alimentaria, blockchain en alimentos, seguridad alimentaria, software para agronegocios, foodchain, qr para alimentos, food traceability` |


#### 6.2.5 Navigation Systems (Sistemas de Navegación)

Los sistemas de navegación son los componentes de la interfaz que guían al usuario a través de las diferentes pantallas. Hemos elegido patrones de navegación estándar y reconocibles para cada plataforma.

* **Aplicación Web:** El sistema de navegación principal es una **Barra Lateral persistente (Sidebar)**. Esta elección es ideal para una aplicación de gestión, ya que mantiene las secciones principales ("Dashboard", "Mis Lotes", etc.) siempre visibles y a un solo clic de distancia, permitiendo al productor moverse de manera eficiente entre los diferentes módulos sin perder el contexto.

* **Aplicación Móvil:** Se utiliza una **Barra de Pestañas Inferior (Tab Bar)** como sistema de navegación principal. Este patrón es el estándar de oro en aplicaciones móviles por ser ergonómico, fácil de alcanzar con el pulgar y familiar para la gran mayoría de los usuarios. Permite al consumidor cambiar rápidamente entre las funciones clave ("Historial", "Escanear", "Empresas") de manera intuitiva.

### **6.3 Landing Page UI Design**
La landing page constituye el primer punto de interacción con los usuarios, por lo que su diseño visual y funcional es fundamental para generar una experiencia memorable. En esta sección se detallan las decisiones adoptadas para el wireframe y mock-up de la página principal, priorizando una estructura intuitiva, visualmente atractiva y optimizada para la conversión. El diseño está orientado a captar la atención del usuario desde el primer instante, comunicar de forma clara y concisa los beneficios clave del producto y guiarlo de manera efectiva hacia la acción principal.

#### 6.3.1 Landing Page Wireframe

![wireframe-landing page.jpeg](../assets/wireframes/Landing%20page.png)

#### 6.3.2 Landing Page Mock-up

![wireframe-landing page.jpeg](../assets/mockups/Landing%20page-mck.png)

### **6.4 Applications UX/UI Design**
Esta sección detalla el diseño de experiencia (UX) e interfaz de usuario (UI) de la aplicación web y móvil de FoodChain. Mediante el uso de wireframes, wireflows, mock-ups y diagramas de flujo, se abordan los elementos visuales y funcionales necesarios para garantizar una experiencia de usuario fluida, accesible y altamente intuitiva. Cada pantalla ha sido cuidadosamente diseñada para responder a las necesidades específicas de los usuarios, optimizando flujos de tareas esenciales como crear actores, gestionar lotes, registrar pasos, etc. El diseño prioriza la simplicidad, la claridad visual y la accesibilidad, asegurando que los usuarios puedan navegar y completar sus objetivos con el menor esfuerzo posible.

#### 6.4.1 Applications Wireframes

- Web Application Wireframes

Sign In
<br>
![wireframe-landing page.jpeg](../assets/wireframes/US26%20-%20Login.png)

Sign Up
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Register.png)

Home
<br>
![wireframe-landing page.jpeg](../assets/wireframes/US03.png)

Register role
<br>
![wireframe-landing page.jpeg](../assets/wireframes/US25%20–%20Registrar%20usuario%20·%20Paso%201_%20Datos%20básicos.png)

Register Step
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Registrar%20Paso%20en%20Lote%20(Éxito).png)

Lot Detail
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Detalle%20del%20lote.png)

- Mobile Application Wireframes

Home
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Home.png)

Timeline
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Timeline.png)

Featuring Companies
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Empresas%20participantes.png)

Company detail
<br>
![wireframe-landing page.jpeg](../assets/wireframes/US24.png)

Lot Route
<br>
![wireframe-landing page.jpeg](../assets/wireframes/US22.png)

Blockchain Verification
<br>
![wireframe-landing page.jpeg](../assets/wireframes/US21.png)

#### 6.4.2 Applications Wireflow Diagrams
Los wireflows fusionan wireframes con diagramas de flujo para representar la forma en que los usuarios navegan e interactúan con la aplicación a través de múltiples pantallas. Esto facilita la comprensión del trayecto integral del usuario y verifica que los flujos diseñados alineen con los objetivos establecidos para procesos como el acceso al sistema, la administración de grupos, la consulta de gastos y la ejecución de pagos.

- **User Goal: Crear cuenta de usuario**
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Wireflows%20-%20Crear%20cuenta.png)
<br>
El usuario accede a la aplicación y, al no tener cuenta, hace clic en "Registrarse". Esto lo redirige a la vista "Sign Up" donde encuentra un formulario para completar sus datos. Una vez llenados los campos requeridos, presiona el botón "Registrarse" y, si el registro es exitoso, el sistema muestra una vista de confirmación o redirige al dashboard principal de la aplicación.


- **User Goal: Restablecer contraseña**
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Wireflows%20-%20Restablecer%20contraseña.png)
<br>
El usuario ha olvidado su contraseña y hace clic en "¿Olvidó su contraseña?" en la pantalla de inicio de sesión. Se le redirige a una vista donde ingresa su correo electrónico para recibir un enlace de restablecimiento. Al hacer clic en el enlace del correo, se le dirige a una vista para ingresar una nueva contraseña. Después de establecer la nueva contraseña, se muestra una confirmación y se le redirige al inicio de sesión.

- **User Goal: Crear lote**
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Wireflows%20%20-%20Crear%20lote.png)
<br>
El productor, después de iniciar sesión, accede al dashboard y hace clic en "Crear Lote". Se le presenta un formulario con campos obligatorios (nombre, finca, fecha de cosecha, variedad). Al completar el formulario y hacer clic en "Crear Lote", el sistema valida los datos. Si son correctos, se crea el lote y se redirige al productor a la página de detalle del lote con un mensaje de confirmación.

- **User Goal: Cerrar lote**
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Wireflows%20-%20Cerrar%20lote.png)
<br>
El productor selecciona un lote activo y hace clic en "Cerrar Lote". El sistema verifica que el lote esté en estado activo y muestra una confirmación. Al confirmar, el lote cambia a estado "Cerrado" y se registra un evento en la blockchain. Si el lote ya está cerrado, se muestra un error.

- **User Goal: Generar QR para lote**
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Wireflows%20-%20Generar%20QR.png)
<br>
El productor selecciona un lote existente y hace clic en "Generar QR". El sistema genera un código QR único para ese lote y muestra una vista previa. El productor tiene opciones para descargar o imprimir el código QR.

- **User Goal: Registrar paso**
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Wireflows%20-%20%20Registrar%20paso.png)
<br>
Un actor (productor, transportista, etc.) inicia sesión y selecciona un lote activo. Luego, hace clic en "Registrar Paso". Se le presenta un formulario con campos específicos según su rol (tipo de paso, fecha, hora, ubicación GPS automática, etc.). Al completar el formulario y hacer clic en "Registrar Paso", el sistema valida la información y registra el paso en la blockchain. Se muestra una confirmación con el ID del evento y el hash de la transacción.

- **User Goal: Escanear QR**
<br>
![wireframe-landing page.jpeg](../assets/wireframes/Wireflows%20-%20%20Escanear%20QR.png)
<br>
El consumidor abre la aplicación y activa el escáner de QR. Enfoca el código QR del producto con la cámara y el sistema lo reconoce automáticamente. Inmediatamente se muestra el historial completo de trazabilidad del lote, incluyendo: fecha y hora de cada paso del proceso, empresas participantes en la cadena de suministro, ubicaciones verificadas con GPS, certificaciones de calidad, mapa interactivo del recorrido, sellos de verificación en blockchain.El usuario puede navegar por la línea de tiempo, ver detalles de cada evento y verificar la autenticidad de la información mediante los hashes de blockchain.

#### 6.4.3 Applications Mock-ups
#### 6.4.4 Applications User Flow Diagrams
User Flow es una representación gráfica que representa el camino completo que sigue un usuario para completar una tarea específica en una aplicación o sitio web.

- **User Goal: Iniciar sesión**
<br>
![wireframe-landing page.jpeg](../assets/mockups/User%20flows%20-%20foodchain-wireflows%20Iniciar%20sesión.png)
<br>

- **User Goal: Crear lote**
<br>
![wireframe-landing page.jpeg](../assets/mockups/User%20flows%20-%20foodchain-wireflows%20Crear%20lote.png)
<br>

- **User Goal: Cerrar lote**
<br>
![wireframe-landing page.jpeg](../assets/mockups/User%20flows%20-%20foodchain-wireflows%20Cerrar%20lote.png)
<br>

- **User Goal: Registrar paso**
<br>
![wireframe-landing page.jpeg](../assets/mockups/User%20flows%20-%20foodchain-wireflows%20Registrar%20paso.png)
<br>

- **User Goal: Escanear QR**
<br>
![wireframe-landing page.jpeg](../assets/mockups/User%20flows%20-%20foodchain-wireflows%20Escanear%20QR.png)
<br>

### 6.5 Applications Prototyping  

- **Prototype Web Application**
<br>
![wireframe-landing page.jpeg](../assets/mockups/prototype-web.png)
<br>

- **Prototype Mobile Application**
<br>
![wireframe-landing page.jpeg](../assets/mockups/prototype-mobile.png)
<br>