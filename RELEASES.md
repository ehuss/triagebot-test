Version 1.73.0 (2023-10-05)
==========================

<a id="1.73.0-Language"></a>

Language
--------

- [Uplift `clippy::fn_null_check` lint as `useless_ptr_null_checks`.](https://github.com/rust-lang/rust/pull/111717/)
- [Make `noop_method_call` warn by default.](https://github.com/rust-lang/rust/pull/111916/)
- [Support interpolated block for `try` and `async` in macros.](https://github.com/rust-lang/rust/pull/112953/)
- [Make `unconditional_recursion` lint detect recursive drops.](https://github.com/rust-lang/rust/pull/113902/)
- [Future compatibility warning for some impls being incorrectly considered not overlapping.](https://github.com/rust-lang/rust/pull/114023/)
- [The `invalid_reference_casting` lint is now **deny-by-default** (instead of allow-by-default)](https://github.com/rust-lang/rust/pull/112431)

<a id="1.73.0-Compiler"></a>

Compiler
--------

- [Write version information in a `.comment` section like GCC/Clang.](https://github.com/rust-lang/rust/pull/97550/)
- [Add documentation on v0 symbol mangling.](https://github.com/rust-lang/rust/pull/97571/)
- [Stabilize `extern "thiscall"` and `"thiscall-unwind"` ABIs.](https://github.com/rust-lang/rust/pull/114562/)
- [Only check outlives goals on impl compared to trait.](https://github.com/rust-lang/rust/pull/109356/)
- [Infer type in irrefutable slice patterns with fixed length as array.](https://github.com/rust-lang/rust/pull/113199/)
- [Discard default auto trait impls if explicit ones exist.](https://github.com/rust-lang/rust/pull/113312/)
- Add several new tier 3 targets:
    - [`aarch64-unknown-teeos`](https://github.com/rust-lang/rust/pull/113480/)
    - [`csky-unknown-linux-gnuabiv2`](https://github.com/rust-lang/rust/pull/113658/)
    - [`riscv64-linux-android`](https://github.com/rust-lang/rust/pull/112858/)
    - [`riscv64gc-unknown-hermit`](https://github.com/rust-lang/rust/pull/114004/)
    - [`x86_64-unikraft-linux-musl`](https://github.com/rust-lang/rust/pull/113411/)
    - [`x86_64-unknown-linux-ohos`](https://github.com/rust-lang/rust/pull/113061/)
- [Add `wasm32-wasi-preview1-threads` as a tier 2 target.](https://github.com/rust-lang/rust/pull/112922/)

Refer to Rust's [platform support page][platform-support-doc]
for more information on Rust's tiered platform support.

<a id="1.73.0-Libraries"></a>

Libraries
---------

- [Add `Read`, `Write` and `Seek` impls for `Arc<File>`.](https://github.com/rust-lang/rust/pull/94748/)
- [Merge functionality of `io::Sink` into `io::Empty`.](https://github.com/rust-lang/rust/pull/98154/)
- [Implement `RefUnwindSafe` for `Backtrace`](https://github.com/rust-lang/rust/pull/100455/)
- [Make `ExitStatus` implement `Default`](https://github.com/rust-lang/rust/pull/106425/)
- [`impl SliceIndex<str> for (Bound<usize>, Bound<usize>)`](https://github.com/rust-lang/rust/pull/111081/)
- [Change default panic handler message format.](https://github.com/rust-lang/rust/pull/112849/)
- [Cleaner `assert_eq!` & `assert_ne!` panic messages.](https://github.com/rust-lang/rust/pull/111071/)
- [Correct the (deprecated) Android `stat` struct definitions.](https://github.com/rust-lang/rust/pull/113130/)

<a id="1.73.0-Stabilized-APIs"></a>

Stabilized APIs
---------------

- [Unsigned `{integer}::div_ceil`](https://doc.rust-lang.org/stable/std/primitive.u32.html#method.div_ceil)
- [Unsigned `{integer}::next_multiple_of`](https://doc.rust-lang.org/stable/std/primitive.u32.html#method.next_multiple_of)
- [Unsigned `{integer}::checked_next_multiple_of`](https://doc.rust-lang.org/stable/std/primitive.u32.html#method.checked_next_multiple_of)
- [`std::ffi::FromBytesUntilNulError`](https://doc.rust-lang.org/stable/std/ffi/struct.FromBytesUntilNulError.html)
- [`std::os::unix::fs::chown`](https://doc.rust-lang.org/stable/std/os/unix/fs/fn.chown.html)
- [`std::os::unix::fs::fchown`](https://doc.rust-lang.org/stable/std/os/unix/fs/fn.fchown.html)
- [`std::os::unix::fs::lchown`](https://doc.rust-lang.org/stable/std/os/unix/fs/fn.lchown.html)
- [`LocalKey::<Cell<T>>::get`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.get)
- [`LocalKey::<Cell<T>>::set`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.set)
- [`LocalKey::<Cell<T>>::take`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.take)
- [`LocalKey::<Cell<T>>::replace`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.replace)
- [`LocalKey::<RefCell<T>>::with_borrow`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.with_borrow)
- [`LocalKey::<RefCell<T>>::with_borrow_mut`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.with_borrow_mut)
- [`LocalKey::<RefCell<T>>::set`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.set-1)
- [`LocalKey::<RefCell<T>>::take`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.take-1)
- [`LocalKey::<RefCell<T>>::replace`](https://doc.rust-lang.org/stable/std/thread/struct.LocalKey.html#method.replace-1)

These APIs are now stable in const contexts:

- [`rc::Weak::new`](https://doc.rust-lang.org/stable/alloc/rc/struct.Weak.html#method.new)
- [`sync::Weak::new`](https://doc.rust-lang.org/stable/alloc/sync/struct.Weak.html#method.new)
- [`NonNull::as_ref`](https://doc.rust-lang.org/stable/core/ptr/struct.NonNull.html#method.as_ref)

<a id="1.73.0-Cargo"></a>

Cargo
-----

- [Encode URL params correctly for `SourceId` in `Cargo.lock`.](https://github.com/rust-lang/cargo/pull/12280/)
- [Bail out an error when using `cargo::` in custom build script.](https://github.com/rust-lang/cargo/pull/12332/)

<a id="1.73.0-Misc"></a>

Misc
----

<a id="1.73.0-Compatibility-Notes"></a>

Compatibility Notes
-------------------

- [Update the minimum external LLVM to 15.](https://github.com/rust-lang/rust/pull/114148/)
- [Check for non-defining uses of return position `impl Trait`.](https://github.com/rust-lang/rust/pull/112842/)

<a id="1.73.0-Internal-Changes"></a>

Internal Changes
----------------

These changes do not affect any public interfaces of Rust, but they represent
significant improvements to the performance or internals of rustc and related
tools.

- [Remove LLVM pointee types, supporting only opaque pointers.](https://github.com/rust-lang/rust/pull/105545/)
- [Port PGO/LTO/BOLT optimized build pipeline to Rust.](https://github.com/rust-lang/rust/pull/112235/)
- [Replace in-tree `rustc_apfloat` with the new version of the crate.](https://github.com/rust-lang/rust/pull/113843/)
- [Update to LLVM 17.](https://github.com/rust-lang/rust/pull/114048/)
- [Add `internal_features` lint for internal unstable features.](https://github.com/rust-lang/rust/pull/108955/)
- [Mention style for new syntax in tracking issue template.](https://github.com/rust-lang/rust/pull/113586/)

