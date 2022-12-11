# Rust Notes
## Cargo
`Cargo` is the Rust package manager. Cargo lets you download dependencies (crates), compile your own packages, make distributable packages, upload them to crates.io, etc. This is most commonly used during development for checking, building, and running.

### Create a new rust program
```
./$ cargo new <new_project_folder_name>
```

### Check the source (doesn't build a binary)
```
./$ cargo check
```

### Build the binary for debug mode (doesn't run)
```
./$ cargo build

NOTE: Binary can be found:
./target/debug/<program_name>

NOTE: Binary can be manually run:
./$ ./target/debug/<program_name>
```

### Build the binary for release mode (doesn't run)
```
./$ cargo build --release

NOTE: Binary can be found:
./target/release/<program_name>

NOTE: Binary can be manually run:
./$ ./target/release/<program_name>
```

### Build and Run
```
./$ cargo run
```

### Build and Run with arguments
```
./$ cargo run -- <first_arg> <second_arg>
```

## rustc
`rustc` is the compiler for Rust.

### Check if rust is installed, and what version
```
./$ rustc --version
```

## rustup
`rustup` is the toolchain installer/updater. Can be used to setup cross compile, etc.

### Update rust
```
./$ rustup update
```

### Local rust documents
```
./$ rustup doc
```

## debugging
### Type information
It seems like Visual Studio code is the best way to develop and debug Rust. Mostly this is because of the `rust-analyzer` plugin, which dynamically displays type information that the rust compiler will wind up inferring. This is convinient because 1) The Rust type syntax is too intricate to manually type, 2) Rust is a low level systems language, where information about types can be significant. An example is Strings, clearly knowing when working with `String` or `&str`.
  
Short of installing Visual Studio Code as a debugger, or having rust docs open all the time, it worked to call a bogus method and then run `./ cargo check`.

#### Example: What string type is returned by lines() method?
```
 48         for line in contents.lines() {
 49             line.test_method(); // Calling a bogus method to throw an error about the type
```

```
cmgrassee@penguin:~/kvstore$ cargo check
    Checking kvstore v0.1.0 (/home/cmgrassee/kvstore)
error[E0599]: no method named `test_method` found for reference `&str` in the current scope
  --> src/main.rs:49:18
   |
49 |             line.test_method();
   |                  ^^^^^^^^^^^ method not found in `&str`

```


