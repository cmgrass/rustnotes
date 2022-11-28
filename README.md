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

