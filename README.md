Initiate a library with Cargo:
```
cargo new --lib yew-app
cd yew-app
```

Add the required dependencies to `Cargo.toml`:
```
[lib]
crate-type = ["cdylib", "rlib"]

[dependencies]
yew = "0.17"
wasm-bindgen = "0.2.67"
```

Create your HTML index:
```sh
mkdir static
touch ./static/index.html
```

Use the example index.html and style.css from `./yew-app/static/`

Build the web application:
```sh
cargo install wasm-pack # if you don't already have it
wasm-pack build --target web --out-name wasm --out-dir ./static
```

Serve it with miniserve (or any other HTTP server):
```sh
cargo install miniserve # if you don't already have it
miniserve ./static --index index.html
```
