# Learn Backend

- [Learn Backend](#learn-backend)
  - [Node | Running JavaScript on the server](#node--running-javascript-on-the-server)
  - [Express](#express)
    - [Why Express?](#why-express)
    - [How we use Express](#how-we-use-express)
    - [Express learning resources](#express-learning-resources)
  - [Drizzle](#drizzle)
    - [Drizzle ORM](#drizzle-orm)
    - [Drizzle Kit](#drizzle-kit)
    - [Drizzle Seed](#drizzle-seed)
    - [Why Drizzle?](#why-drizzle)
    - [How we use Drizzle](#how-we-use-drizzle)
    - [Drizzle learning resources](#drizzle-learning-resources)
  - [Zod](#zod)
    - [Why Zod?](#why-zod)
    - [How we use Zod](#how-we-use-zod)
    - [Zod learning resources](#zod-learning-resources)
  - [Testing](#testing)
    - [Node test runner](#node-test-runner)
    - [Node assert](#node-assert)
    - [Supertest](#supertest)
    - [Insomnia](#insomnia)
  - [API Documentation](#api-documentation)
    - [Swagger](#swagger)
    - [ZodOpenAPI](#zodopenapi)
    - [How to add OpenAPI specifications](#how-to-add-openapi-specifications)
      - [How to add a resource to the specification](#how-to-add-a-resource-to-the-specification)
      - [How to add a scema to the specification](#how-to-add-a-scema-to-the-specification)
  - [Appendix](#appendix)
    - [REST API](#rest-api)
    - [HTTP Requests](#http-requests)

## Node | Running JavaScript on the server

<https://www.theodinproject.com/paths/full-stack-javascript/courses/nodejs>

## Express

Express is a back end web application framework for building [REST APIs](#rest-api) with Node.

### Why Express?

We use Express because it is one of the most vidley used web application frameworks both in Node and in general.
It is easy to use and has a good amount of both official documentation and tutorials all availible online.

### How we use Express

We use Express to listen for requests to our server from the frontend. See:

- [src/main](https://github.com/vektorprogrammet/api/blob/main/src/main.ts)
- [src/routes](https://github.com/vektorprogrammet/api/tree/main/src/routers)

### Express learning resources

Wikipedia:

- english: <https://en.wikipedia.org/wiki/Express.js>
- norwegian: <https://no.wikipedia.org/wiki/Express.js>

Official documentation: <https://expressjs.com/>

Official sourcecode: <https://github.com/expressjs/express>

Official wiki: <https://github.com/expressjs/express/wiki>

NPM package: <https://www.npmjs.com/package/express>

## Drizzle

Drizzle ORM is a collection of database management and access tools.
The most promintent one is Drizzle ORM.
But there is also Drizzle Kit and Drizzle Seed.

### Drizzle ORM

Drizzle ORM is a object relational mapper (ORM) and is used to define and manage database schemas, and also allows you to acces the data in a SQL-like or relational way.

### Drizzle Kit

Drizzle Kit is a tool used to generate and run SQL migration files.
It also comes with Drizzle Studio, a database visualising and interaction tool.

### Drizzle Seed

Drizzle Seed is a TypeScript library that helps you generate deterministic, yet realistic, fake data to populate your database.
By leveraging a seedable pseudorandom number generator (pRNG), it ensures that the data you generate is consistent and reproducible across different runs.

### Why Drizzle?

We use drizzle because it gives us easy definitions of tables in our database, but doesn't abstract too much away from the actual database.
There is also a lot of good tools to make Drizzle fit with our other tools.

### How we use Drizzle

Drizzle is used all all over the place:

- table declaration ([db/tables](https://github.com/vektorprogrammet/api/tree/main/db/tables))
- database migration ([db/config](https://github.com/vektorprogrammet/api/blob/main/db/config/drizzle.config.ts))
- database access ([src/db-access](https://github.com/vektorprogrammet/api/blob/main/src/db-access))

### Drizzle learning resources

Drizzle ORM in 100 seconds: <https://www.youtube.com/watch?v=i_mAHOhpBSA>

Intro video to Drizzle: <https://www.youtube.com/watch?v=7-NZ0MlPpJA>

Drizzle Guides for common task: <https://orm.drizzle.team/docs/guides>

Official documentation: <https://orm.drizzle.team/docs/overview>

Officail sourcecode: <https://github.com/drizzle-team/drizzle-orm>

NPM packages:

- ORM: <https://www.npmjs.com/package/drizzle-orm>
- kit: <https://www.npmjs.com/package/drizzle-kit>
- seed: <https://www.npmjs.com/package/drizzle-seed>

## Zod

Zod is a schema declaration and validation library.
The term "schema" broadly refers to any data type, from a simple string to a complex nested object.

### Why Zod?

Typescript has a powerful and complex type system.
This fact might make you wonder why we would need Zod to validate our literals and objects.
Well, the fact is also that while Typescript has a powerful typesystem, it is built upon a language with no types. This often makes it hard to verify types at runtime, either because they originate from a pure-javascript module, or if your object is parsed from a string or similar.
Zod therefore introduces features for parsing objects and literals at runtime.
This is incredibly useful, becuase writing such code on your own can get incredibly convoluted.

To read more about the motivation for Zod and other Zod alternatives, see this blockpost by the creator: <https://colinhacks.com/essays/zod>

### How we use Zod

We use Zod to parse:

- API requests (see [src/requestparsing](https://github.com/vektorprogrammet/api/tree/main/src/response-handling))
  - url queries
  - parameters
  - json bodies
- database errors (see [db/errors](https://github.com/vektorprogrammet/api/tree/main/db/errors))
- enviromentvariables (see [src/enviroment](https://github.com/vektorprogrammet/api/blob/main/src/enviroment.ts) or [db/config/parameters](https://github.com/vektorprogrammet/api/blob/main/db/config/parameters.ts))

### Zod learning resources

Intro video to Zod: <https://www.youtube.com/watch?v=L6BE-U3oy80>

Some Zod exercises: <https://github.com/total-typescript/zod-tutorial>

Official documentation: <https://zod.dev/>

Official source code: <https://github.com/colinhacks/zod>

NPM package: <https://www.npmjs.com/package/zod>

## Testing

### [Node test runner](https://nodejs.org/docs/latest-v22.x/api/test.html)

Node testrunner is a built in Node module we use to run tests with.
It is important that you verify thar you use Node version 22 or higher, in order to make this module work as expected.

### [Node assert](https://nodejs.org/docs/latest-v22.x/api/assert.html)

Node assert is a built in Node library containing a set of functions for verifying correctedness in tests.

### [Supertest](https://www.npmjs.com/package/supertest)

Supertest is a HTTP testing tool, built on Superagent.
We use it to run different HTTP requests to our API in order to check that it returns the correct responses.

### [Insomnia](https://insomnia.rest/)

Insomnia is an open source desktop application used for interacting with and designing, debugging, and testing APIs. We use it to usertest that specific requests works as expected.

Official documentation: <https://docs.insomnia.rest/>
Download page: <https://insomnia.rest/download>

## API Documentation

### [Swagger](https://swagger.io/docs/specification/v3_0/about/)

Swagger is a set tools that easier to follow the OpenAPI specification.
We use the swagger-ui-express tool to host our openapi specification in our api itself.
We use the swagger-jsdoc NPM package to write openapi specifications in jsdoc comments directly in the code, to make the specifications easier to write and read, when you can look at the code in the same place.

### [ZodOpenAPI](https://www.npmjs.com/package/zod-openapi)

A tool used to transform our Zod scemas to schemas we can use in our OpenAPI specification.

### How to add OpenAPI specifications

#### How to add a resource to the specification

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

#### How to add a scema to the specification

In order to add a Zod schema to the OpenAPI specification, go to [the openapi configuration file](https://github.com/vektorprogrammet/api/blob/main/src/openapi/config.ts).
Under components you can add your schema. Remember that when you reference you scema in the specification, use the key assigned it with here.

## Appendix

### REST API

RESTful APIs in 100 seconds: <https://www.youtube.com/watch?v=-MTSQjw5DrM>

REST(REpresentational State Transfer) is a architecture style describing how a multimedia system exposed to the internet should behave.

A core principle in REST is that the client and server don't need to know what state the other is in.
This makes it easier to create reliable interfaces over the web.

A RESTful api requires the client to send HTTP-requests to the server

### HTTP Requests

HTTP request methods: <https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods>

Http requests consists of:

- a path to a resource
- an HTTP verb, which defines what kind of operation to perform
- a header, which allows the client to pass along information about the request
- an optional message body containing data

There are four basic HTTP request verbs: GET, POST, PUT and delete.
These corresponds to the four CRUD operations

Read more about the CRUD operations on Wikipedia:

- <https://en.wikipedia.org/wiki/Create,_read,_update_and_delete>
- <https://no.wikipedia.org/wiki/Opprett,_les,_oppdater_og_slett>
