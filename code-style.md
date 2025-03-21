# Code style guide

VektorIT's code style which cannot be enforced using linters or formatters.

- [Code style guide](#code-style-guide)
  - [Principles](#principles)
    - [Readability is priority number one](#readability-is-priority-number-one)
    - [Follow established conventions, only break them for VERY good reasons](#follow-established-conventions-only-break-them-for-very-good-reasons)
    - [Minimise scope when possible](#minimise-scope-when-possible)
  - [Organising your projects](#organising-your-projects)
    - [Prefer long files over many smaller files](#prefer-long-files-over-many-smaller-files)
    - [Avoid folders unless they enhance readability](#avoid-folders-unless-they-enhance-readability)
    - [Prefer co-location over categorisation / separation of concerns](#prefer-co-location-over-categorisation--separation-of-concerns)
  - [TypeScript](#typescript)
    - [Write pure functions when possible](#write-pure-functions-when-possible)
    - [Explicitly declare function return types, except for React components](#explicitly-declare-function-return-types-except-for-react-components)
    - [Variable names are camelCase](#variable-names-are-camelcase)
    - [Type names are PascalCase](#type-names-are-pascalcase)
  - [React](#react)
    - [Follow the Rules of React](#follow-the-rules-of-react)
    - [Component names are PascalCased](#component-names-are-pascalcased)
    - [Declare named functions over anonymous functions](#declare-named-functions-over-anonymous-functions)
    - [ReactNode or ReactElement?](#reactnode-or-reactelement)

## Principles

### Readability is priority number one

The computer can read extremely ugly code and still know what to do.\
Humans (and LLMs) have a way harder time reading code than compilers.\
So we make sure we write code which can be understood by people,\
which keeps the projects easy to maintain.

### Follow established conventions, only break them for VERY good reasons

Helps with readability for both humans and LLMs.

### Minimise scope when possible

Scope is about where variables are accessible.
By minimising it, we reduce the amount of variables one needs to keep in their head as they are reading it.

## Organising your projects

This section focuses on how to structure files and folders.

### Prefer long files over many smaller files

If one features is organized into multiple components,
keep the components within the same file until another file needs to import it.

By not exporting variables immaturely,
we minimise the variables' scope without adding restrictions or unnecessary folders.

### Avoid folders unless they enhance readability

### Prefer co-location over categorisation / separation of concerns

Instead of grouping files by categories easily readable for computers,
group them by their relation to other files for better human readability.

Don't do this:

- `/`
  - `/html`
    - `index.html`
    - `profile.html`
    - `sign-in.html`
    - `sign-out.html`
  - `/css`
    - `index.css`
    - `profile.css`
    - `sign-in.css`
    - `sign-out.css`
    - `layout.css`
  - `/js`
    - `index.js`
    - `profile.js`
    - `auth.js`
    - `utils.js`

Do this instead:

- `/`
  - `/features`
    - `/auth`
      - `auth.js`
      - `/sign-in`
        - `sign-in.html`
        - `sign-in.css`
      - `/sign-out`
        - `sign-out.html`
        - `sign-out.css`
  - `/pages`
    - `layout.css`
    - `/index`
      - `index.html`
      - `index.css`
      - `index.js`
    - `/profile`
      - `profile.html`
      - `profile.css`
  - `/lib`
    - `utils.js`

From the structure alone, we can infer that

- `auth.js` is only used within the `/auth` folder
- `layout.css` is only used within the `/pages` folder
- `/lib` and `/features`s contents are accessible within the whole repository, as they are placed at the root level of the repository

Files and folders are assumed to have access to files and folders within the same directory/folder.\
You can imagine that the scope of files cascades down subfolders like a waterfall.

Better to spend extra time thinking about organisation and how the code relates to other code instead of slapping it into a folder letting it rot until some other poor soul has to decipher what files relates to what.

## TypeScript

### Write pure functions when possible

A pure function is one where the result only depends on its arguments.

This is not a pure function as the mutable variable `amount` could change and affect the result of the `add` function

```ts
let amount = 5;
function add(a: number) {
  return a + amount;
}
add(2);
```

Here is an example of how to rewrite `add` as a pure function

```ts
let amount = 5;
function add(a: number, b:number) {
  return a + b;
}
add(2, 5);
```

### Explicitly declare function return types, except for React components

This makes it easy to understand the function type at a glance.

It also helps make sure functions return what they're supposed to,
and if the return type changes,
your code editor can point you to its occurrences which need to be updated.

```diff
- function add(a: number, b: number) {
+ function add(a: number, b: number): string
  return `${a}${b}`
}
```

We make an exception for React components as they are the only functions written with PascalCase.

```diff
- function Component(): JSX {
+ function Component() {
  ...
}
```

### Variable names are camelCase

By JavaScript convention.

### Type names are PascalCase

By JavaScript and general convention.

## React

[Essential Typescript for React - Blogpost, Jacob Paris](https://www.jacobparis.com/content/react-ts)

### Follow the Rules of React

<https://react.dev/reference/rules>

By following these you will implicitly write code in a functional style

If you want to learn more about functional programming ask @phibkro.

### Component names are PascalCased

```diff
- function my_component() {
+ function MyComponent() {
  ...
}
```

### Declare named functions over anonymous functions

Make sure you understand that functions in JavaScript are [hoisted](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_hoisting)

```diff
- const myFunction = () => {
+ function myFunction() {
  ...
}
```


### ReactNode or ReactElement?

<https://stackoverflow.com/questions/58123398/when-to-use-jsx-element-vs-reactnode-vs-reactelement>
