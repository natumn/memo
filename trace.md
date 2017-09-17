straceコマンド
strace [command] でプロセスが呼び出すシステムコールをトーレスして、その情報を表示する。
strace -p [pid]　でデーモン化してたりなどの実行中のプロセスをトレースできる。
-o ファイル出力
-s 表示する文字数を増やす

ltraceコマンド
共有ライブラリの関数呼び出しをトレースする。
オプションはstraceと同じ。

参照: http://0xcc.net/blog/archives/000103.html
