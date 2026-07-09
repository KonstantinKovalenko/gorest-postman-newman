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

The collection validates the complete User CRUD workflow:

- Create User
- Get All Users
- Get User by ID
- Update User
- Partial Update User
- Delete User
- Negative Get User by ID (404)

---

## Automated Validations

Common assertions are centralized at the collection level where possible.

The project validates:

- HTTP status codes
- Response time
- Content-Type header
- JSON schema
- CRUD data consistency
- Pagination
- Filtering
- Negative API responses

---

## CI/CD

GitHub Actions automatically:

- Installs project dependencies
- Executes the Newman collection
- Generates an HTML report
- Uploads the HTML report as a workflow artifact
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

The project separates configuration and runtime data using environment variables.

### Configuration Variables
- cfg_baseURL
- cfg_token
- cfg_maxResponseTime
- cfg_page
- cfg_perPage
- cfg_status

### Runtime Variables

Runtime variables are generated automatically during execution to keep test runs independent and avoid hardcoded data.

Examples include:

- runtime_userId
- runtime_userName
- runtime_userEmail
- runtime_expectedStatusCode

All runtime variables are removed automatically after the collection finishes.

---

## Author

Konstantin Kovalenko

* GitHub: https://github.com/KonstantinKovalenko  
* LinkedIn: [www.linkedin.com/in/kostyantyn-kovalenko/](https://www.linkedin.com/in/kostyantyn-kovalenko/)
* Email: chvyaka.kk@gmail.com
* Telegram: @kovakost