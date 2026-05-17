# SpringAIDemo

SpringAIDemo is a demo repository showing how to integrate AI capabilities into a Spring Boot application. It provides a small, easy-to-follow scaffold with example services and REST endpoints so you can experiment with calling AI APIs from a familiar Spring environment.

> Note: This repository is a demo. Replace placeholder code, endpoints, and configuration with your real AI provider and secure secrets management before production use.

## Features

- Minimal Spring Boot application scaffold
- Example AI service component (placeholder) showing how to call an external AI API
- REST controller exposing simple endpoints for health and AI queries
- Configuration examples for API keys and endpoints
- Guidance for testing, development, and production hardening

## Prerequisites

- Java 17 or newer
- Maven 3.6+ (project is Maven-based by default)
- An API key for the AI provider you choose to use

## Quick start

1. Clone the repo

   git clone https://github.com/jcentino/SpringAIDemo.git
   cd SpringAIDemo

2. Provide your AI API key. Prefer using environment variables or a secrets manager. Example env var:

   export AI_API_KEY="your_api_key_here"

   (Alternatively set ai.api.key in src/main/resources/application.properties for local testing only.)

3. Build and run

   mvn clean package
   mvn spring-boot:run

4. Open http://localhost:8080

## Example endpoints

- GET /health — simple health check
- POST /ai/query — submit a JSON payload with a prompt (controller expects a small JSON object; adapt to your implementation)

Example curl (adjust JSON shape to match your controller):

curl -X POST http://localhost:8080/ai/query \
  -H "Content-Type: application/json" \
  -d '{"prompt":"Say hello from SpringAIDemo"}'

## Configuration keys

The demo uses these configuration keys (see application.properties):

- ai.api.key — API key for the AI provider
- ai.endpoint — (optional) override endpoint for the provider
- server.port — Spring Boot server port (default 8080)

## Development notes

- Keep external API calls isolated in a service layer to allow unit testing by mocking.
- Consider using a typed SDK for your AI provider, or an HTTP client with timeouts and retry logic.
- Add appropriate exception handling, retries, and rate-limit handling for production.
- Never commit secrets into source control; use environment variables or a secrets store.

## Testing

- Add unit tests under src/test/java. Mock the AI client when testing the service and controller layers.
- For integration testing, consider a local stub for the AI provider or use recorded responses.

## Contributing

Contributions are welcome. Open an issue or submit a pull request.

## License

This repository is provided as a demo. Add a LICENSE file (for example, MIT) if you plan to publish or reuse the code publicly.

## Contact

For questions, contact the repository owner.
