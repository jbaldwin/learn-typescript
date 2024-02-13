# Lesson 002 Primitive Types

In this lesson we will learn about all the [primitive types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html) in TypeScript and print them to the terminal.

Whats a primitive type? It is a type that is built into the language and is always available to use. In [lesson-001](../lesson-001/hello-world.md) we used the `string` primitive type to print `"Hello World"` to the terminal.

Setup: In this lesson we'll use the terminal to create the directory structure and make the `typescript` file that we'll then edit in VS Code.

1. Open `Git Bash`
2. Navigate to `~/repos/learn-typescript/lessons/lesson-002`
   1. Reference the [Checkout Repository](../../start/checkout-repository.md) for help in changing directories in the terminal.
   2. Next steps note: you can pass the entire path to the `cd` command to navigate there in one execution, e.g.:
      1. `cd ~/repos/learn-typescript/lessons/lesson-002`

New command: `touch`. The `touch` command will "touch" or create a new empty file that we can then use in VS Code.

3. Run `touch primitive-types.ts` in the terminal. If you then execute `ls` from the terminal you should see the newly created file.
4. Open VS Code
5. Open the project in VS Code `File -> Open Folder` then choose the `learn-typescript` project.
6. On the lefthand side click the `Explorer` tab and then open the newly created `lesson/lesson-002/primitive-types.ts` file that you created from the terminal.

## Boolean

The `boolean` type is named after [George Boole](https://en.wikipedia.org/wiki/George_Boole), he is known for creating [boolean algebra](https://en.wikipedia.org/wiki/Boolean_algebra) which the `boolean` primitive type is based on.

The `boolean` type is either `true` or `false`, nothing else.

In the VS Code editor for the `primitive-types.ts` file you created earlier lets create two boolean types and print their values to the terminal. We'll also print the `true` `false`.

```typescript
let b1: boolean = true;
let b2: boolean = false;

console.log(b1);
console.log(b2);
console.log(true);
console.log(false);
```

Lets execute the `primitive-types.ts` program that you just wrote for the `boolean` types.

1. Switch to `git bash` with the `~/repos/learn-typescript/lessons/lesson-002` directory open from earlier in the lesson.
2. Execute the program with `ts-node primitive-types.ts`.

Expected output:

```bash
$ ts-node primitive-types.ts
true
false
true
false
```

## Number

The `number` type is for numbers like `42` or `3.14`. Typescript only has `number`'s where other programming languages differentiate between an `integer` (a number that is not a fraction, a whole number) and `float` (a computer science term for a number with a fraction amount, not a whole number).

In the VS Code editor for the `primitive-types.ts` file lets add some additional code below the `boolean` code that you previously wrote.

```typescript
let n1: number = 42;
let n2: number = 3.14;
let n3 = 1337;

console.log(n1);
console.log(n2);
console.log(n3);
console.log(1234);
console.log(0.9876);
```

*Note*: `n3` doesn't explicitly declare its type, it is _inferred_ by `typescript`. In general you can omit types as long as the `typescript` compiler can infer it, but if it cannot infer the type based on the context then you must annotate the type, via `: <type>` where `<type>` is the type of the object, in this case `number`.

Lets execute the `primitive-types.ts` program that you just wrote for the `number` types.

1. Switch to `git bash` with the `~/repos/learn-typescript/lessons/lesson-002` directory open from earlier in the lesson.
2. Execute the program with `ts-node primitive-types.ts`.

Expected output: (includes boolean output too!)

```bash
$ ts-node primitive-types.ts
true
false
true
false
42
3.14
1337
1234
0.9876
```

## String

A `string` is a set of zero or more characters (a character is a single letter of `a` to `z` or `A` to `Z` or `0` to `9`, or any other character you can type on your keyboard)

There are two types of strings, a `string` literal and an interpolated `string`. We'll cover both.

### String Literal

A string literal is a string that as you see it is what it is. To create a `string` literal we will use double quotes `""` to encapsulate the characters that make up the string.

In the VS Code editor for the `primitive-types.ts` file lets add some additional code below the `boolean` and `number` code that you previously wrote.

```typescript
let s1 = "Hello World";
let s2 = "";
let s3 = "1234";

console.log(s1);
console.log(s2);
console.log(s3);
```

1. Switch to `git bash` with the `~/repos/learn-typescript/lessons/lesson-002` directory open from earlier in the lesson.
2. Execute the program with `ts-node primitive-types.ts`.

Expected output:

```bash
$ ts-node primitive-types.ts
true
false
true
false
42
3.14
1337
1234
0.9876
Hello World

1234
```

Notice that `s2` is an "empty" string, it has no characters, so it prints out nothing.

Notice that s3 is a _number_ but is a set of characters in a `string`. It is important to understand that a `string` that consists of numbers is not identical to a `number`, e.g. `"1234"` is not the same as `1234` since one is a `string` representing 1234 where `1234` is a `number` that has the value of 1234.

### Interpolated String

An interpolated `string` uses  \`\` tick marks instead of the double quotes `""` to denote that the string is interpolated. Within an interpolated `string` you can include references to variables to "stringify" the variable into the string. To reference a variable within an interpolated `string` you start with a `$` dollar sign and then use the brackets `{}` with the variables name between the brackets to reference the variable you want to include in the string. Lets try an example.

In the VS Code editor for the `primitive-types.ts` file lets add some additional code below the `boolean` and `number` code that you previously wrote.

```typescript
let h = "Hello";
let w = "World";
let hi = `${h} I'm interpolated`;
let wi = `${w} I am also!`;
let hw = `${hi} ${wi}!`;

console.log(h);
console.log(w);
console.log(hi);
console.log(wi);
console.log(hw);
````

1. Switch to `git bash` with the `~/repos/learn-typescript/lessons/lesson-002` directory open from earlier in the lesson.
2. Execute the program with `ts-node primitive-types.ts`.

Expected output:

```bash
$ ts-node primitive-types.ts
true
false
true
false
42
3.14
1337
1234
0.9876
Hello World

1234
Hello
World
Hello I'm interpolated
World I am also!
Hello I'm interpolated World I am also!!
```

## Arrays

An `array` is a container of a specific type that can contain zero or more of that type. An array is ordered from `0` to `n` where `n` is the total number of items contained by the `array`.

In the VS Code editor for the `primitive-types.ts` file lets add some additional code below the `boolean` and `number` code that you previously wrote.

To define an `array` use the other brackets `[]` with the values it contains inside the brackets and each item separated by a comma `,`.

```typescript
let a1: number[] = [1, 2, 3, 4, 5];
let a2: number[] = [];
let a3 = [true, false, true];
let a4 = ["Hello", "World"];

let hello = "Hello";
let world = "World";
let a5 = [hello, world, "from variables"];

console.log(a1);
console.log(a2);
console.log(a3);
console.log(a4);
console.log(a5);
```

1. Switch to `git bash` with the `~/repos/learn-typescript/lessons/lesson-002` directory open from earlier in the lesson.
2. Execute the program with `ts-node primitive-types.ts`.

Expected output:

```bash
$ ts-node primitive-types.ts
true
false
true
false
42
3.14
1337
1234
0.9876
Hello World

1234
Hello
World
Hello I'm interpolated
World I am also!
Hello I'm interpolated World I am also!!
[ 1, 2, 3, 4, 5 ]
[]
[ true, false, true ]
[ 'Hello', 'World' ]
[ 'Hello', 'World', 'from variables' ]
```

Note that because `a2` does not contain any values the `typescript` compiler cannot infer the type of items that the `array` contains and thus you must include the full type for it to work.

## Commit your new code!

From [lesson-001](../lesson-001/hello-world.md) in step 10 you learned how to commit your newly created code. Follow these steps again but for the new `primitive-types.ts` code you wrote to finish up this lesson.
