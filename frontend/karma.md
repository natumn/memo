# Karma

### Karmaとは
ブラウザ上で単体テストを実行するためのテストランナー。
ファイル変更の監視や結果のレポートの出力など様々な機能がある。

### Karmaの構成
Karmaには大きく４つのプラグインが存在する。

- Framework
	テストライブラリやテストの対象となるファイルの登録

- Launcher
　テストを実行するブラウザの登録

- Perprocessor
	ファイル読み込みの前に割り込ませる処理

- Reporter
　テスト結果のログ出力

### 設定
karmaの設定はkarma.conf.jsがデフォルトで読み込まれる。
例
```javascript:karma.conf.js
// karmaの内部でrequire('./karma.conf.js')で内部的に呼ばれるのでmodules.exportsする。
var webpackConfig = require('../../build/webpack.test.conf');

module.exports = function(config) {
	config.set({
		files: [
			'app/app.js'
			'test/test_*.js',
		],
		logLevel: config.LOG_DEBUG,
		browsers: ['Chrome'],	

		// 使用するテストフレームワークを設定
		frameworks: ['mocha', 'sinon-chai']

		reporter: ['spec', 'coverage'],

		// ファイル変更があったら再実行してくれる。デフォルトでtrue
		autoWatch: true,

		//webpackの設定
		webpack: webpackConfig,
	}),
}

```

多すぎで書ききれないので[karma document](https://karma-runner.github.io/0.13/config/configuration-file.html)を参照.
