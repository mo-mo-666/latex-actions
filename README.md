# latex-compile
LaTeX complile platform for GitHub actions

## 流れ
GitHub Actionsでコンパイルしたいファイルのpathを指定し，手動実行する。

1. 予めmainブランチに`.github/workflows/compile.yaml`ファイルを配置しておく（TeXファイル自体はmainブランチに配置する必要はない）
1. 予めmainブランチ直下に`.latexmkrc`ファイルを配置する
1. GitHub Actionsのページから`Complie and Upload`を選択し，右上の`Run workflow`ボタンを押す。押した際にブランチも設定できる
1. `Path to TeX file`にコンパイルしたいTeXファイルのパスを入力する（例: `samples/ineq/samples.tex`）
1. GitHub Actionsが実行され，コンパイルが完了すると，`compiled`フォルダにコンパイル結果がアップロードされる

### 注意
- `Path to TeX file`は直下からの相対パスで指定する必要がある
- コンパイルが上手くいかなくても，GitHub Actionsは成功として扱うことがある（`continue-on-error: true`が設定されているため）
