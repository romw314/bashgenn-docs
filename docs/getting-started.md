# Getting started with Bashgenn

## Installation

First of all, we want to install RBGN, the interpreter of Bashgenn. To install RBGN, [install Rust](https://rustup.rs){:target=blank} and then run this command (works cross-platform):

```sh
cargo install rbgn
```

## Hello, World!

Create a file named `hello_world.bgn` and open it in your favorite editor. We do it in Nano:

```sh
nano hello_world.bgn
```

Put this contents into the file:

```
- Lines starting with a hyphen (-) are comments in Bashgenn.
- Please note that you can't place a comment after a command.
- You need to add comments to separate lines

- This sets the `hello` variable to `Hello, World`.
STATIC_STR_VAR hello Hello, World!

- This writes the contents of the `hello` variable to the standard output.
ECHO hello
```

Save the file. In Nano, you can save and close the file by pressing `Ctrl+X`, `Y` and then `Enter`. Then, run the script using this command:

```sh
rbgn -i hello_world.bgn
```

It will print `Hello, World!` to the output.

## Practice 1 - Hello, Bashgenn!

Now, create a program that prints `Hello, Bashgenn!` to the output.

<details><summary>Click to expand the solution</summary>
```
STATIC_STR_VAR hello_bg Hello, Bashgenn!
ECHO hello_bg
```
</details>

## Reading input

We can also read input and write it to the output:

```
- READ reads one line of input into a variable
READ my_variable
ECHO my_variable
```

We can also read two lines of input and write them:

```
READ my_variable
ECHO my_variable
READ your_variable
ECHO your_variable
```

## Practice 2 - Reversing lines

Now, create a program that reads two lines of input and writes them in reversed order.

<details><summary>Click to expand the solution</summary>
```
READ my_variable
READ your_variable
ECHO your_variable
ECHO my_variable
```
</details>

## Moving characters

To write the last character from a variable, use the `LAST` command (this also removes the character from the variable):

```
STATIC_STR_VAR hello Hello, World!

- This prints `!`
LAST hello
```

## Loops

We can also do something forever:

```
STATIC_STR_VAR hello Hello, Bashgenn!

FOREVER
  ECHO hello
DONE
```

## Practice 3 - Repeating input

Now, create a program that reads one line of output and writes it forever.

<details><summary>Click to expand the solution</summary>
```
READ my_variable

FOREVER
  ECHO my_variable
DONE
```
</details>

Please note that you can't have nested loops because of [the bug in RBGN](https://github.com/romw314/rust-bashgenn/issues/1){:target=blank}.

