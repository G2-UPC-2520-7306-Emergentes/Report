# Capítulo II: Requirements Elicitation & Analysis


## 2.1. Competidores


### 2.1.1. Análisis competitivo



### 2.1.2. Estrategias y tácticas frente a competidores


## 2.2. Entrevistas


### 2.2.1. Diseño de entrevistas


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



### 2.3.4. Empathy Mapping


### 2.3.5. As-is Scenario Mapping



## 2.4. Ubiquitous Language

