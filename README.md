# pages

GitHub Pages で公開する小さな Web ツール置き場です。

公開 URL: https://nichicom-sakurai.github.io/pages/

## 構成

| パス | 内容 |
| --- | --- |
| `index.html` | ツール一覧 (トップページ) |
| `font-preview/` | 書体プレビュー |
| `.nojekyll` | Jekyll 処理を無効化し、ファイルをそのまま配信する |

## ツールの追加方法

1. `<ツール名>/index.html` を作る (ビルド不要の静的ファイル)。
2. ルートの `index.html` の一覧にリンクを追加する。
3. `main` ブランチに push すると、数分で公開に反映される。

## 注意

- リポジトリは Public です。秘密情報や社外に出せない内容は置かないでください。
- 有償フォントのファイルはライセンス上ここに置かないでください。`font-preview` は利用者のブラウザ内でフォントファイルを読み込む方式です。
