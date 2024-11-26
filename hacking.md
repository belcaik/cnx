# Hacking Guide for Cnx Project

Welcome to the Cnx project! This guide will help you get started with hacking on Cnx, a simple X11 status bar for use with simple window managers (WMs). Follow the steps below to set up your development environment, understand the project structure, and start contributing.

## Table of Contents

1. [Project Structure](#project-structure)
2. [Setting Up the Development Environment](#setting-up-the-development-environment)
3. [Building the Project](#building-the-project)
4. [Running the Project](#running-the-project)
5. [Testing the Project](#testing-the-project)

## Project Structure

The Cnx project is organized into several directories and files:

```
.github/
.vscode/
cnx/
cnx-bin/
cnx-contrib/
target/
Cargo.lock
Cargo.toml
CHANGELOG.md
LICENSE
Makefile
README.md
rust-toolchain
shell.nix
```

- **cnx/**: Core library for the Cnx status bar.
- **cnx-bin/**: Binary crate for running the Cnx status bar.
- **cnx-contrib/**: Additional widgets and extensions for Cnx.
- **target/**: Directory for build artifacts.
- **Cargo.toml**: Cargo configuration file for the workspace.
- **Makefile**: Makefile for common tasks.
- **README.md**: Project documentation.
- **shell.nix**: Nix shell configuration for development.

## Setting Up the Development Environment

1. **Install Rust**: Ensure you have Rust installed. You can install Rust using [rustup](https://rustup.rs/).

2. **Clone the Repository**:
   ```sh
   git clone https://github.com/mjkillough/cnx.git
   cd cnx
   ```

3. **Install Dependencies**:
   - On Ubuntu:
     ```sh
     sudo apt-get install libx11-xcb-dev libxcb-ewmh-dev libpango1.0-dev libcairo2-dev libasound2-dev libiw-dev
     ```
   - Using Nix:
     ```sh
     nix-shell
     ```

4. **Set Up Rust Toolchain**:
   ```sh
   rustup toolchain install $(cat rust-toolchain)
   rustup component add rustfmt clippy
   ```

## Building the Project

To build the project, run the following command:
```sh
cargo build
```

## Running the Project

To run the Cnx status bar, use the following command:
```sh
cargo run --bin cnx-bin
```

## Testing the Project

To run the tests, use the following command:
```sh
cargo test
```