# wx-wasm-pack

wasm-pack for Wechat

### Install

```bash
cargo install --git https://github.com/BenLocal/wx-wasm-pack
```

### Usage

1. Create a new project

```bash
wx-wasm-pack new demo
```

2. Build your WebAssembly package

```bash
cd demo
wx-wasm-pack build -t web --no-typescript --release
```

3. Integrate with WeChat Mini Program

   Copy the generated files to your WeChat Mini Program project:

- `./pkg/my-project_bg.wasm`: WebAssembly binary
- `./pkg/my-project.js`: JavaScript bindings 4. usage

4. Use in WeChat Mini Program

```js
// index.js
import initSync, {greet} from "demo"

...

onLoad() {
    // Initialize WebAssembly module
    initSync("/pages/index/demo_bg.wasm")

    // Call exported functions
    greet() // Hello, demo!
},
```
