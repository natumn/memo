# rustc_driverクレートについて、理解した点 && よくわからない点まとめ

## rust-lang公式より
> The rustc_driver crate, at the top of this lattice, is effectively the "main" function for the rust compiler. It doesn't have much "real code", but instead ties together all of the code defined in the other crates and defines the overall flow of execution. (As we transition more and more to the query model, however, the "flow" of compilation is becoming less centrally defined.)

rustc_driverクレートがRustコンパイラのメインとなる。機能自体（コード）は多くはないが、他のクレートを結びつけて、コンパイラの実行フローを定義してる。

[lib.rs](https://github.com/rust-lang/rust/blob/master/src/librustc_driver/lib.rs)


