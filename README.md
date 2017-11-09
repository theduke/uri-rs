# URI

A URI type for Rust.

[![Build Status](https://travis-ci.org/hyperium/http.svg?branch=master)](https://travis-ci.org/hyperium/http)
[![Crates.io](https://img.shields.io/crates/v/uri.svg?maxAge=2592000)](https://crates.io/crates/uri)
[![Documentation](https://docs.rs/uri/badge.svg)][dox]

More information about this crate can be found in the [crate
documentation][dox].

[dox]: https://docs.rs/uri

## Usage

To use `uri`, first add this to your `Cargo.toml`:

```toml
[dependencies]
uri = "0.1"
```

Next, add this to your crate:

```rust
extern crate uri;

use uri::{Uri};

fn main() {
    // ...
}
```

## Examples

Create an HTTP request:

```rust
extern crate http;

use http::Request;

fn main() {
    let request = Request::builder()
      .uri("https://www.rust-lang.org/")
      .header("User-Agent", "awesome/1.0")
      .body(())
      .unwrap();
}
```

Create an HTTP response:

```rust
extern crate http;

use http::{Response, StatusCode};

fn main() {
    let response = Response::builder()
      .status(StatusCode::MOVED_PERMANENTLY)
      .header("Location", "https://www.rust-lang.org/install.html")
      .body(())
      .unwrap();
}
```

# License

`uri` is primarily distributed under the terms of both the MIT license and the
Apache License (Version 2.0), with portions covered by various BSD-like
licenses.

See LICENSE-APACHE, and LICENSE-MIT for details.
