# security notes

GitHub Pages 用の、CTF・セキュリティ関連の Writeup を掲載するシンプルな Jekyll サイトです。通常の更新では Markdown ファイルだけを追加・編集します。

## 作成した構成

- `_posts/`: Writeup の Markdown
- `_tools/`: Tool ページの Markdown
- `_layouts/`: 共通レイアウト
- `assets/css/style.css`: サイト共通のスタイル
- `index.md`, `writeups.md`, `tools.md`, `about.md`: 各ページ

## Writeup を追加する

`_posts/YYYY-MM-DD-article-name.md` を追加します。

```md
---
layout: post
title: "Example CTF"
date: 2026-09-12
tags:
  - web
  - crypto
tools:
  - Burp Suite
  - nmap
---

## Writeup

ここに本文を書きます。
```

記事は `/writeups/`、トップページの Recent Writeups に自動で表示されます。`tools` は `_tools/` に登録した `title` と完全に同じ名前を指定してください。該当ツールのページに「Used in」として記事が自動表示されます。

## Tool を追加する

`_tools/tool-name.md` を追加します。

```md
---
layout: tool
title: "Burp Suite"
category: "Web"
---

ツールの説明を Markdown で書きます。
```

ツールは `/tools/` に自動で表示されます。

## Writeup・Tool に画像を追加する

画像は、記事ごと・ツールごとの `screenshots` フォルダに置きます。画像ファイルも GitHub に push すれば、そのまま公開されます。

```text
assets/images/
  writeups/
    example-ctf/
      screenshots/
        request.png
        result.png
  tools/
    burp-suite/
      screenshots/
        repeater.png
```

Markdown の front matter にフォルダと画像一覧を指定すると、ページ下部にスクリーンショット一覧が自動表示されます。

```md
image_dir: /assets/images/writeups/example-ctf/screenshots
screenshots:
  - file: request.png
    alt: "HTTP request"
    caption: "Target request"
  - file: result.png
    alt: "Response showing the result"
```

画像を本文中の好きな場所に表示することもできます。GitHub Pages のプロジェクトサイトでも正しいURLになるよう、次の形式を使います。

```md
![HTTP request]({{ '/assets/images/writeups/example-ctf/request.png' | relative_url }})
```

Tool でも同じ仕組みを使えます。`image_dir` のパスを `assets/images/tools/<tool-name>/screenshots` に変更してください。

## GitHub Pages で公開する

1. このリポジトリを GitHub に push します。
2. GitHub のリポジトリ画面で **Settings** → **Pages** を開きます。
3. **Build and deployment** の Source で **Deploy from a branch** を選び、公開するブランチ（通常は `main`）と `/(root)` を指定して保存します。
4. 公開 URL が表示されたら完了です。

`_config.yml` は GitHub Pages 標準の Jekyll 環境で動作する構成です。
