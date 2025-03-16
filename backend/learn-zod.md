# Learn Zod

## Table of contents

- [Learn Zod](#learn-zod)
  - [Table of contents](#table-of-contents)
  - [What is Zod?](#what-is-zod)
  - [Why zod?](#why-zod)
  - [How we use Zod](#how-we-use-zod)
  - [Zod learning resources](#zod-learning-resources)

## What is Zod?

Zod is a schema declaration and validation library. The term "schema" broadly refers to any data type, from a simple string to a complex nested object.

## Why zod?

Typescript has a powerful and complex type system. This fact might make you wonder why we would need Zod to validate our literals and objects.
Well, the fact is also that while Typescript has a powerful typesystem, it is built upon a language with no types. This often makes it hard to verify types at runtime, either because they originate from a pure-javascript module, or if your object is parsed from a string or similar.
Zod therefore introduces features for parsing objects and literals at runtime. This is incredibly usefull, becuase writing such code on your own can get incredibly convoluted.

To read more about the motivation for zod and other zod alternatives, see this blockpost by the creator: <https://colinhacks.com/essays/zod>

## How we use Zod

We use zod to parse:

- API requests (see [src/requestparsing](https://github.com/vektorprogrammet/api/tree/main/src/response-handling))
  - url queries
  - parameters
  - json bodies
- database errors (see [db/errors](https://github.com/vektorprogrammet/api/tree/main/db/errors))
- enviromentvariables (see [src/enviroment](https://github.com/vektorprogrammet/api/blob/main/src/enviroment.ts) or [db/config/parameters](https://github.com/vektorprogrammet/api/blob/main/db/config/parameters.ts))

## Zod learning resources

Intro video to Zod: <https://www.youtube.com/watch?v=L6BE-U3oy80>
Some Zod exercises: <https://github.com/total-typescript/zod-tutorial>

Official documentation: <https://zod.dev/>
Official source code: <https://github.com/colinhacks/zod>
NPM package: <https://www.npmjs.com/package/zod>
