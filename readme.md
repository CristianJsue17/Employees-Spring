### Crear docker compose con postgresql primero
- Crear un archivo docker-compose.yml con el siguiente contenido:
```
services:
  postgres-taller:
    image: postgres:15-alpine
    container_name: db-taller
    environment:
      POSTGRES_USER: root
      POSTGRES_PASSWORD: root
      POSTGRES_DB: db_taller
    ports:
      - "5433:5432"
    volumes:
      - postgres_taller_data:/var/lib/postgresql/data
    restart: unless-stopped

volumes:
  postgres_taller_data:
```
- docker compose up -d
- docker compose exec postgres-taller psql -U root -d db_taller -c

### Arrancar spring boot
- Compilar proyecto con intelij idea.