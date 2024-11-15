# Cypress API and UI Tests
Hello and Welcome! This project contains automated tests using Cypress, including an API test for electronic products and a UI test to sort products on the SauceDemo website.

## Installation

Ensure you have the following software installed:

. Node.js

. Cypress (installed via npm)

1. Clone the repository by downloading and unzipping the compressed file to your local hard drive
2. On VS Code (or other TDE of your choice), select the Folder "Projeto CY1"

## Running Tests Locally
To run tests using the cyperss interface, type on the terminal:

```python
npx cypress open
```
To run tests in headless mode:
```python
npx cypress run
```
## Test Cases Scenarios
. API Test (API Testing): The Electronics Filter test makes a request to https://fakestoreapi.com/products, filters products in the "electronics" category, and validates that there are at least five electronic products available.

.UI Test (Sauce Demo Login): The Sort Products test logs into the SauceDemo website, changes the product order to "Name (Z to A)," and validates that the first displayed item is Test.allTheThings() T-Shirt (Red).

## Extra Notes

During the making of the Sauce Demo Login test, i stumble upon an error that Cypress got stuck at cy.visit() and couldn't load the page properly.
I've found a page on github with some users reporting the same issue and presented several solutions to that. Link can be found [here](https://github.com/cypress-io/cypress/issues/27501).

Problem was solved by including this line of code on the cypress.config.js file:
```python
blockHosts: [ "www.googletagmanager.com", "analytics.google.com", "www.google-analytics.com" ],
    specPattern: "cypress/e2e/**/*.{cy,spec}.{js,ts}",
    watchForFileChanges: false,
    chromeWebSecurity: false,
    blockHosts: ["https://events.backtrace.io"],
```
