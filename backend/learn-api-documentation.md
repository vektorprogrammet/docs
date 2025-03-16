# Learn API documentation

## Table of contents

- [Learn API documentation](#learn-api-documentation)
  - [Table of contents](#table-of-contents)
  - [Tools](#tools)
    - [Swagger](#swagger)
    - [ZodOpenAPI](#zodopenapi)
  - [How to add OpenAPI specifications](#how-to-add-openapi-specifications)
    - [How to add a resource to the specification](#how-to-add-a-resource-to-the-specification)
    - [How to add a scema to the specification](#how-to-add-a-scema-to-the-specification)

## Tools

### [Swagger](https://swagger.io/docs/specification/v3_0/about/)

Swagger is a set tools that easier to follow the OpenAPI specification.
We use the swagger-ui-express tool to host our openapi specification in our api itself.
We use the swagger-jsdoc NPM package to write openapi specifications in jsdoc comments directly in the code, to make the specifications easier to write and read, when you can look at the code in the same place.

### [ZodOpenAPI](https://www.npmjs.com/package/zod-openapi)

A tool used to transform our Zod scemas to schemas we can use in our OpenAPI specification.

## How to add OpenAPI specifications

### How to add a resource to the specification

To add an addition to the OpenAPI specification, you need to add a comment following this format:

```yaml
/**
 * @openapi
 * /path/to/your/resource:
 *  (http verb here):
 *   tags: [some, tags, in, here]
 *   summary: "Here goes the summary"
 *   description: "And here the description"
 *   parameters:
 *    - $ref: "#/components/parameters/yourParameterHere"
 *   requestBody:
 *    required: true
 *    content:
 *     json:
 *      schema:
 *       $ref: "#/components/schemas/yourRequestScema"
 *   responses:
 *    (response code here):
 *     description: "Description of your response
 *     content:
 *      application/json:
 *       schema:
 *        $ref: "#/components/schemas/yourReturnScema"
 */
```

### How to add a scema to the specification

In order to add a Zod schema to the OpenAPI specification, go to [the openapi configuration file](https://github.com/vektorprogrammet/api/blob/main/src/openapi/config.ts).
Under components you can add your schema. Remember that when you reference you scema in the specification, use the key assigned it with here.
