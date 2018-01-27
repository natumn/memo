# Min-Camlについてまとめ
main.mlの末尾の let = ()からコンパイラの実行が始まる。
「プログラム名.ml」というMinCamlソースコードから「プログラム名.s」というSPARCアセンブリが生成される。
そこから、lexbufにソースコードのバッファを渡して、コンパイルが開始される。


### ちなみにSPARCアセンブラとは
RISCアーキテクチャ（コンピュータの命令セットのアーキテクチャ（ISA）の設計手法の一つ）でメモリのロード・ストアと演算命令が分離している。
命令はどれも１ワードの32bitの固定長である。
レジスタウィンドウという独特の仕組みを持つ。(min-camlでは使ってない)
など、詳しくは下記の参考の[MinCaml読解ノート: SPARC概要](http://smpl.seesaa.net/article/4600753.html)にあるので、そっち見て。

## メインルーチン(main.lexbuf)でのTODOリスト

* コマンドラインの解析 -> オプション解析、ソースコード取得(main.ml)
* 字句解析(Lexer.token)
* 構文解析(Parser.exp)
* 型推論(Typing.f)
* K正規化(KNomal.f)
* α変換(Alpha.f)
* 最適化(iter) -> 値が変わらなくなるまで、また-iterの回数分繰り返す。
  * β簡約化(Beta.f)
  * ネストしたletの簡約(Assoc.f)
  * インライン展開(Inline.f)
	* 定数畳み込み(ConstFold.f)
	* 不要定義削除(Elim.f)
* クロージャ変換(Closure.f)
* 仮想マシンコード生成(Virtual.f)
* SPARCの13bit即値最適化(Simm13.f)
* レジスタ割り当て(RegAlloc.f)
* アセンブリ生成(Emit.f)

## 文法まとめ

[ここみて](http://esumii.github.io/min-caml/index.html)

## カリー化

## 参考
* [MinCamlチュートリアル](http://esumii.github.io/min-caml/tutorial-mincaml-1.html)
* [MinCaml読解ノート: SPARC概要](http://smpl.seesaa.net/article/4600753.html)
