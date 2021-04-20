# __MagnetoMutants__
Challenge MercadoLibre

### Magneto quiere reclutar la mayor cantidad de mutantes para poder luchar contra los X-Men.
### Te ha contratado a ti para que desarrolles un proyecto que detecte si un humano es mutante basándose en su secuencia de ADN.

![magneto2](https://user-images.githubusercontent.com/58950018/115470578-ef1e9c00-a20c-11eb-974d-810d81e114d0.png)

---

## __Tecnologías__
- Java 8
- Spring Boot
- MongoDB
- Maven
- AWS

## __Lanzar la aplicación__
Deberá clonarse el repositorio y, parado sobre la raíz del proyecto, lanzar el comando mvn spring-boot:run

### Consideraciones
- Deberá tener una instancia MongoDB en su ambiente, los parametros de conexion a la base puede encontrarlos en el archivo de configuracion application.properties.
- Intalada una version de java 8 o superior.
- Instalado Maven.
- Conexion a internet para bajar las librerias de los repositorios remotos que les sean necesarias para compilar y ejecutar el proyecto.

---

## __API URLs__

### Desarrollo: http://localhost:8080
### Producción:

## __Servicios disponibilizados__

### /mutant - Verifica si un humado es mutante

``` 
POST /v1/api/mutants 
```
#### Body (ADN Humano)
```
{"dna":["AATACT", "CCCAGA", "GGGATT", "AATTCC", "GGATCG", "TCACTG"]}
```
#### Response
``` 
403 Forbidden 
```

#### Body (ADN Mutante)
```
{"dna":["ATGCGA", "CAGGGC", "TTATGT", "AGAAGG", "CCCCTA", "TCACTG"]}
```
#### Response: 
``` 
200 OK 
```

### /atats - Retorna las estadisticas de los humanos verificados, dando cantidades y el ratio de mutantes encontrados.
``` 
GET /v1/api/atats 
``` 

### Response: 
``` 
{
    "ratio": 6.0,
    "count_mutant_dna": 6,
    "count_human_dna": 0
}
```
