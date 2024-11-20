# docs

## Code style handbook

Javascript is a multi-paradigm language which gives the users full freedom over how to write their code.\
This is a very double-edged sword within teams.\
That is why we have written this handbook to standardise our practices and provide a place for members to look up what to do if they are confused.

### Modular programming | Programming paradigm

We try to make our code as modular as possible as it is the most maintainable programming paradigm and most idiomatic for Javascript.

[Modular Programming | How to write good procedural code - YouTube](https://www.youtube.com/watch?v=0iyB0_qPvWk)

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

#### Logic modules

Logic modules should **not** contain global mutable variables.

Logic modules should contain:

- constant values
- types
- pure functions
- function closures (instead of classes) [Write closures, not classes](#write-closures-not-classes)

#### State modules

`main` is **always** a state module.

Within a web project, routes and pages are (basically) the only state modules.

#### Create modular programs by reducing state modules and maximising logic modules

#### Optimistically favor pure functions

<!-- Called out by linter -->

### Variable declaration

#### Never use `var`. Default to `const`. Use `let` if reassignment is needed

Using `var` for variable declarations is widely accepted as bad practice.

`var` is bound to function scope while `let` and `const` are bound to block scope.\
This leads to confusing and unintuitive behavior.

TODO: Give some examples

### Always use triple equals `===` over double equals `==`

### `async` `await` or promises?

Use whichever syntax makes the code more readable.

Only exception is if it affects performance like processing multiple asynchronous operations in parallel instead of sequentially.

Whats more important than having a steadfast rule to stand by is to understand how async await and promise work.\
What operations are essentially equivalent and what operations execute differently.

[Async await vs promises - StackOverflow](https://stackoverflow.com/questions/53057110/difference-of-using-async-await-vs-promises)

### Write closures, not classes
<!-- Not called out by linter -->
> Why not write classes?

Writing function closures instead of classes is more representative of what happens under the hood.

Function closures also has the benefit of avoiding the extremely confusing `this` keyword in Javascript and instead just reference variables directly.

[Closures vs classes - StackOverflow](https://stackoverflow.com/questions/71670779/closures-vs-classes-in-modern-javascript)
