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

1. Provision a PostgreSQL database in Azure and update `application.properties` with its connection string.
2. Create an Azure App Service or Function App that supports Java 17.
3. Save the app's publish profile as the repository secret `AZURE_FUNCTIONAPP_PUBLISH_PROFILE`.
4. Edit `.github/workflows/azure-functions-app-java.yml` and set the following values:
   - `AZURE_FUNCTIONAPP_NAME` – your app name.
   - `JAVA_VERSION` – typically set to `17`.
5. Commit and push to the `main` branch. The included GitHub Actions workflow will build and deploy the application.
