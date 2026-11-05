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
- 有償フォントのファイルはライセンス上ここに置かないでください。`font-preview` は Adobe Fonts の配信か、利用者の Mac にインストール済みのフォントを使います。

## font-preview (書体プレビュー)

行書体・千社文字・江戸文字・寄席文字で文字を表示し、画像保存と印刷ができるツールです。
字形を正確に再現するため、代替フォントは使いません。正式なフォントが見つからない書体は「未インストール」と表示します。

### フォントの探し方 (優先順)

1. Adobe Fonts の Web プロジェクトのフォント (`STYLES[].adobe` に CSS 用の font-family 名などを書く)
2. Mac にインストール済みのフォント (`STYLES[].candidates`)

インストール済みフォントは `@font-face` の `local()` で照合します。Chrome では英語のフルネームか PostScript 名でないと一致しません (例: `YuKyokasho Medium`)。

### Adobe Fonts

Adobe Fonts の日本語フォントは、ページ上の文字だけを配信する方式のため JavaScript の埋め込みコードを使います。Web プロジェクト ID は `font-preview/index.html` の `ADOBE_FONTS_PROJECT_ID` (`zwp6jxa`) です。

| 書体 | Adobe Fonts のフォント | `STYLES[].adobe[].family` |
| --- | --- | --- |
| 行書体 | [AB-香蘭行書](https://fonts.adobe.com/fonts/ab-kouran-gyosho) | `ab-kouran-gyosho` |
| 行書体 (比較用) | [Sic優美毛筆行書](https://fonts.adobe.com/fonts/sicyubi-mohitsugyosho) | `sicyubi-mohitsugyosho` |
| 行書体 (比較用) | [Sic優美筆行書](https://fonts.adobe.com/fonts/sicyubi-fudegyosho) | `sicyubi-fudegyosho` |
| 行書体 (比較用) | [Sic優美板書行書](https://fonts.adobe.com/fonts/sicyubi-banshogyosho) | `sicyubi-banshogyosho` |
| 行書体 (比較用) | [AH白洲毛筆行草体W0](https://fonts.adobe.com/fonts/ah-hakushu-running-script) | `ah-hakushu-running-script` |
| 行書体 (比較用) | [TA-礼筆M](https://fonts.adobe.com/fonts/ta-rehitsu-m) | `ta-rehitsu-m` |
| 千社文字 | [VDL 京千社](https://fonts.adobe.com/fonts/vdl-kyosensya) | `vdl-kyosensya` |
| 千社文字風 | [AB-青龍L](https://fonts.adobe.com/fonts/ab-seiryu-light) | `ab-seiryu-light` |
| 千社文字風 | [AB-組木_M](https://fonts.adobe.com/fonts/ab-kumiki-m) | `ab-kumiki-m` |
| 千社文字風 | [AB雅楽B](https://fonts.adobe.com/fonts/ab-gagaku-b) | `ab-gagaku-b` |
| 千社文字風 | [TA-雅](https://fonts.adobe.com/fonts/ta-miyabi) | `ta-miyabi` |
| 千社文字風 | [ABイントレ](https://fonts.adobe.com/fonts/ab-intore) | `ab-intore` |
| 千社文字風 | [AB-駿河U](https://fonts.adobe.com/fonts/ab-suruga-u) | `ab-suruga-u` |
| 千社文字風 | [AB-やまびこB](https://fonts.adobe.com/fonts/ab-yamabiko-b) | `ab-yamabiko-b` |
| 江戸文字 | [AB-渡月勘亭流](https://fonts.adobe.com/fonts/ab-togetsukanteiryu) | `ab-togetsukanteiryu` |
| 寄席文字 | [TA演芸筆](https://fonts.adobe.com/fonts/ta-engeifude) | `ta-engeifude` |

書体を追加するときは、fonts.adobe.com の Web プロジェクトにフォントを追加し、`STYLES[].adobe` に `{ family, name, url }` を追加します。`family` は Web プロジェクトに表示される CSS 用の font-family 名、`name` はカードに表示するフォント名、`url` はフォントの紹介ページ (fonts.adobe.com のフォントのページ) です。カードではフォント名が紹介ページへのリンクになります。

社内プロキシ配下では Adobe Fonts の配信 (`use.typekit.net` など) が読み込めない可能性があります。確認はプロキシ配下ではない回線で行ってください。
