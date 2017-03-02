> Variable scope in TypeScript
> There are a lot of ways to define variables in TypeScript. In this lesson we discuss variable scope which determines all the places where a particular variable can be used.

When you use parenthesis in TypeScript it creates a block.

```js
{

}
```
You can define a variable in TypeScript using `var`, `let`, `const`, `function`, `class`, `namespace`, `enum`.

```js
{
  var foo = 123;
  let bar = 123;
  const baz = 123;
  function qux() {}
  class Dave {}
  namespace Matt {}
}
```

`var` is something that should be considered legacy and not used in any new code base. Unlike other variables, `var` is *function* scoped. A block has no impact on a var. This can be demonstrated when you try to use the `var` outside the block. 

```js
{
  var foo = 123; 
  let bar = 123;
  const baz = 123;
  function qux() {}
  class Dave {}
  namespace Matt {}
}
console.log(foo); // OKAY!
```

Everything else is constrained by the block and TypeScript will point that out for you.

```js
{
  var foo = 123; 
  let bar = 123;
  const baz = 123;
  function qux() {}
  class Dave {}
  namespace Matt {}
}
console.log(foo, bar, baz, qux, Dave, Matt); // ERRORS
```
For this reason you should *never* use `var` in new code. Lets consider a few cases that resuult in a scope naturally (`if`,`else`,`for`,`

TODO: mention creating a scope in switch. 