# ryoma-lab

実験的 Web ツール置き場。単一 HTML で完結する小さな道具を、検証しながら少しずつ並べていくハブ。

公開: https://ryoma-lab.pages.dev

## 構成

```
.
├── index.html         # ホーム（ハブ）。各ツールへのリンク一覧
├── telop/
│   └── index.html     # テロップアニメーション プリセット集（60+）
├── video-effects/
│   └── index.html     # 映像エフェクト大全（5,500+ 種・5 系統の検索リファレンス）
└── effects-playground/
    └── index.html     # エフェクト・プレイグラウンド（288 種を WebGL 実装・スライダー調整）
```

各ツールは `<tool>/index.html` の 1 ファイルで完結する。ホーム (`index.html`) のカードからリンクで開く。

## ツール追加の手順

1. `mkdir <tool> && cp your-tool.html <tool>/index.html`
2. `index.html` の `.grid` 内にカードを 1 枚追加（`href="./<tool>/"`）
3. commit & push → Cloudflare Pages が自動デプロイ（または `wrangler pages deploy . --project-name ryoma-lab`）

## デプロイ

Cloudflare Pages。

- ハブ: https://ryoma-lab.pages.dev
- telop 単体の短縮配布 URL: https://telop.pages.dev （`telop/` を直デプロイ。ハブとは別プロジェクトだが中身は同一）

```sh
# ハブ全体
wrangler pages deploy . --project-name ryoma-lab --branch main

# telop 単体（短縮 URL 用）
wrangler pages deploy telop --project-name telop --branch main
```
