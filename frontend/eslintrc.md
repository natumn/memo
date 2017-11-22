## eslintrc

#### eslintrcとは

eslintの設定ファイル。

例えば,こんな感じ。


```json:.eslintrc

{
  "parserOptions": {
    "ecmaVersion": 6,
    "sourceType": "module"
  },
  "env": {
    "mocha": true,
    "es6": true,
		"node": true,
  },
	"ecmaFeatures": {
		"jsx": true,
	},
  "globals": {
    "expect": true,
    "sinon": true
  }
	"rules": {
		"strict": false,
		"semi": 2,
		"no-unused-vars": [1, {"vars": "all", "args": "after-used"}],
	},
}

```
うえのほうは文法やツール類,rulesとかは細かい設定になってくる。


最近のツールだとここら辺を自動設定してくれてるが、es6（例えば、import文,jsxとか）などはなかったりしてエラーを吐き、思うように書けないことがあったりする。ので、覚えとくと詰むことが減ると思う。
