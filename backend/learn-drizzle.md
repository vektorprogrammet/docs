# Learn Drizzle

## Table of contents

- [Learn Drizzle](#learn-drizzle)
  - [Table of contents](#table-of-contents)
  - [What is Drizzle?](#what-is-drizzle)
    - [Drizzle ORM](#drizzle-orm)
    - [Drizzle Kit](#drizzle-kit)
    - [Drizzle Seed](#drizzle-seed)
  - [Why Drizzle?](#why-drizzle)
  - [How we use Drizzle](#how-we-use-drizzle)
  - [Drizzle learning resources](#drizzle-learning-resources)

## What is Drizzle?

Drizzle ORM is a collection of database management and access tools. The most promintent one is Drizzle ORM. But there is also Drizzle Kit and Drizzle Seed.

### Drizzle ORM

Drizzle ORM is a object relational mapper (ORM) and is used to define and manage database schemas, and also allows you to acces the data in a SQL-like or relational way.

### Drizzle Kit

Drizzle Kit is a tool used to generate and run SQL migration files. It also comes with Drizzle Studio, a database visualising and interaction tool.

### Drizzle Seed

Drizzle Seed is a TypeScript library that helps you generate deterministic, yet realistic, fake data to populate your database. By leveraging a seedable pseudorandom number generator (pRNG), it ensures that the data you generate is consistent and reproducible across different runs.

## Why Drizzle?

We use drizzle because it gives us easy definitions of tables in our database, but doesn't abstract too much away from the actual database. There is also a lot of good tools to make Drizzle fit with our other tools.

## How we use Drizzle

Drizzle is used all all over the place:

- table declaration ([db/tables](https://github.com/vektorprogrammet/api/tree/main/db/tables))
- database migration ([db/config](https://github.com/vektorprogrammet/api/blob/main/db/config/drizzle.config.ts))
- database access ([src/db-access](https://github.com/vektorprogrammet/api/blob/main/src/db-access))

## Drizzle learning resources

Drizzle ORM in 100 seconds: <https://www.youtube.com/watch?v=i_mAHOhpBSA>
Intro video to Drizzle: <https://www.youtube.com/watch?v=7-NZ0MlPpJA>
Drizzle Guides for common task: <https://orm.drizzle.team/docs/guides>

Official documentation: <https://orm.drizzle.team/docs/overview>
Officail sourcecode: <https://github.com/drizzle-team/drizzle-orm>
NPM packages:

- ORM: <https://www.npmjs.com/package/drizzle-orm>
- kit: <https://www.npmjs.com/package/drizzle-kit>
- seed: <https://www.npmjs.com/package/drizzle-seed>
