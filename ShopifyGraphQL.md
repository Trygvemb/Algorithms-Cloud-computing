---
title : "Shopify GraphQL API Testing"
---

## Resources

- [Introduction video](https://www.youtube.com/watch?v=Q68EXTH08vI)
- [Shopify GraphQL API Documentation](https://shopify.dev/docs/admin-api/graphql/reference)

## Learning Objectives

- **Knowledge**
  - Understanding the basics of GraphQL and how it differs from REST.
  - Understanding the structure of the Shopify GraphQL API.
  - Understanding how to authenticate and make requests to the Shopify GraphQL API.
  - Understanding how to test the Shopify GraphQL API (maybe using Postman.)

- **Skills**
  - **Set up a Shopify development store and generate API credentials.**
  - Write queries and mutations to interact with the Shopify GraphQL API.
  - Analyze the responses from the Shopify GraphQL API and handle errors.
  - Use variables and fragments in GraphQL queries.

- **Competencies**
  - Identify and define test cases for the Shopify GraphQL API.
  - Evaluate the responses from the Shopify GraphQL API and verify the correctness of the data.
  - Learn and apply new features of the Shopify GraphQL API when required by complex tasks.

## Quality Criteria

- Have a fully functional Shopify development store.
- Write at least 5 queries and 5 mutations to interact with the Shopify GraphQL API.
- Successfully authenticate and make requests to the Shopify GraphQL API.
- Write test cases for at least 3 different scenarios and evaluate the responses.

## Getting Started

1. **Set up a Shopify development store**
   - Go to [Shopify Partner](https://www.shopify.com/partners) and create a Partner account.
   - Create a development store from the Partner Dashboard.

2. **Set up GraphQL Admin API reference**
   - in terminal, run the following command to install the Shopify App CLI:

   ``` bash
   npm install --save @shopify/shopify-app-remix
   ```

3. **Set up local project**
   - Create a new project folder and initialize Shopify App CLI by running

   ``` bash
    npm init@shopify/app@latest
   ```

   - Follow the prompts to set up the project.
