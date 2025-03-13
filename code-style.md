# Code style guide

- [Code style guide](#code-style-guide)
  - [Intro](#intro)
  - [General philosophy](#general-philosophy)
    - [Prioritise readability over performance](#prioritise-readability-over-performance)
    - [Use modular programming | Programming Paradigm](#use-modular-programming--programming-paradigm)
      - [Why not Object-Oriented Programming(OOP)?](#why-not-object-oriented-programmingoop)
      - [Minimise state modules, maximise logic modules](#minimise-state-modules-maximise-logic-modules)
      - [Logic modules should not contain global mutable variables](#logic-modules-should-not-contain-global-mutable-variables)
      - [`main` is always a state module](#main-is-always-a-state-module)
    - [The only state our web server should depend on is the state of our database.](#the-only-state-our-web-server-should-depend-on-is-the-state-of-our-database)
    - [Optimistically favor pure functions](#optimistically-favor-pure-functions)
  - [JavaScript / TypeScript](#javascript--typescript)
    - [Never use `var`. Always use `const` or `let` if reassignment is needed | Variable declaration](#never-use-var-always-use-const-or-let-if-reassignment-is-needed--variable-declaration)
    - [Always use triple equals `===` over double equals `==` | Equality Checks](#always-use-triple-equals--over-double-equals---equality-checks)
    - [`async` `await` or promises? | Asynchronous operations](#async-await-or-promises--asynchronous-operations)
    - [Write closures, not classes | Data Encapsulation](#write-closures-not-classes--data-encapsulation)
  - [React](#react)
    - [Type `children` prop with ReactNode](#type-children-prop-with-reactnode)
  - [Writing style guide](#writing-style-guide)
    - [Keep it precise and concise](#keep-it-precise-and-concise)
    - [Headings containing subheadings should usually tell us what subject or category the subheadings are about.](#headings-containing-subheadings-should-usually-tell-us-what-subject-or-category-the-subheadings-are-about)
    - [Subheadings should be written in imperative commands, like git commits](#subheadings-should-be-written-in-imperative-commands-like-git-commits)

## Intro

JavaScript/TypeScript (JS/TS) is a multi-paradigm language which gives the users full freedom over how to write their code.\
This is a very double-edged sword within teams.\
That is why we have written this handbook to standardise our practices and provide a place for members to look up what to do if they are confused.

**How to read this guide**

If you just want to learn our rules/guidelines and don't care for the explanations,
take a quick look at the outline/headers.

In the headers we try to summarise the points into quick imperative commands,
then articulate **why** in the body of the section.\
Optionally, a category name is added to clearly categorise what topic we are talking about.

## General philosophy

### Prioritise readability over performance

TODO: make this section better, add examples of good times to optimise f. eks.

While performance is important, most optimisations are brilliantly automated by engineers far better than ourselves.\
Trying to optimise our code most often reduces readability both for our team members,
and for the compiler tasked with optimising our code.\
Mind you, this doesn't mean write shit code.\
What it means is don't try to be cute,\
Keep It Simple Stupid (KISS).

### Use modular programming | Programming Paradigm

We try to make our code as modular as possible as it is the most maintainable programming paradigm and most idiomatic for Javascript.

[Modular Programming | How to write good procedural code - YouTube, Brian Will](https://www.youtube.com/watch?v=0iyB0_qPvWk)

[Difference between modular programming and object-oriented programming - StackOverflow](https://stackoverflow.com/questions/18034683/what-is-the-big-difference-between-modular-and-object-oriented-programming)

<!--
In the end, paradigms are tools for solving the problem of writing programs.\
This requires understanding the problem you are trying to solve and using the best possible solution.\
**Most** programs is about transforming data from one shape to another.\
So emulating that behavior in the structure of our code is most beneficial
-->

#### Why not Object-Oriented Programming(OOP)?

Because it sucks and makes it even harder to maintain a codebase (its hard enough to use Javascript in a team).

If you want to learn more about why OOP sucks I highly recommend this video by Brian Will,
which might ironically make you better at writing good OOP code for when you inevitably get a corporate job.

[Object-Oriented Programming is Bad - YouTube, Brian Wil](https://youtu.be/QM1iUe6IofM)

TODO: Write something about how to write good functional good for logic modules

#### Minimise state modules, maximise logic modules

In JS/TS

#### Logic modules should not contain global mutable variables

Logic modules should contain:

- constant values
- types
- pure functions
- function closures (instead of classes) [Write closures, not classes](#write-closures-not-classes)

#### `main` is always a state module

Within a web project, routes and pages should be the only state modules.

### The only state our web server should depend on is the state of our database.

### Optimistically favor pure functions

Pure functions are functions where the output only differ if its input differ.\
This means calling the functions repeatedly with the same arguments should **always** return the same results.

This lets us rewrite the entire workings of the inner function body,
as long as we make sure the output stays the same.\
This drastically improves predictability which also makes the codebase easier to maintain.

<!-- Called out by linter -->

## JavaScript / TypeScript

### Never use `var`. Always use `const` or `let` if reassignment is needed | Variable declaration

Using `var` for variable declarations is widely accepted as bad practice.

`var` is bound to function scope while `let` and `const` are bound to block scope.\
This leads to confusing and unintuitive behavior.

TODO: Give some examples

### Always use triple equals `===` over double equals `==` | Equality Checks

### `async` `await` or promises? | Asynchronous operations

Use whichever syntax makes the code more readable.

Only exception is if it affects performance like processing multiple asynchronous operations in parallel instead of sequentially.

Whats more important than having a steadfast rule to stand by is to understand how async await and promise work.\
What operations are essentially equivalent and what operations execute differently.

[Async await vs promises - StackOverflow](https://stackoverflow.com/questions/53057110/difference-of-using-async-await-vs-promises)

### Write closures, not classes | Data Encapsulation
<!-- Not called out by linter -->
> Why not write classes?

Writing function closures instead of classes is more representative of what happens under the hood.

Function closures also has the benefit of avoiding the extremely confusing `this` keyword in JS/TS and instead just reference variables directly.

[Closures vs classes - StackOverflow](https://stackoverflow.com/questions/71670779/closures-vs-classes-in-modern-javascript)

## React

[Essential Typescript for React - Blogpost, Jacob Paris](https://www.jacobparis.com/content/react-ts)

### Type `children` prop with ReactNode

## Writing style guide

### Keep it precise and concise

We are not writing a book.\
We are writing a guide one should be able to skim through and get the gist of it.

### Headings containing subheadings should usually tell us what subject or category the subheadings are about.

### Subheadings should be written in imperative commands, like git commits
