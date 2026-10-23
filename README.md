# CI/CD Final Project: Continuous Integration and Continuous Delivery (Node.js Track)

This repository contains the completed final project for the Coursera course **Continuous Integration and Continuous Delivery (CI/CD)** offered by IBM Developer Skills Network.

## Project Overview

This project implements an automated, end-to-end CI/CD pipeline for a Node.js and Express RESTful Counter API microservice. The pipeline automates continuous integration using GitHub Actions and continuous delivery using Tekton Pipelines on Red Hat OpenShift.

### Key Capabilities
- **Microservice**: RESTful Counter API service built with Node.js, Express, Helmet, CORS, and Morgan.
- **Continuous Integration**: Automated linting with ESLint and unit testing with Jest via GitHub Actions on every push and pull request.
- **Continuous Delivery**: Automated build and deployment pipeline assembled with Tekton tasks (`cleanup`, `git-clone`, `eslint`, `jest`, `buildah`, `openshift-client`) executing on OpenShift.

## Repository Structure

```text
.
|-- .github/workflows/
|   `-- workflow.yml       # GitHub Actions CI workflow
|-- .tekton/
|   |-- tasks.yml          # Tekton cleanup and jest test tasks
|   `-- pipeline.yml       # Tekton OpenShift CD pipeline definition
|-- bin/
|   `-- setup.sh           # Environment setup script
|-- src/                   # Node.js Express application source code
|-- tests/                 # Unit and integration test cases (Jest)
|-- .eslintrc.js           # ESLint configuration
|-- Dockerfile             # Container image build configuration
|-- Procfile               # Process definition
|-- package.json           # Dependencies and scripts
`-- package-lock.json      # Dependency lockfile
```

## API Endpoints

- `GET /` - Service information
- `GET /health` - Health check
- `GET /counters` - List all counters
- `POST /counters/:name` - Create a new counter
- `GET /counters/:name` - Read a specific counter
- `PUT /counters/:name` - Increment a counter
- `DELETE /counters/:name` - Delete a counter

## Environment Requirements

- Node.js >= 18.0.0
- npm >= 9.0.0
- ESLint 8.42.0 (code linting)
- Jest 29.5.0 with Supertest 6.3.3 (unit testing)
- Docker / Buildah (containerization)
- Red Hat OpenShift 4.x
- Tekton Pipelines (`tekton.dev/v1beta1`)
- OpenShift CLI (`oc`) and Tekton CLI (`tkn`)

## Setup Instructions

1. Install project dependencies:
   ```bash
   npm install
   ```

2. Run code linter:
   ```bash
   npm run lint
   ```

3. Run unit test suite:
   ```bash
   npm test
   ```

4. Run with code coverage:
   ```bash
   npm run test:coverage
   ```

## Author

- **Name**: Parag
- **GitHub**: [Paragraut24](https://github.com/Paragraut24)
- **Course**: IBM DevOps and Software Engineering - Continuous Integration and Continuous Delivery (CI/CD)

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for details.