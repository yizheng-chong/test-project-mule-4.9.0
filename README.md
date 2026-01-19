# Mule 4.9 Test Application (Java 17)

Minimal Mule application to test Mule 4.9 runtime with Java 17.

## Prerequisites

- Java 17 (set `JAVA_HOME` accordingly)
- Maven 3.8+
- Mule Runtime 4.9.x standalone

## Build

```bash
mvn clean package
```

This produces: `target/mule-test-app-1.0.0-SNAPSHOT-mule-application.jar`

## Deploy to Standalone Mule

Copy the JAR to your Mule `apps` directory:

```bash
cp target/mule-test-app-1.0.0-SNAPSHOT-mule-application.jar $MULE_HOME/apps/
```

Mule will auto-deploy the application (hot deployment).

## Test Endpoints

Once deployed:

- **Hello endpoint**: `curl {http://localhost:8081}/hello`
- **Health check**: `curl {http://localhost:8081}/health`

The health endpoint returns JSON with runtime version and Java version to confirm your environment.

## Verify Java 17

The `/health` endpoint output should show Java version 17.x.x, confirming the runtime is using Java 17.
