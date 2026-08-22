# LIFE SHIFT ｜ 電子書籍版

人生OSをアップデートする9つの物語 ― 全9章＋エピローグ。著者　大橋孝行

`index.html` と表紙画像 `cover.jpg` の2ファイルだけで動きます
（外部CSS・JS・Webフォント・CDNへの依存なし）。GitHub Pages に置くだけで公開できます。

## 公開手順（GitHub Pages）

```bash
git init
git add .
git commit -m "LIFE SHIFT 電子書籍版"
git branch -M main
git remote add origin https://github.com/<ACCOUNT>/<REPO>.git
git push -u origin main
```

そのあと **Settings → Pages** で Source = `Deploy from a branch` /
Branch = `main` / フォルダ = `/ (root)` を選ぶと公開されます。

## 仕様

| 項目 | 内容 |
|---|---|
| 目次 | 画面上部に固定。「目次」ボタンで全10項目を一覧できます |
| 現在地 | 上部バーに章番号と章題を表示。青いバーが読了率を示します |
| PC表示 | 左に追従する目次サイドバー＋右に本文。現在の章がハイライトされます |
| スマホ表示 | 目次はボタンから全画面で開閉。ノッチ／ホームバー（safe-area）を避けて配置 |
| 傍点 | 原本の強調（傍点付き）を `text-emphasis` で再現しています |
| 比較表 | 昭和OS／令和OSの20項目。スマホでは項目ごとの積み上げ表示に自動で切り替わります |
| 章末カード | LIFE SHIFT ／ SHIFT POINT ／ 今日の問い の3枚組を各章末に収録 |
| 対応端末 | iOS Safari / Android Chrome / PC各ブラウザ。375px幅から横スクロールなしで読めます |

※ 検索エンジンに載せたくない場合は `index.html` の `<head>` に
`<meta name="robots" content="noindex">` を1行足してください。

## 更新方法

元データは共有フォルダの `LIFESHIFT教科書_A4横書き　最新.pdf.build.pdf`。
差し替える場合は `work/source.pdf` を置き換えて、`work/` で次を実行します。

```bash
python parse.py
python build_web.py
python audit.py
```
