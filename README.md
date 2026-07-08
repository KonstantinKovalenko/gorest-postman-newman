# GoREST API Testing with Postman & Newman

API automation project built with Postman and Newman using the GoREST public API.

## Tech Stack

* Postman
* Newman
* Newman HTML Extra Reporter
* Node.js
* GitHub Actions

## Project Structure

```
collection/
environment/
reports/
package.json
README.md
```

## Prerequisites

* Node.js 18+
* npm

## Installation

```bash
npm install
```

## Run Tests

Execute the Postman collection:

```bash
npm run newman
```

Generate an HTML report:

```bash
npm run report
```

Remove generated reports:

```bash
npm run clean
```

## Test Coverage

The collection includes automated tests for:

* Create User
* Get User by ID
* Update User
* Partial Update User
* Delete User
* Negative Get User by ID
* Get All Users with pagination and filtering

Validation includes:

* Status codes
* Response time
* JSON schema validation
* Business logic validation
* Pagination
* Filtering
* Content-Type validation

## CI/CD

The collection is executed automatically using GitHub Actions, and the HTML report is published to GitHub Pages.
