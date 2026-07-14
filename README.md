# GoREST API Testing Framework

API automation project for the GoREST public REST API.

✔ Postman Collection with reusable collection scripts  
✔ CRUD API testing with dynamic runtime data  
✔ JSON Schema validation and business logic assertions  
✔ Newman HTML reporting  
✔ CI/CD with GitHub Actions  
✔ Automatic report publishing to GitHub Pages  

[![GitHub Pages](https://img.shields.io/badge/View-Latest_Report-blue?logo=github)](https://konstantinkovalenko.github.io/gorest-postman-newman/)

---

## Test Coverage

The collection validates the complete User CRUD workflow.

Positive scenarios:
- Create User
- Get User by ID
- Update User
- Partial Update User
- Delete User
- Get All Users with pagination and filtering

Negative scenarios:
- Create User with Existing Email (422)
- Update User with Invalid Gender (422)
- Partial Update User without Authorization (401)
- Get Deleted User by ID (404)

---

## Automated Validations

Common assertions are centralized at the collection level where possible.

The project validates:

- HTTP status codes
- Response time
- Content-Type validation
- JSON Schema validation (AJV)
- CRUD data consistency
- Runtime-generated test data
- Pagination
- Filtering
- Negative API scenarios (401, 404, 422)

---

## CI/CD

GitHub Actions automatically:

- Runs on push and pull request events
- Installs project dependencies
- Executes the Newman collection
- Injects the API token securely using GitHub Secrets
- Generates an HTML report
- Uploads the report as a workflow artifact
- Publishes the latest report to GitHub Pages

---

## Project Structure

```
├── collections/  
│   └── goREST.postman_collection.json   
├── environments/  
│   └── qa.postman_environment.json  
├── reports/  
├── .github/  
│   └── workflows/  
├── package.json  
└── README.md  
```

---

## Getting started
### Install
```
npm install
```
### Run Tests
> **Note:** Before running the collection locally, configure a valid GoREST API token in the `cfg_token` environment variable.
#### Execute the collection:
```
npm run newman
```
#### Execute the collection and generate an HTML report:
```
npm run report
```
#### Remove generated reports:
```
npm run clean
```

---

## Environment Management

The project separates configuration and runtime data using environment variables. Sensitive values such as API tokens are provided securely through GitHub Secrets during CI execution.

### Configuration Variables
- cfg_baseURL
- cfg_token
- cfg_maxResponseTime
- cfg_page
- cfg_perPage
- cfg_status

### Runtime Variables

Runtime variables are generated automatically during collection execution using Postman local variables (`pm.variables`) to keep test runs isolated and avoid persisting temporary data.

Examples include:

- runtime_userId
- runtime_userName
- runtime_userEmail
- runtime_expectedStatusCode

---

## Author

Konstantin Kovalenko

* GitHub: https://github.com/KonstantinKovalenko  
* LinkedIn: [www.linkedin.com/in/kostyantyn-kovalenko/](https://www.linkedin.com/in/kostyantyn-kovalenko/)
* Email: chvyaka.kk@gmail.com
* Telegram: @kovakost