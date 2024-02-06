# Lesson 001 Hello World

In this lesson we will write a classic "Hello World" program in TypeScript. This is tradition for all new programmers, or learning a new programming language, to write a "Hello World" program to print to the terminal "Hello World".

NOTE: Previsouly we were executing the commands we typed into the terminal when we pressed 'enter'. Editing code in Visual Studio Code is more like using Microsoft Word or Google Docs, the code is being edited and not _executed_ yet.

1. Open the project in VS Code `File -> Open Folder` then choose the `learn-typescript` project
2. On the lefthand side of VS Code there should be 5 icons, papers, magnifying glass, a weird branchy thing, a bug and a play button, and then building blocks. (If you hover over them they will tell you what they do including keyboard shortcuts!). Click on the papers to open the "Explorer", (it might already be open if it is selected.). This opens an explorer which shows all the files and directories in the opened project.
3. In the explorer you can find this lesson's file by opening `lessons/lesson-001/hello-world.md`. `.md` stands for Markdown, and its a file format that allows you to write in plain text but have it be rendered in the browser easily without writing HTML.
    * If you click the building blocks on the left you can install "Markdown All in One" extension and have it render the markdown inside of VS Code just like you see it in Github, talk to jbaldwin if you wish to try this for more detailed instructions.
4. Create a new file `hello-world.ts` inside the `lessons/lesson-001` directory. You can do this in VS Code by right clicking in the explorer the `lesson-001` directory and choosing the new file option. It should give you an inline text box in the explorer to type the name of the file and its extension. Hit enter to create it and then the VS Code editor should automatically open the newly created file.
5. What is a [Variable](https://en.wikipedia.org/wiki/Variable_(computer_science)) in programming? The wikipedia page is very exhaustive but a simple definition could be: "a variable is a named container for a particular set of bits or type of data".

6. Lets write out first piece of code, enter the following into your `hello-world.ts` editor, this piece of code is specific to `typescript` and we will defined each part below the code.

```typescript
let message = "Hello World";
```

Where `let` is a typescript [reserved keyword](https://en.wikipedia.org/wiki/Reserved_word) that tells the program you want to define a variable.

Where `message` is a name we get to pick, we could name this `msg` or `output` or anything we want, its the name of the variable we are creating.

Where `=` is not equality, but is the [assignment operator](https://en.wikipedia.org/wiki/Assignment_(computer_science)) and is telling the program to assign everything on the right hand side of the `=` to the variable we named `message`.

Where `"Hello World"` is a data type string and any characeters (letters or numbers) between the two quotes `"` is the data the string variable contains.

To break this down again this is a statment that assigns the string type to a new variable named message with the contents "Hello World".

7. Console is another name for terminal. Don't forget terminal is where we first started in [checkout repository](../../start/checkout-repository.md). Now we want to print the message to the terminal. In `typescript` there is a standard library object (this is a fancy way of saying it comes with the `typescript` language already builtin) named `console`. On the `console` object there are functions that allow us to print our variables to the screen. We'll learn about functions in more depth later, but for now a function takes arguments (typically variables) and executes code against those functions. Functions can be called many times with different arguments and run the same code with those different arguments each time. Effectively functions are a way to repeat executing the same code with different input. The function on the `console` object we want to call is `log`. To do this we will write out `console.log(message);`.  To break this down we are using the `console` object, which is inherit to typescript (included in its standard library) and then we are using the `.` operator to call `console`'s `log` function. To pass parameters to a function the typescript grammer says we start with `(` open parathesis, then we write the first variable, and then we close the parameter list with `)` closing parenthesis. As like the prior statement we wrote, we must finish the statement with a `;`.  Note: if you had a function that took multiplie arguments you would comma `,` separate them, e.g. it might look like: `foo(a, b, c)` for a function named `foo` that takes three parameters, `a`, `b`, and `c`.

    * Arguments: The function's defined input when you write the functions code, we'll learn how to do this later.
    * Parameters: When a function is called the instances of the arguments to the function, these are usually variables.

```typescript
let message = "Hello World";
console.log(message);
```

7. Now that we've written our code in Visual Studio Code it needs to be saved, just like a Word document you need to save, the short cut is the usual `control + s` when you have the file open or you can use the `File -> Save All` to save any and all documents open within Visual Studio Code quickly.
8. We now have a hello world program, but how do we run it? Open your terminal and navigate to the `lesson-001` directory within the project. If you need help refer to the [Checkout Repository](../../start/checkout-repository.md) for the terminal commands on how to navigate the directory structure.
9. To execute our code we will use `ts-node` which is the typescript (ts) node program. It understands how to read our code and execute it from the terminal. Node is a program that was originally created for javascript (js) and is usually referred to as `nodejs`. Type out `ts-node <typescript_file>` where `<typescript_file>` is the name of our code file, we named it `hello-world.ts` above in this lesson. `ts-node hello-world.ts` and then enter to execute your first typescript program.

```bash
joshr@GoobToob MINGW64 ~/repos/learn-typescript/lessons/lesson-001 (main)
$ ts-node hello-world.ts
Hello World
```

Congratulations you have written and run your first typescript Hello World program!

10. We've written our first important piece of code and we should commit it to our repository so we can track it in `git`. `git` is the source control program that we used to clone the repository locally, for now we will only create commits locally to learn how `git` works, Github that we clone the repo for can host a copy of our `git` repository, in later lessons we will learn how to do this. Start by navigating to the root of the repository, that should be `/c/Users/<user>/repos/learn-typescript` or `~/repos/learn-typescript`. Once there we can issue a series of `git` commands to stage the changed file(s) and then create a new commit on the repository to "save" our changes. If we make a mistake in the future we can always revert to any "save' we make in the repository.

Start by issuing the `git status` command. This tells `git` to report the current status of the files in the repository.

```bash
joshr@GoobToob MINGW64 ~/repos/learn-typescript (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        lessons/lesson-001/hello-world.ts

nothing added to commit but untracked files present (use "git add" to track)
```

The new file you created `lessons/lesson-001/hello-world.ts` should appear as an `untracked` file. That means `git` isn't tracking or saving the history of this file yet because its new. We can track it by issuing the `git add <file>` command. Lets do that now for our hello world program.

```bash
git add lessons/lesson-001/hello-world.ts
```

If you then issue the `git status` command again it changes to:

```bash
joshr@GoobToob MINGW64 ~/repos/learn-typescript (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   lessons/lesson-001/hello-world.ts
```

Before we commit our file into the repository we should issue a `git log` command to see all the commits in the repository, this isn't normally necessary, but to understand what we are committing we will look at the log before and after we make the commit.

```bash
joshr@GoobToob MINGW64 ~/repos/learn-typescript (main)
$ git log
commit 74b3add7bfb0a5f8d274dae813c234e97715ed47 (HEAD -> main)
Author: jbaldwin <email>@<hoster>
Date:   Mon Dec 18 14:11:20 2023 -0700

    Lesson 001

commit 1b6fc6f4c46756c07c0052920290a5febb6525f7 (origin/main, origin/HEAD)
Author: Josh Baldwin <email>@<hoster>
Date:   Mon Dec 18 11:27:24 2023 -0700

    Initial commit
```

At the time of writing this there are 2 commits in this learn typescript repository. The initial commit when I created the repo on Github and the Lesson 001 commit for this lesson. As more commits are added the log will grow. Each commit in this log is a snapshot of what the code looked like when that commit was made, and you can revert or go back in time to see what that code looked like with various git commands, these are more advanced and we'll learn about them later.


Since we put our file in the `stage` we can now commit it. `stage` is a special area where new files or edited files are 'staged' to be commited. It lets you pick and choose edited or new files to add into the commit. Quite often it is everything you edited, but sometimes it isn't and `stage` allows you to only add those certain files you want to include in the commit. Lets commit our hello world program to the repository, do that by issuing the command `git commit --message "Lesson 001 Hello World Program"`.

```bash
joshr@GoobToob MINGW64 ~/repos/learn-typescript (main)
$ git commit -m "Lesson 001 Hello World Program"
[main 0b116b0] Lesson 001 Hello World Program
 1 file changed, 2 insertions(+)
 create mode 100644 lessons/lesson-001/hello-world.ts
```

Now we can re-issue the `git log` command and see the newly created commit!

```bash
joshr@GoobToob MINGW64 ~/repos/learn-typescript (main)
$ git log
commit 0b116b0f491ed51a3fc52456bc0191c072f64d02 (HEAD -> main)
Author: jbaldwin <<email>@<hoster>>
Date:   Mon Dec 18 14:20:25 2023 -0700

    Lesson 001 Hello World Program

commit 74b3add7bfb0a5f8d274dae813c234e97715ed47
Author: jbaldwin <<email>@<hoster>>
Date:   Mon Dec 18 14:11:20 2023 -0700

    Lesson 001

commit 1b6fc6f4c46756c07c0052920290a5febb6525f7 (origin/main, origin/HEAD)
Author: jbaldwin <<email>@<hoster>>
Date:   Mon Dec 18 11:27:24 2023 -0700

    Initial commit

```

Congratulations! You've now written your first Hello World Typescript program and committed it to the repository for safe keeping!