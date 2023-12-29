# Getting started with Bashgenn

First of all, we want to install RBGN, the interpreter of Bashgenn. To install RBGN, [install Rust](https://rustup.rs) and then run this command (works cross-platform):

```sh
cargo install rbgn
```

Create a file named `hello_world.bgn` and open it in your favorite editor. We do it in Nano:

```sh
nano hello_world.bgn
```

Put this contents into the file:

```
- Lines starting with a hyphen (-) are comments in Bashgenn.
- Please note that you can't pace a comment after a command.
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

Now, create a program that prints `Hello, Bashgenn!` to the output.

<details><summary>Click to expand the solution</summary>
```
STATIC_STR_VAR hello_bg Hello, Bashgenn!
ECHO hello_bg
```
</details>

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

<!-- TODO: practice: reverse 2 lines of input -->

