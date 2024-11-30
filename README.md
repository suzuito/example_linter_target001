# golangci-lint `Module Plugin System` 利用例

[私的なlinter](https://github.com/suzuito/linter1/tree/main/linter2)をgolangci-lintから実行する。

- 前提条件
  - golangci-lint `v1.57.0`以上

## [Module Plugin System](https://golangci-lint.run/plugins/module-plugins)

プラグインとして、私的なlinterをgolangci-lintへ追加する。下記のどちらかの方法によりカスタムなgolangci-lintバイナリをビルドし、このバイナリを実行する。

- (方法1) `.custom-gcl.yml`を書き、`golangci-lint custom`によってカスタムなgolangci-lintバイナリをビルドする
- (方法2) golangci-lintのレポジトリをクローンし、`cmd/golangci-lint/plugins.go`にて私的なプラグインをimportし、golangci-lintバイナリをビルドする

方法1は方法2を自動でやってるだけ。

## 方法1

```bash
golangci-lint -v custom && ./custom-gcl run --max-same-issues 0 -v ./...
```
