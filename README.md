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

## font-preview (書体プレビュー)

行書体・千社文字・江戸文字・寄席文字で文字を表示し、画像保存と印刷ができるツールです。
字形を正確に再現するため、代替フォントは使いません。正式なフォントが見つからない書体は「未インストール」と表示します。

### フォントの探し方 (優先順)

1. 各書体の「使用フォント」欄に入力したフォント名 (ブラウザの localStorage に保存)
2. Adobe Fonts の Web プロジェクトのフォント (`STYLES[].adobe` に CSS 用の font-family 名を書く)
3. Mac にインストール済みのフォント (`STYLES[].candidates`)

インストール済みフォントは `@font-face` の `local()` で照合します。Chrome では英語のフルネームか PostScript 名でないと一致しません (例: `YuKyokasho Medium`)。

### Adobe Fonts を使う (作業途中)

Adobe Fonts の日本語フォントは、ページ上の文字だけを配信する方式のため JavaScript の埋め込みコードを使います。

1. fonts.adobe.com で Web プロジェクトを作り、次のフォントを追加する。
   - 行書体: AB-香蘭行書
   - 江戸文字: AB-渡月勘亭流
   - 千社文字: VDL 京千社 (提供が続いているか要確認)
   - 寄席文字: Adobe Fonts には見当たらない (別途用意が必要)
2. `font-preview/index.html` の `ADOBE_FONTS_PROJECT_ID` に、埋め込みコード `https://use.typekit.net/<ID>.js` の `<ID>` を書く。
3. `STYLES` の各書体の `adobe` に、Web プロジェクトに表示される CSS 用の font-family 名を書く。
4. ページを開き、各書体のバッジが「Adobe Fonts」になることを確認する。

社内プロキシ配下では Adobe Fonts の配信 (`use.typekit.net` など) が読み込めない可能性があります。確認はプロキシ配下ではない回線で行ってください。
