# `stringslice`

[![Build status](https://img.shields.io/github/workflow/status/staticintlucas/stringslice/Build?style=flat-square)][build]
[![Test status](https://img.shields.io/github/workflow/status/staticintlucas/stringslice/Test?label=tests&style=flat-square)][tests]
[![Code coverage](https://img.shields.io/codecov/c/gh/staticintlucas/stringslice?style=flat-square)][coverage]
[![Code quality](https://img.shields.io/codefactor/grade/github/staticintlucas/stringslice?style=flat-square)][code quality]
[![Crate version](https://img.shields.io/crates/v/stringslice?style=flat-square)][version]
[![Rust version](https://img.shields.io/badge/rust-1.30%2B-informational?style=flat-square)][rust version]
[![Downloads](https://img.shields.io/crates/d/stringslice?style=flat-square)][downloads]

A collection of methods to slice strings based on character indices rather than bytes.

This crate implements the `StringSlice` trait for `&str`,
containing the `slice`, `try_slice`, `substring`, and `try_substring` methods.

## Features

* Uses primitive `&str` and standard `String` types
* `#[no_std]` compatible by default
* No `unsafe` code
* Small footprint
  * ~50 LoC excluding blank lines, comments, and tests
  * No additional dependencies (only dev-dependencies)

## Usage

Add `stringslice` to your `Cargo.toml` file:

```toml
[dependencies]
stringslice = "0.1"
```

## Examples

The `slice` method can be used to slice a `&str`.

```rust
use stringslice::StringSlice;

assert_eq!("Ùníc😎de".slice(4..5), "😎");
assert_eq!("世界こんにちは".slice(2..), "こんにちは");
```

The `substring` method is provided for convenience and accepts
separate parameters for the start and end of the slice.

```rust
use stringslice::StringSlice;

assert_eq!("Γεια σου κόσμε".substring(9, 14), "κόσμε");
```

There are also equivalent `try_slice` and `try_substring` methods
which return `None` for invalid input.

```rust
use stringslice::StringSlice;

assert_eq!("string".try_slice(4..2), None);
```

## Documentation

* [API reference on docs.rs][docs]

[build]: https://github.com/staticintlucas/stringslice/actions/workflows/build.yml
[tests]: https://github.com/staticintlucas/stringslice/actions/workflows/test.yml
[coverage]: https://app.codecov.io/gh/staticintlucas/stringslice
[code quality]: https://www.codefactor.io/repository/github/staticintlucas/stringslice/
[version]: https://crates.io/crates/stringslice
[rust version]: https://crates.io/crates/stringslice
[downloads]: https://crates.io/crates/stringslice

[docs]: https://docs.rs/stringslice/latest/stringslice/

## Licence

Licensed under either of

* Apache License, Version 2.0, ([LICENCE-APACHE](LICENCE-APACHE) or [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0))
* MIT license ([LICENCE-MIT](LICENCE-MIT) or [http://opensource.org/licenses/MIT](http://opensource.org/licenses/MIT))

at your option.
