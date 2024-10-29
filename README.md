# Diagrama de Entidad-Relación (DER)

## Entidades

| Entidad    | Atributos                                        |
|------------|--------------------------------------------------|
| **FLIGHTS**| `id` (PK)                                       |
|            | `origin_id`                                     |
|            | `destination_id`                                |
|            | `duration`                                      |
| **AIRPORT**| `id` (PK)                                       |
|            | `code`                                          |
|            | `city`                                          |
| **PASSENGERS**| `person_id` (PK)                             |
|            | `flight_id`                                     |
| **PEOPLE** | `id` (PK)                                       |
|            | `first`                                         |
|            | `last`                                          |

## Relaciones

| Relación                         | Entidades Involucradas               |
|----------------------------------|--------------------------------------|
| Un vuelo **origina** en un aeropuerto | FLIGHTS ||--o{ AIRPORT             |
| Un vuelo **llega** a un aeropuerto   | FLIGHTS ||--o{ AIRPORT             |
| Un pasajero **incluye** a una persona | PASSENGERS }o--|| PEOPLE           |
| Un pasajero **reserva** un vuelo      | PASSENGERS }o--|| FLIGHTS          |
