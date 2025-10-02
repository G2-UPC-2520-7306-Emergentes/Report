# Capítulo V: Tactical-Level Software Design 

## 5.1. Bounded Context: Trazabilidad

El diccionario de clases del Bounded Context Trazabilidad detalla la estructura del Core Domain de FoodChain. Diseñado bajo Domain-Driven Design (DDD), este modelo encapsula la lógica inmutable para el registro de eventos en la cadena de suministro, asegurando la integridad y consistencia de los datos anclados a la blockchain.

<table style="width:100%; border-collapse: collapse; border: 1px solid black; table-layout: fixed;">
  <thead>
    <tr>
      <th colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Nombre: LoteDeTrazabilidad</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Relaciones: EventoDeTrazabilidad (Composition), Producto (Reference), Actor (Reference)</td>
    </tr>
    <tr>
      <td colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Descripción: Representa el historial inmutable de un lote de productos a lo largo de la cadena de suministro, desde su origen hasta el consumidor final. Cada lote agrupa la secuencia de eventos de trazabilidad (creación, transformación, custodia) y la huella digital (hash) anclada en la blockchain, garantizando su integridad y auditabilidad.</td>



    </tr>
    <tr>
      <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: center;">Atributos</td>
      <td rowspan="2" style="border: 1px solid black; padding: 8px; text-align: center;">Métodos</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px; width: 20%; text-align: center;">Nombre</td>
      <td style="border: 1px solid black; padding: 8px; width: 20%; text-align: center;">Tipo de Dato</td>
      <td style="border: 1px solid black; padding: 8px; width: 10%; text-align: center;">Visibilidad</td>
      </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">loteId</td>
      <td style="border: 1px solid black; padding: 8px;">String</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
      <td rowspan="5" style="border: 1px solid black; padding: 8px; vertical-align: top;">
        LoteDeTrazabilidad() 



        LoteDeTrazabilidad(CrearLoteCommand) 



        registrarEvento(RegistrarEventoCommand) 



        actualizarEstado(String nuevoEstado) 



        consultarHistorial() 



        obtenerIdentificadorQR() 



        calcularYAnclarHash(EventoDeTrazabilidad)
      </td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">identificadorQR</td>
      <td style="border: 1px solid black; padding: 8px;">String</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">estado</td>
      <td style="border: 1px solid black; padding: 8px;">String</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">producto</td>
      <td style="border: 1px solid black; padding: 8px;">Producto</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">historialEventos</td>
      <td style="border: 1px solid black; padding: 8px;">List&lt;EventoDeTrazabilidad&gt;</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
  </tbody>
</table>

<table style="width:100%; border-collapse: collapse; border: 1px solid black; table-layout: fixed;">
  <thead>
    <tr>
      <th colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Nombre: EventoDeTrazabilidad</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Relaciones: LoteDeTrazabilidad (Composition owner), Ubicacion (Value Object)</td>
    </tr>
    <tr>
      <td colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Descripción: Representa un evento atómico e inmutable (como 'Cosecha', 'Transporte', 'Procesamiento') ocurrido en un momento y lugar específico. Contiene el hash de la transacción en la blockchain.</td>
    </tr>
    <tr>
      <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: center;">Atributos</td>
      <td rowspan="2" style="border: 1px solid black; padding: 8px; text-align: center;">Métodos</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px; width: 20%; text-align: center;">Nombre</td>
      <td style="border: 1px solid black; padding: 8px; width: 20%; text-align: center;">Tipo de Dato</td>
      <td style="border: 1px solid black; padding: 8px; width: 10%; text-align: center;">Visibilidad</td>
      </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">eventoId</td>
      <td style="border: 1px solid black; padding: 8px;">String</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
      <td rowspan="5" style="border: 1px solid black; padding: 8px; vertical-align: top;">
        EventoDeTrazabilidad(RegistrarEventoCommand) 



        asociarHashBlockchain(String hash) 



        obtenerUbicacion() 



        esEventoDeOrigen()
      </td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">tipoEvento</td>
      <td style="border: 1px solid black; padding: 8px;">String (Enum: Cosecha, Transporte, etc.)</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">fechaHora</td>
      <td style="border: 1px solid black; padding: 8px;">DateTime</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">hashTransaccion</td>
      <td style="border: 1px solid black; padding: 8px;">String</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">ubicacion</td>
      <td style="border: 1px solid black; padding: 8px;">Ubicacion</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
  </tbody>
</table>

<table style="width:100%; border-collapse: collapse; border: 1px solid black; table-layout: fixed;">
  <thead>
    <tr>
      <th colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Nombre: Ubicacion</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Relaciones: EventoDeTrazabilidad (Reference owner)</td>
    </tr>
    <tr>
      <td colspan="4" style="border: 1px solid black; padding: 8px; text-align: left;">Descripción: Es un Value Object. Define la localización geográfica o física donde ocurrió un evento. Es inmutable y se define por sus valores (latitud, longitud).</td>
    </tr>
    <tr>
      <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: center;">Atributos</td>
      <td rowspan="2" style="border: 1px solid black; padding: 8px; text-align: center;">Métodos</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px; width: 20%; text-align: center;">Nombre</td>
      <td style="border: 1px solid black; padding: 8px; width: 20%; text-align: center;">Tipo de Dato</td>
      <td style="border: 1px solid black; padding: 8px; width: 10%; text-align: center;">Visibilidad</td>
      </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">latitud</td>
      <td style="border: 1px solid black; padding: 8px;">Double</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
      <td rowspan="2" style="border: 1px solid black; padding: 8px; vertical-align: top;">
        Ubicacion(Double lat, Double lon) 



        getCoordenadasGPS() 



        equals(Object other)
      </td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px;">longitud</td>
      <td style="border: 1px solid black; padding: 8px;">Double</td>
      <td style="border: 1px solid black; padding: 8px;">private</td>
    </tr>
  </tbody>
</table>

### 5.1.1. Domain Layer

La capa de dominio del contexto Trazabilidad define las clases centrales que modelan el comportamiento y los datos fundamentales del sistema relacionados con el registro inmutable de eventos y la auditoría del producto a lo largo de la cadena de suministro. Esta capa agrupa Aggregate, Entidades, Value Objects y Servicios de Dominio que encapsulan las reglas de negocio, garantizando una lógica coherente para la verificación de la integridad del producto mediante la blockchain en la solución FoodChain.

| <<Aggregate>> LoteDeTrazabilidad             |
|----------------------------------------------|
|Atributos:                                    |
| loteId: String                               |
| identificadorQR: IdentificadorQR             |
| estadoActual: String                         |
| producto: Producto                           |
| historialEventos: List<EventoDeTrazabilidad> |
|Métodos:                                       |
| LoteDeTrazabilidad(CrearLoteCommand)         |
| registrarEvento(RegistrarEventoCommand)      |
| verificarIntegridad()                        |
| actualizarEstado(String)                     |


| <<Entity>> EventoDeTrazabilidad              |
|----------------------------------------------|
|Atributos:                                    |
| eventoId: String                             |
| tipoEvento: String                           |
| fechaHora: DateTime                          |
| actorResponsable: Actor                      |
| ubicacion: Ubicacion                         |
| hashTransaccion: String                      |
|Métodos:                                       |
| EventoDeTrazabilidad(RegistrarEventoCommand) |
| asociarHashBlockchain(String hash)           |
| obtenerActorResponsable()                    |

| <<ValueObject>> Ubicacion         |
|-----------------------------------|
|Atributos:                                    |
| latitud: Double                   |
| longitud: Double                  |
|Métodos:                           |
| Ubicacion(Double lat, Double lon) |
| getCoordenadasGPS()               |
| equals(Object)                    |

| <<DomainService>> ServicioDeAnclajeBlockchain |
|-----------------------------------------------|
|                                               |
|Métodos:                                       |
| anclarEvento(EventoDeTrazabilidad): Hash      |
| obtenerTransaccion(String hash)               |
| verificarHash(String hash)                    |

| <<Repository>> LoteDeTrazabilidadRepository |
|---------------------------------------------|
|                                             |
|Métodos:                                     |
| save(LoteDeTrazabilidad)                    |
| findById(String loteId): LoteDeTrazabilidad |
| delete(LoteDeTrazabilidad)                  | 

### 5.1.2. Interface Layer

La capa de interfaces contiene los Controladores REST que exponen los servicios del contexto Trazabilidad hacia el exterior. Estos puntos de entrada permiten a los actores de la cadena registrar eventos y a los consumidores consultar el historial completo de un producto mediante un QR.

| LoteController                                                                                                       |
|----------------------------------------------------------------------------------------------------------------------|
| +crearLoteOrigen(crearLoteResource: CrearLoteResource): ResponseEntity<LoteIdResponse>                               |
| +registrarEvento(loteId: String, registrarEventoResource: RegistrarEventoResource): ResponseEntity<EventoIdResponse> |
| +actualizarEstadoLote(loteId: String, nuevoEstado: String): ResponseEntity<Void>                                     |
| +obtenerEventosPendientes(actorId: String): ResponseEntity<List<EventoDeTrazabilidad>>                 |

| ConsultaTrazabilidadController                                                  |
|---------------------------------------------------------------------------------|
| +consultarPorQR(identificadorQR: String): ResponseEntity<HistorialLoteResponse> |
| +obtenerDetalleEvento(eventoId: String): ResponseEntity<DetalleEventoResponse>  |
| +verificarHash(hashTransaccion: String): ResponseEntity<VerificacionResponse>   |

| Resource DTOs (Objetos de Petición/Respuesta)                                          |
|----------------------------------------------------------------------------------------|
| CrearLoteResource (Request DTO para crear el lote inicial)                             |
| RegistrarEventoResource (Request DTO para un nuevo paso en la cadena)                  |
| HistorialLoteResponse (Response DTO que contiene toda la cadena de eventos para un QR) |
| EventoIdResponse (Response DTO simple con el ID del evento recién creado)              |




### 5.1.3. Application Layer

En esta capa se definen los Servicios de Aplicación que modelan los Casos de Uso Command/Query del contexto Trazabilidad. Su rol principal es orquestar la ejecución transaccional. Reciben comandos de la interfaz, utilizan los Repositorios como el LoteDeTrazabilidadRepository para cargar y guardar los Aggregate Roots del Dominio, y coordinan la secuencia de la tarea completa, incluyendo la llamada al Servicio de Anclaje a Blockchain. Esto asegura la coherencia de los datos en FoodChain.

| LoteCommandServiceImpl                             |
|----------------------------------------------------|
| loteRepository: LoteDeTrazabilidadRepository       |
| blockchainService: ServicioDeAnclajeBlockchain     |
|                                                    |
| +handle(command: CrearLoteCommand): LoteId         |
| +handle(command: RegistrarEventoCommand): EventoId |
| +handle(command: ActualizarEstadoCommand): void    |


| ConsultaTrazabilidadQueryServiceImpl            |
|-------------------------------------------------------------------|
| loteRepository: LoteDeTrazabilidadRepository                       |
|                                                                    |
| +handle(query: ObtenerHistorialPorQRQuery): HistorialLoteResponse  |
| +handle(query: ConsultarEventoPorHashQuery): DetalleEventoResponse |
| +handle(query: VerificarIntegridadLoteQuery): VerificacionResponse |

### 5.1.4. Infrastructure Layer

Esta capa es la encargada de resolver los detalles técnicos y de persistencia para el Bounded Context Trazabilidad. Esta capa implementa las interfaces de Repositorio y los Adaptadores de Servicios Externos definidos en la Capa de Dominio, sirviendo como el puente que conecta la lógica de negocio con las tecnologías de almacenamiento y la red Blockchain en FoodChain.

| LoteDeTrazabilidadRepository      |
|--------------------------------------------------------------------|
| +save(lote: LoteDeTrazabilidad): LoteDeTrazabilidad                 |
| +findById(loteId: String): Optional<LoteDeTrazabilidad>             |
| +findByIdentificadorQR(qrId: String): Optional<LoteDeTrazabilidad>  |
| +findAllEventosByLoteId(loteId: String): List<EventoDeTrazabilidad> |
| +delete(lote: LoteDeTrazabilidad): void                             

| ServicioDeAnclajeBlockchain|
|--------------------------------------------------------------------|
| +anclarEvento(evento: EventoDeTrazabilidad): HashTransaccion       |
| +consultarTransaccion(hash: String): JsonData                      |
| +verificarHash(hash: String): Boolean                              |

| Data Mappers                                                                |
|-------------------------------------------------------------------------------|
| LoteDataMapper (Mapea entre LoteDeTrazabilidad y LoteData/LoteEntity)         |
| EventoDataMapper (Mapea entre EventoDeTrazabilidad y EventoData/EventoEntity) |


### 5.1.5. Bounded Context Software Architecture Component Level Diagrams 

Esta sección presenta el diagrama de componentes correspondiente al Bounded Context Trazabilidad, donde se visualizan las principales dependencias entre el Controller REST, los Servicios de Aplicación (Commands y Queries), las Interfaces del Dominio y los Adaptadores de Infraestructura.

Este diagrama permite comprender cómo están organizados los distintos módulos dentro del contexto, cómo se comunican entre ellos, y cómo interactúan con los Actores y Sistemas Externos.


![boundedContextTraceability.png](../assets/img/bcTraceability.png)

### 5.1.6. Bounded Context Software Architecture Code Level Diagrams

#### 5.1.6.1. Bounded Context Domain Layer Class Diagrams

#### 5.1.6.2. Bounded Context Database Design Diagram.

