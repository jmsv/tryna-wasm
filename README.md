# tryna-wasm

Just playing around with WebAssembly and stuff

---

## Getting Started

At the moment this repo just contains a FizzBuzz C program, `hello.c`, with a minimal setup for running this from JavaScript via WASM.

1. Install Emscripten. Instructions at https://emscripten.org/docs/getting_started/downloads.html
2. Run `npm start` - this runs `npm run build` and then `node hello.build.js`

`package.json`'s `build` command runs `emcc hello.c -s WASM=1 -o hello.build.js` to compile `hello.c` to `hello.build.wasm` and create `hello.build.js`, which wraps the WebAssembly.

This `hello.build.js` file can also be used in a browser environment; change the build command to output html (e.g. `emcc hello.c -s WASM=1 -o hello.html`) and serve this file to try it out.
