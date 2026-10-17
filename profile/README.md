<p align="center">
  <img width="120" alt="" src="./mark.png" />
</p>

<p align="center">
  <img width="340" alt="zlow" src="./logo-light.svg#gh-light-mode-only" />
  <img width="340" alt="zlow" src="./logo-dark.svg#gh-dark-mode-only" />
</p>

<p align="center">
<b>The blazing fast polyglot toolkit.</b>
</p>

<p align="center">
<a href="https://www.zlow.site">Website</a> ·
<a href="https://www.zlow.site/docs">Docs</a> ·
<a href="https://www.zlow.site/docs/typescript">TypeScript</a> ·
<a href="https://www.zlow.site/docs/kotlin">Kotlin</a> ·
<a href="https://www.zlow.site/docs/python">Python</a> ·
<a href="https://www.zlow.site/docs/go">Go</a> ·
<a href="https://www.zlow.site/docs/rust">Rust</a> ·
<a href="https://www.zlow.site/docs/cpp">C++</a>
</p>

Welcome to [zlow](https://www.zlow.site) — compilers and transpilers you run from one binary. TypeScript builds, checks, and bundles in a native CLI. Kotlin, Python, Go, Rust, and C++ numeric kernels compile through the same spine.

```sh
npm install @zlow/cli
```

## Languages

### [TypeScript](https://www.zlow.site/docs/typescript)

Transpile, type-check, bundle, and emit declarations from one binary. Emit stays independent of the checker.

- **Build** — type stripping to JavaScript, with source maps, watch, and your `tsconfig.json`
- **Check** — a separate type-check, so transpile speed stays independent of the checker
- **Bundle** — tree-shaken module graphs, multi-entry chunks, and `.d.ts` rollups
- **API** — `transformSync` in-process on Linux and macOS

24 ms to transpile zod. esbuild took 115 ms on the same corpus (4.8×).

### [Kotlin](https://www.zlow.site/docs/kotlin)

A `Double` / `Boolean` kernel, compiled to a native binary. `zlow.json` names the entry. Accepted kernels match pinned Kotlin/Native.

- **Compile** — 139 ms for the kernel; Gradle Kotlin/Native took 41.2 s on the same source (296×)
- **Output** — 3.6 KB stripped, against a 497 KB Gradle release `.kexe` for the same kernel
- **Hot path** — the rest of the app stays Kotlin

### [Python](https://www.zlow.site/docs/python)

A `float` / `bool` kernel, compiled to a native binary. Accepted kernels match pinned CPython.

- **Runtime** — 32.3 ms for `entry()`, against 661 ms on CPython (20.5×)
- **Setup** — a `zlow.json` and `zlow native .`
- **Scope** — out-of-scope code fails by name, before a binary is written

### [Go](https://www.zlow.site/docs/go)

A `float64` kernel, compiled to a native binary. Accepted kernels match pinned `go` (gc).

- **Runtime** — 1.4 ms for `entry()`, against 9.1 ms on the gc compiler (6.7×)
- **Setup** — a `zlow.json` and `zlow native .`
- **Hot path** — the rest of the app stays Go and can load the shared library

### [Rust](https://www.zlow.site/docs/rust)

An `f64` kernel, compiled to a native binary or a shared library. Accepted kernels match pinned rustc.

- **Runtime** — 8.7 ms for `entry()`, against 141.3 ms on rustc (16.3×)
- **Setup** — a `zlow.json` and `zlow native .`
- **Hot path** — the rest of the app stays Rust and can load the shared library

### [C++](https://www.zlow.site/docs/cpp)

A `double` kernel, compiled to LLVM text. Accepted kernels match pinned Clang.

- **Runtime** — 6.4 ms for `entry()`, matching `clang++ -O2` on the same branchy kernel
- **Setup** — a `zlow.json` and `zlow native . --emit-llvm kernel.ll`
- **Hot path** — the rest of the app stays C++

## Also in the toolkit

Every language ships in the same CLI.

- **Install** — `npm install @zlow/cli`, or the same package with yarn, bun, or deno
- **Packages** — `zlow install` fills `node_modules` from `package.json`, Kotlin Maven coordinates into `kotlin_modules`, and Go modules into `vendor`
- **One binary** — `zlow build` for TypeScript, `zlow native` for kernels

## Why zlow

zlow is one native binary for TypeScript builds and for numeric kernels in Kotlin, Python, Go, Rust, and C++. Compile the hot path. Keep the rest of the program in the language you already write.

Try [zlow](https://www.zlow.site) today.
