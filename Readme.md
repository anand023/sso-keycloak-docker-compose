
### Using Docker Compose Commands with Custom Filename

1. **Start the Services**:

   ```sh
   docker-compose -f docker-compose-keycloak-postgresql.yaml up
   ```

2. **Start the Services in Detached Mode**:

   ```sh
   docker-compose -f docker-compose-keycloak-postgresql.yaml up -d
   ```

3. **Stop the Services**:

   ```sh
   docker-compose -f docker-compose-keycloak-postgresql.yaml down
   ```
By using the `-f` flag, you can specify any custom name for your Docker Compose file and still manage your services effectively.

- **Volumes Section**: 
  - The `volumes` section at the bottom defines a named volume called `postgres_data`. This volume uses the default `local` driver, which stores data on the host filesystem.
  - This ensures that data stored in the PostgreSQL database persists across container restarts or recreation.

### Usage Steps

1. **Access Keycloak** at `http://localhost:8180`.

2. **Log in** with the Keycloak admin credentials (`admin`/`admin`).

This configuration ensures that PostgreSQL data is persisted to the `postgres_data` volume, providing durability across container lifecycle events.
