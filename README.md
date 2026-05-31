# ryoma-lab

実験的 Web ツール置き場。単一 HTML で完結する小さな道具を、検証しながら少しずつ並べていくハブ。

公開: https://ryoma-lab.pages.dev

## 作っている人 / 発信

**中島 竜馬（Ryoma Nakajima）** — AIで有意義な暮らしを創る GTM エンジニア。
動画編集・AI まわりのツールづくりや実験を、各 SNS で発信しています。

[![X](https://img.shields.io/badge/X_(Twitter)-@ryoma__nakajima-000000?logo=x&logoColor=white)](https://x.com/ryoma_nakajima)
[![Instagram](https://img.shields.io/badge/Instagram-@ryoma__nakajima-E4405F?logo=instagram&logoColor=white)](https://instagram.com/ryoma_nakajima)
[![YouTube](https://img.shields.io/badge/YouTube-@ryoma__nakajima-FF0000?logo=youtube&logoColor=white)](https://www.youtube.com/@ryoma_nakajima)
[![Website](https://img.shields.io/badge/Web-ryoma--n.com-6E7681?logo=googlechrome&logoColor=white)](https://ryoma-n.com)

- 🌐 Web: <https://ryoma-n.com>
- 𝕏 (Twitter): <https://x.com/ryoma_nakajima>
- 📸 Instagram: <https://instagram.com/ryoma_nakajima>
- ▶️ YouTube: <https://www.youtube.com/@ryoma_nakajima>

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
