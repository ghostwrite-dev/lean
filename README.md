# Lean for Ghostwrite

A [Ghostwrite](https://github.com/ghostwrite-dev/ghostwrite) plugin for [Lean 4](https://lean-lang.org):
`.lean` files, served by `lake serve` if it's on your PATH, with the goals in a panel beside the
file (`space v` shows or hides it), colored by Lean's tokens, and with its abbreviations (`\to` is
`→`).

Its code colors Lean and says what its goals panel shows, and reaches nothing at all.

## Installing

In Ghostwrite:

```
:plugin install ghostwrite-dev/lean
```

That installs its latest release.

## Building

With [plugin-build](https://github.com/ghostwrite-dev/plugin-build)'s `build.sh`:

```sh
git clone https://github.com/ghostwrite-dev/plugin-build ../plugin-build
rustup target add wasm32-wasip2
sh ../plugin-build/build.sh
```

That makes `target/plugin/lean`, which `:plugin install target/plugin/lean` installs. It's built
with Rust 1.97.0, against [`ghostwrite-plugin-api`](https://github.com/ghostwrite-dev/ghostwrite/tree/plugin-api-v1.0.0/crates/plugin-api)
at the tag `plugin-api-v1.0.0`, and with the versions in `Cargo.lock`.

## Releases

A tag `v<version>`, the version in `plugin.json`, releases it as `lean-<version>.zip`, with its
sha256 in `lean-<version>.zip.sha256`.

## License

Mozilla Public License 2.0: see [LICENSE](LICENSE).
