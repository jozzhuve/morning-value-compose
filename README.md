
# Gran Torneo Galáctico (Java 17 + React + Docker Compose)

Sistema demo con arquitectura de microservicios (hexagonal) para gestionar especies y combates del **Gran Torneo Galáctico**.

- **Microservicios**:
  - `species-service`: registra/lista especies.
  - `combat-service`: inicia combates y expone ranking.
- **Frontend**: React + Vite (ranking).
- **H2 + Flyway**, **EhCache**, **Swagger/OpenAPI 3**.
- **Tracing**: OpenTelemetry javaagent + **Jaeger**.
- **Pruebas**: Unitarias e Integración. **JaCoCo** con umbral mínimo 60% (INSTRUCTION).

## Requisitos
- Docker y Docker Compose

## Ejecutar
```bash
docker compose build
docker compose up
```

Servicios:
- Frontend:        http://localhost:3000
- Species Swagger: http://localhost:8081/swagger-ui.html
- Combat Swagger:  http://localhost:8082/swagger-ui.html
- Jaeger UI:       http://localhost:16686

## Pruebas y cobertura (local)
```bash
cd species-service && mvn -q test jacoco:report
cd ../combat-service && mvn -q test jacoco:report
# Ver reportes en target/site/jacoco/index.html
```
