# **Capítulo V: Tactical-Level Software Design**

El diseño de software a nivel táctico se enfoca en el "cómo", detallando la estructura interna de cada Bounded Context identificado en el diseño estratégico. Para FoodChain, aplicamos los patrones de Domain-Driven Design (DDD) para modelar las clases, agregados, entidades y servicios que encapsulan la lógica de negocio de manera coherente y robusta.

Este capítulo descompone el diseño detallado de uno de los Core Domains de nuestra solución, el **Bounded Context: Batch Management**, responsable del ciclo de vida de los lotes.

## **5.1. Bounded Context: Batch Management**

Este Bounded Context es el responsable exclusivo del **ciclo de vida del Lote (`Batch`)**. Su única preocupación es la creación, modificación de estado (ej. "cerrar" un lote) y la consistencia de la información maestra del lote. Siguiendo el principio de alta cohesión y bajo acoplamiento, este servicio no tiene conocimiento sobre los eventos de trazabilidad individuales ni sobre la tecnología blockchain.

### **5.1.1. Domain Layer**

La capa de dominio contiene el corazón de la lógica de negocio, encapsulada en el Aggregate Root `Batch`. Esta capa es completamente independiente de la infraestructura y de la capa de aplicación, enfocándose únicamente en las reglas y el estado del dominio.

| <<Aggregate Root>> Batch |
|---|
| **Descripción:** Representa un lote de productos como una unidad de gestión. Es la raíz del agregado y el único punto de entrada para modificar su estado, garantizando así la consistencia de sus invariantes de negocio (reglas). |
| **Atributos:** |
| `- batchId: BatchId (Value Object)` |
| `- enterpriseId: UUID` |
| `- productDescription: String` |
| `- creationDate: DateTime` |
| `- status: BatchStatus (Enum: OPEN, CLOSED)` |
| **Métodos:** |
| `+ static create(enterpriseId: UUID, productDescription: String): Batch` |
| `+ close(): void` |
| `+ updateDetails(newDescription: String): void` |

| <<Value Object>> BatchId |
|---|
| **Descripción:** Representa el identificador único de un Lote. Como Value Object, es inmutable y se valida en su creación para garantizar que no sea nulo o vacío. |
| **Atributos:** |
| `- value: UUID` |
| **Métodos:** |
| `+ BatchId(value: UUID)` |
| `+ equals(other: Object): boolean` |

| <<Repository Interface>> IBatchRepository |
|---|
| **Descripción:** Define el contrato que debe cumplir la capa de infraestructura para la persistencia del agregado `Batch`. Desacopla la lógica de dominio de los detalles de la base de datos. |
| **Métodos:** |
| `+ save(batch: Batch): void` |
| `+ findById(batchId: BatchId): Optional<Batch>` |
| `+ nextIdentity(): BatchId` |

### **5.1.2. Interface Layer**

La capa de interfaces (o de presentación) expone los casos de uso del Bounded Context al mundo exterior a través de endpoints REST. Actúa como la fachada del microservicio, recibiendo peticiones HTTP, validando la entrada (DTOs) y delegando la ejecución a la capa de aplicación.

| <<Controller>> BatchController |
|---|
| **Descripción:** Punto de entrada para todas las operaciones relacionadas con lotes. Traduce las peticiones HTTP en Comandos y los pasa al servicio de aplicación. |
| **Dependencias:** `BatchService`, `IAMAntiCorruptionLayer` |
| **Métodos (Endpoints):** |
| `+ POST /api/v1/batches (resource: CreateBatchResource): ResponseEntity<UUID>` |
| `+ PUT /api/v1/batches/{id}/close: ResponseEntity<Void>` |
| `+ GET /api/v1/batches/{id}: ResponseEntity<BatchDetailsResponse>` |

| Resource DTOs (Data Transfer Objects) |
|---|
| **Descripción:** Objetos planos utilizados para transferir datos entre el cliente y el controlador. No contienen lógica de negocio. |
| `CreateBatchResource (Request)` |
| `BatchDetailsResponse (Response)` |

| <<Anti-Corruption Layer>> IAMAntiCorruptionLayer |
|---|
| **Descripción:** Implementación del cliente que protege al `Batch Management Service` de los detalles internos del `Identity Service`. Es responsable de realizar una llamada **HTTP REST** al endpoint de validación del `Identity Service` para verificar un token JWT. Si el token es válido, traduce la información relevante (como el ID de usuario y sus permisos) en un `Value Object` local (`AuthorizedActor`) que el dominio puede utilizar sin estar acoplado a la estructura de un JWT. |
| **Dependencias:** `RestTemplate` o `WebClient` (Spring) |
| **Métodos Implementados:** |
| `+ validateAndTranslate(token: String): AuthorizedActor` |

### **5.1.3. Application Layer**

La capa de aplicación es la responsable de orquestar los casos de uso. No contiene lógica de negocio del dominio, sino que actúa como un coordinador: recibe un Comando, utiliza el Repositorio para cargar el Agregado correspondiente, invoca el método de negocio apropiado en el Agregado y, finalmente, utiliza el Repositorio para persistir el nuevo estado.

| <<Application Service>> BatchService |
|---|
| **Descripción:** Implementa los casos de uso del Bounded Context. Cada método público corresponde a un Comando que el sistema puede ejecutar. |
| **Dependencias:** `IBatchRepository` |
| **Métodos (Command Handlers):** |
| `+ handle(command: CreateBatchCommand): BatchId` |
| `+ handle(command: CloseBatchCommand): void` |
| `+ handle(command: UpdateBatchDetailsCommand): void` |

| Command/Query Objects |
|---|
| **Descripción:** Objetos inmutables que representan la intención de una operación, ya sea un cambio de estado (Comando) o una solicitud de datos (Query). |
| `CreateBatchCommand` |
| `CloseBatchCommand` |
| `GetBatchDetailsQuery` |

### **5.1.4. Infrastructure Layer**

En esta capa, el equipo presenta aquellas clases que acceden a servicios externos como bases de datos o APIs de otros microservicios. Es en esta capa que se ubica la implementación de las interfaces de `Repository` definidas en la Domain Layer, actuando como un puente entre el modelo de dominio y la tecnología de persistencia. De igual manera, aquí se implementan los clientes que consumen servicios externos, como el `Identity Service`.

| <<Repository Implementation>> BatchRepositoryImpl |
|---|
| **Descripción:** Implementación concreta de la interfaz `IBatchRepository`. Utiliza un framework de persistencia como **JPA (con Hibernate)** para mapear el agregado `Batch` y sus componentes a las tablas correspondientes en la `BatchDatabase`. Se encarga de traducir las llamadas del servicio de aplicación (ej. `save`) en operaciones de base de datos (ej. `INSERT`/`UPDATE`). |
| **Dependencias:** `EntityManager` (JPA) |
| **Métodos Implementados:** |
| `+ save(batch: Batch): void` |
| `+ findById(batchId: BatchId): Optional<Batch>` |
| `+ nextIdentity(): BatchId` |

### **5.1.5. Bounded Context Software Architecture Component Level Diagrams**

En esta sección, se presenta el Component Diagram del modelo C4 para el contenedor `Batch Management Service`. Este diagrama refleja la descomposición del contenedor en sus bloques estructurales principales y sus interacciones, mostrando cómo se orquesta un caso de uso siguiendo los principios de Domain-Driven Design. El diagrama ilustra el flujo de un comando desde su entrada en el `Batch Controller`, pasando por la validación de seguridad en la capa `ACL`, la orquestación en el `Application Service`, la ejecución de la lógica de negocio en el `Batch Aggregate` y finalmente la persistencia a través del `Batch Repository`.

###### **Figura [N°]: Diagrama de Componentes del Batch Management Service**
*Diagrama de Componentes del Batch Management Service*
`../assets/img/chapter-4/c4/structurizr-106906-BatchManagementService_Components.svg`

### **5.1.6. Bounded Context Software Architecture Code Level Diagrams**

En esta sección, se presentan y explican los diagramas que ofrecen un mayor detalle sobre la implementación de los componentes en el Bounded Context. Aquí se incluyen como secciones internas los diagramas de clases del Dominio y el diagrama de la Base de Datos.

#### **5.1.6.1. Bounded Context Domain Layer Class Diagrams**

En esta sección se presenta el Class Diagram de UML para las clases del Domain Layer en el `Batch Management Context`. El diagrama modela las clases, interfaces y enumeraciones clave, detallando sus atributos, métodos y visibilidad (private, public). Se evidencian las relaciones fundamentales de DDD: el `Batch Aggregate Root` encapsula su estado y expone métodos de negocio, utilizando el `BatchId Value Object` como su identificador. La interfaz `IBatchRepository` define el contrato de persistencia, desacoplando el dominio de la infraestructura.

###### **Figura [N°]: Diagrama de Clases del Dominio de Batch Management**
*(Placeholder para el diagrama de clases UML)*

#### **5.1.6.2. Bounded Context Database Design Diagram**

En esta sección se presenta y explica el Database Diagram que incluye los objetos de base de datos que permitirán la persistencia de información para el `Batch Management Context`. Dado que este Bounded Context sigue el patrón "Database-per-Service", posee su propio esquema aislado. El diagrama muestra la tabla `batches`, que es la representación relacional del agregado `Batch`. Se especifican sus columnas, tipos de datos y constraints (Primary Key), reflejando cómo el estado del agregado es persistido.

###### **Figura [N°]: Diagrama de Base de Datos de Batch Management**
*(Placeholder para el diagrama de la base de datos)*

## **5.2. Bounded Context: Traceability**

Este Bounded Context tiene una única y crucial responsabilidad: **registrar los eventos inmutables** que ocurren a lo largo de la cadena de suministro para un lote específico. Actúa como un libro de registro (`ledger`) auditable. Su principal función es crear una entrada por cada paso (`TraceabilityEvent`), persistirla y, fundamentalmente, **publicar un evento de dominio** para notificar al resto del sistema que un nuevo paso ha sido registrado. No tiene conocimiento del ciclo de vida del lote, solo de la secuencia de eventos que le pertenecen.

### **5.2.1. Domain Layer**

La capa de dominio de este contexto se centra en la entidad `TraceabilityEvent`. A diferencia de un agregado, un evento es inmutable una vez creado; no tiene un ciclo de vida complejo, simplemente se registra.

| <<Entity>> TraceabilityEvent |
|---|
| **Descripción:** Representa un evento atómico e inmutable en el historial de un lote (ej. 'Cosecha', 'Transporte'). Es una pieza de evidencia que tiene su propia identidad y no puede ser alterada una vez registrada. |
| **Atributos:** |
| `- eventId: EventId (Value Object)` |
| `- batchId: BatchId (Value Object)` |
| `- eventType: String` |
| `- timestamp: DateTime` |
| `- actorId: UUID` |
| `- location: Location (Value Object)` |
| `- blockchainStatus: BlockchainStatus (Enum: PENDING, CONFIRMED, FAILED)` |
| `- transactionHash: String (nullable)` |
| **Métodos:** |
| `+ static record(batchId: BatchId, type: String, actorId: UUID, location: Location): TraceabilityEvent` |
| `+ confirmAnchoring(txHash: String): void` |
| `+ markAsFailed(): void` |

| <<Value Object>> Location |
|---|
| **Descripción:** Representa la localización geográfica donde ocurrió un evento. Es inmutable y se define por sus valores (latitud, longitud), garantizando que una ubicación es siempre la misma si sus coordenadas lo son. |
| **Atributos:** |
| `- latitude: Double` |
| `- longitude: Double` |
| **Métodos:** |
| `+ Location(latitude: Double, longitude: Double)` |
| `+ equals(other: Object): boolean` |

| <<Repository Interface>> ITraceabilityRepository |
|---|
| **Descripción:** Define el contrato para la persistencia de la entidad `TraceabilityEvent`. |
| **Métodos:** |
| `+ save(event: TraceabilityEvent): void` |
| `+ findByBatchId(batchId: BatchId): List<TraceabilityEvent>` |
| `+ nextIdentity(): EventId` |

### **5.2.2. Interface Layer**

La capa de interfaces expone el endpoint para que los actores de la cadena registren nuevos eventos y para que los sistemas de consulta (como el `Consumer Inquiry Context`) puedan obtener el historial de un lote.

| <<Controller>> StepController |
|---|
| **Descripción:** Punto de entrada para todas las operaciones relacionadas con los eventos de trazabilidad. |
| **Dependencias:** `TraceabilityService`, `IAMAntiCorruptionLayer` |
| **Métodos (Endpoints):** |
| `+ POST /api/v1/trace/events (resource: RegisterStepResource): ResponseEntity<UUID>` |
| `+ GET /api/v1/trace/history/{batchId}: ResponseEntity<TraceabilityHistoryResponse>` |

| Resource DTOs (Data Transfer Objects) |
|---|
| **Descripción:** Objetos planos para la comunicación. `RegisterStepResource` contiene los datos necesarios para registrar un nuevo evento. `TraceabilityHistoryResponse` contiene la lista de eventos para ser mostrada al consumidor. |
| `RegisterStepResource (Request)` |
| `TraceabilityHistoryResponse (Response)` |

### **5.2.3. Application Layer**

La capa de aplicación orquesta el caso de uso de registrar un nuevo evento. Su responsabilidad más importante es, tras persistir el evento en su propia base de datos, **publicar un evento de dominio** para que el `Blockchain Worker` pueda actuar de forma asíncrona.

| <<Application Service>> TraceabilityService |
|---|
| **Descripción:** Implementa el caso de uso de registrar un evento. Actúa como un Command Handler que coordina la creación de la entidad, su persistencia y la publicación del evento de dominio resultante. |
| **Dependencias:** `ITraceabilityRepository`, `IDomainEventPublisher` |
| **Métodos (Command Handlers):** |
| `+ handle(command: RegisterStepCommand): EventId` |

| <<Query Service>> HistoryQueryService |
|---|
| **Descripción:** Servicio dedicado a manejar las consultas de solo lectura, optimizado para recuperar y formatear el historial de trazabilidad de un lote. |
| **Dependencias:** `ITraceabilityRepository` |
| **Métodos (Query Handlers):** |
| `+ handle(query: GetHistoryByBatchIdQuery): TraceabilityHistoryResponse` |

| Command/Query Objects |
|---|
| **Descripción:** Objetos que representan la intención de una operación. `RegisterStepCommand` encapsula todos los datos para crear un nuevo evento. |
| `RegisterStepCommand` |
| `GetHistoryByBatchIdQuery` |