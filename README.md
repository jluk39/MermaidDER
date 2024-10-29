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
        STRING code
        STRING city
    }
    
    PASSENGERS {
        INTEGER person_id PK
        INTEGER flight_id
    }
    
    PEOPLE {
        INTEGER id PK
        STRING first
        STRING last
    }

    FLIGHTS ||--o{ AIRPORT : "originates"
    FLIGHTS ||--o{ AIRPORT : "arrives"
    PASSENGERS }o--|| PEOPLE : "includes"
    PASSENGERS }o--|| FLIGHTS : "books"
