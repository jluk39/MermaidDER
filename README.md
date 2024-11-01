# Diagrama de Entidad-Relación (DER)

A continuación se presenta el diagrama de entidad-relación para la base de datos de vuelos, aeropuertos, pasajeros y personas.

```mermaid
erDiagram
    FLIGHTS {
        INTEGER id PK
        INTEGER origin_id
        INTEGER destination_id
        INTEGER duration
    }
    
    AIRPORT {
        INTEGER id PK
        VARCHAR(10) code
        VARCHAR(100) city
    }
    
    PASSENGERS {
        INTEGER person_id PK
        INTEGER flight_id
    }
    
    PEOPLE {
        INTEGER id PK
        VARCHAR(50) first
        VARCHAR(50) last
    }

    FLIGHTS ||--o{ AIRPORT : "originates"
    FLIGHTS ||--o{ AIRPORT : "arrives"
    PASSENGERS }o--|| PEOPLE : "includes"
    PASSENGERS }o--|| FLIGHTS : "books"


```
# Diccionario de Datos

## Tablas y Atributos

| Tabla        | Atributo             | Tipo        | Descripción                                      |
|--------------|----------------------|-------------|--------------------------------------------------|
| **FLIGHTS**  | `id`                 | INTEGER     | Identificador único del vuelo (PK).              |
|              | `origin_id`          | INTEGER     | ID del aeropuerto de origen.                     |
|              | `destination_id`     | INTEGER     | ID del aeropuerto de destino.                    |
|              | `duration`           | INTEGER     | Duración del vuelo en minutos.                   |
| **AIRPORT**  | `id`                 | INTEGER     | Identificador único del aeropuerto (PK).         |
|              | `code`               | VARCHAR (10)      | Código del aeropuerto.                            |
|              | `city`               | VARCHAR (100)     | Ciudad donde se encuentra el aeropuerto.         |
| **PASSENGERS**| `person_id`         | INTEGER     | ID de la persona (pasajero) (PK).               |
|              | `flight_id`          | INTEGER     | ID del vuelo en el que está el pasajero.        |
| **PEOPLE**   | `id`                 | INTEGER     | Identificador único de la persona (PK).          |
|              | `first`              | VARCHAR (50)     | Nombre de la persona.                            |
|              | `last`               | VARCHAR (50)      | Apellido de la persona.                          |

