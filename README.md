# toolchain for building rustc
A project that provides a toolchain for building the Rust compiler on x86_64 Linux.

*Note: This is a community website and is not officially endorsed by the Rust project.

musl targets are copied from https://musl.cc/

## Usage
```bash
cargo install --git https://github.com/oligamiq/toolchain-for-building-rustc
toolchain-for-building-rustc --tier 1 --tier 2-host --os linux -t sparcv9-sun-solaris -t arm-unknown-linux-musleabi -t arm-unknown-linux-musleabihf -t i586-unknown-linux-gnu -t i686-unknown-linux-musl
```
Currently, only these are supported. For more details, please refer to: `https://github.com/oligamiq/rust_wasm/blob/82e56231caf29dbba4c28a719bfef1ac89772234/.github/workflows/rustc_llvm_with_lld.yml`.

### about install
All file is installed in `/x-tools` directory.
Place the symbolic link for bin in /usr/local/bin.

## !! Caution !!
Several musl targets are not tested yet and it depends on the gnu toolchain.

## compile check
Compile check is done, but it is not guaranteed to work.
Compile check on c, c++.

## TODO
- [] Check downloaded files by signature.
- [] Refactor the error handling.
- [] Handle ctrl-c and safely exit.

## Related Projects
- https://musl.cc/

## License

Unless otherwise noted, the original source code, build scripts, configuration
files, and documentation in this repository are licensed under either of

- [MIT License](LICENSE-MIT)
- [Apache License, Version 2.0](LICENSE-APACHE)

at your option.

The `scripts/` directory, `configs/` configuration files, and parts of the
GitHub Actions build infrastructure include code copied or adapted from the
[Rust project's CI build infrastructure](https://github.com/rust-lang/rust/tree/46e8d20301cb4abe91ab0a4bea43bb085e1d4e4a/src/ci/docker).
Upstream copyrights are retained by the Rust contributors. Those portions remain
subject to Rust's [license terms and copyright notices](https://github.com/rust-lang/rust/blob/46e8d20301cb4abe91ab0a4bea43bb085e1d4e4a/COPYRIGHT).

The GCC and glibc patches under `configs/riscv64gc-unknown-linux-gnu/patches/`
are third-party code and are excluded from this repository's dual-license grant.
They retain their original authorship, copyright notices, and applicable
[GCC](https://gcc.gnu.org/onlinedocs/gcc/Copying.html) and
[glibc](https://www.gnu.org/software/libc/) license terms.

Third-party toolchains and components, including those obtained from
[musl.cc](https://musl.cc/), remain subject to their respective licenses and
copyright notices. The licenses of this repository do not relicense those
components or distributed artifacts.
