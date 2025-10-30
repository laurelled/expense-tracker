## API description

Backend microservices for expense tracking (`auth`, `users`, `expenses`).
Tech stack: Node.js + Fastify + TypeScript + MongoDB.

This API should let you:

- Sign up as a new user.

- Generate and validate JWTs for handling authentication and user session.

- List and filter your past expenses. You can add the following filters:

    - Past week.

    - Last month.

    - Last 3 months.

    - Custom (to specify a start and end date of your choosing).

- Add new expenses.

- Remove existing expenses.

- Update existing expenses.

## Requirements

- a working IDE (VSCodium or others)
- MongoDB 8.0.13 or higher Community
- Node version v24.1.0 or higher
- Docker (optionally)

## Installation

To install dependencies, run

1. `npm ci`
2. Start local infrastructure: `docker-compose up --build`

## Project layout

```
.github -- CI workflows
services/ -- each deployable microservice
|--auth/
    |--src/
        |--controllers/
        |--plugins/
        |--libs/
        |--routes/
        |--schemas/
    |--tests/
    |--package.json (workspace package)
|--users/
    ...same structure
|--expenses/
    ...same structure
libs/ -- shared libraries
|--auth-middleware/
    |--src/
    |--package.json (workspace package)
|--.../
infra/ -- docker-compose, k8s manifests
.env.example
package.json (root package)
```

## Git workflow
- Branching: uses feature branching. `feature/`, `fix/` prefixes
- Commit: follows [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)  (message should complete the sentence "this commit will..")
- PRs: small and focused, with testing steps.

## GitHub repo setup

The GitHub repo is set up to have the `main` branch with 

## Testing 
The root package can run `npm test` that runs the same script in each workspace.

## Linting
The root package can run `npm run lint` that runs the same script in each workspace.

## Application

To change application configuration, you can set up environment variables creating a `.env` file. You can see the variables you can change in the `default.env` file.

## Authorization - JWT tokens

The endpoints use JWT token as the authorization mechanism. A future challenge will be storing them in the front-end securely, so I asked myself "How can JWT tokens be stored securely?". As per the (OWASP HTML5 Cheatsheet)[https://cheatsheetseries.owasp.org/cheatsheets/HTML5_Security_Cheat_Sheet.html#local-storage], local storage is not recommended, and session storage or cookies would be ideal. (This guide)[https://workos.com/blog/secure-jwt-storage] on how to securely store JWT token is worth a read, since it explains various flags to avoid the most common attacks.

Also, it's also worth re-reading (what are JWT and its use cases)[https://www.jwt.io/introduction#how-json-web-tokens-work].
