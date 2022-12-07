# Private Voting
This library implements an API for running privacy-preserving ballots. The library can be compiled to WASM, making it suitable for use within a browser application (for Cryptosim), as well as part of the flight software.

## Installing prerequisites
Prerequisites include
 
 *  `cargo`
 *  `wasm-pack`

`cargo` can be installed using `rustup`. Follow the installation instructions on [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install).

Once `cargo` is installed, `wasm-pack` can be installed by running

    $ cargo install wasm-pack

## Building and testing

To run the unit tests, execute
    
    $ cargo test

To build the WASM target and its JS bindings, run

    $ wasm-pack build --target web
    
The WASM target and JS bindings will then be placed in a `pkg` directory.

### Testing in a browser

To run unit tests in a browser, execute

    $ wasm-pack test --chrome

To test calling the compiled WASM from Javascript code, there is a simple HTML under the `html` directory, named `test.html`. It has to be served over HTTP and not just opened directly as a file in the browser, since otherwise, CORS policies will block importing the Javascript file with the WASM bindings.

### Generating documentation
To build the documentation for the `private_voting` library, execute

     $ cargo doc
     
which outputs the documentation in HTML format under `target/doc`.