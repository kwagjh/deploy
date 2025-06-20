# Forecast System Web

This repository contains a Spring Boot application backed by PostgreSQL.
It demonstrates basic forecasting and authentication features.

## Prerequisites

- **Java 17**
- **Maven** (or use the provided `./mvnw` wrapper)

## Running locally

1. Configure database details in `src/main/resources/application.properties`.
2. Start the application:

   ```bash
   mvn spring-boot:run
   ```

3. Visit `http://localhost:8080` and sign in using the seeded users.

## Deploying to Azure

1. Provision a PostgreSQL database in Azure.
2. Create an Azure App Service or Function App that supports Java 17.
3. Set the following application settings in your Azure App Service:
   - `SPRING_DATASOURCE_URL`
   - `SPRING_DATASOURCE_USERNAME`
   - `SPRING_DATASOURCE_PASSWORD`
4. Save the app's publish profile as the repository secret `AZURE_FUNCTIONAPP_PUBLISH_PROFILE`.
5. Edit `.github/workflows/azure-functions-app-java.yml` and set the following values:
   - `AZURE_FUNCTIONAPP_NAME` – your app name.
   - `JAVA_VERSION` – typically set to `17`.
6. Commit and push to the `main` branch. The included GitHub Actions workflow will build and deploy the application.
