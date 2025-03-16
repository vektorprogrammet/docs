# Learn Express

- [Learn Express](#learn-express)
  - [What is Express?](#what-is-express)
    - [What are RESTful APIs?](#what-are-restful-apis)
    - [What are HTTP requests?](#what-are-http-requests)
  - [Why Express?](#why-express)
  - [How we use Express](#how-we-use-express)
  - [Express learning resources](#express-learning-resources)

## What is Express?

Express is a back end web application framework for building RESTful APIs with Node.js.

### What are RESTful APIs?

REST(REpresentational State Transfer) is a architecture style describing how a multimedia system exposed to the internet should behave.

A core principle in REST is that the client and server don't need to know what state the other is in.
This makes it easier to create reliable interfaces over the web.

A RESTful api requires the client to send HTTP-requests to the server

### What are HTTP requests?

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

## Why Express?

We use Express because it is one of the most vidley used web application frameworks both in Node and in general.
It is easy to use and has a good amount of both official documentation and tutorials all availible online.

## How we use Express

We use Express to listen for requests to our server from the frontend. See:

- [src/main](https://github.com/vektorprogrammet/api/blob/main/src/main.ts)
- [src/routes](https://github.com/vektorprogrammet/api/tree/main/src/routers)

## Express learning resources

RESTful APIs in 100 seconds: <https://www.youtube.com/watch?v=-MTSQjw5DrM>

HTTP request methods: <https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods>

Wikipedia:

- english: <https://en.wikipedia.org/wiki/Express.js>
- norwegian: <https://no.wikipedia.org/wiki/Express.js>

Official documentation: <https://expressjs.com/>

Official sourcecode: <https://github.com/expressjs/express>

Official wiki: <https://github.com/expressjs/express/wiki>

NPM package: <https://www.npmjs.com/package/express>
