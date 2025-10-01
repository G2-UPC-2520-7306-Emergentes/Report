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

### 5.1.2. Interface Layer

### 5.1.3. Application Layer

### 5.1.4. Infrastructure Layer

### 5.1.5. Bounded Context Software Architecture Component Level Diagrams 

### 5.1.6. Bounded Context Software Architecture Code Level Diagrams

#### 5.1.6.1. Bounded Context Domain Layer Class Diagrams

#### 5.1.6.2. Bounded Context Database Design Diagram.

