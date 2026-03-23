# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A learning repository following [The Rust Programming Language](https://rust-book.cs.brown.edu/) (Brown University edition). Notes are captured in a Quarto document; code lives alongside in scripts and Cargo projects.

## Repository Layout

- `notes.qmd` -- chapter-by-chapter notes and summaries (Quarto/HTML format)
- `scripts/` -- standalone `.rs` files compiled with `rustc` (no Cargo)
- `projects/` -- Cargo projects created while following the book (e.g. `hello_cargo/`, `hello_world_cargo_manual/`)
- `projects/get-dependencies/` -- utility Cargo project for pre-caching crates (`rand`, `trpl`) for offline work

## Commands

### Standalone Rust files (in `scripts/`)
```sh
rustc scripts/<file>.rs -o scripts/<file> && ./scripts/<file>
```

### Cargo projects (in `projects/` or `get-dependencies/`)
```sh
cd projects/<name>
cargo build          # compile (debug)
cargo run            # build + run
cargo check          # fast compile check, no binary
cargo test           # run tests
cargo build --release  # optimised build
```

### Render notes
```sh
quarto render notes.qmd
```

## Conventions

- Notes use em dashes (--) for typography, not hyphens
- The `.gitignore` excludes compiled Rust (`target/`), Quarto output (`*.html`, `_site/`, `_book/`), and RStudio artifacts
- Each book chapter may produce new Cargo projects under `projects/`; standalone examples go in `scripts/`
- Rust edition 2024 is used across all Cargo projects
