# StringSlice

A collection of methods to slice strings based on character indices rather than bytes.

This crate implements the `StringSlice` trait for `&str`,
which contains various methods to slice the string.

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
