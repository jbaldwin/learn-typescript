# Install Toolchains

There are some custom settings we'll want per package, walkthrough with `jbaldwin`.

1. Install [VS Code](https://code.visualstudio.com/Download)
2. Install [Git for Windows](https://git-scm.com/download/win)
3. Install [nodejs](https://nodejs.org/en/download)
4. Install typescript
   1. Open `Git Bash`
   2. In the terminal execute `npm install -g typescript`
      * This comman runs the `npm` (node package manager) and `install`'s `-g` (global) the `typescript` package.
   1. In the terminal execute `npm install -g ts-node`
      * This installs a version of `nodejs` that executes typescript directly.
      * We will be using `ts-node` to run the programs that we write.
5. Setup git config
   * NOTE: it is standard anytime a commands arguments that have a parameter surrounded by `<` and `>` that you need to replace that argument _including_ the angled `<>` brackets. For example in the next step you'll see `<you@example.com>`, that means you should replace the entire `<you@example>` including the `<` and `>` to your email address, e.g. `git config --global user.email foo@bar.com`.
   1. In the terminal execute ` git config --global user.email <you@example.com>` but replace the email with your email address.
   2. In the terminal execute `git config --global user.name <Your Name>` and again replace Your Name with.. your name!
   3. This is necessary to be able to commit code to the repository, anytime you install `git` these variables need to be setup.