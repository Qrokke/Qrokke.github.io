# Research Site — 運用メモ

Jekyll + GitHub Pages 製の個人研究ページ。プラグイン不要（GitHub Pages 標準ビルドのみ）で動きます。

## 公開手順

1. GitHub に **研究用アカウント**でリポジトリ `<account>.github.io` を作成（後述の分離方針を参照）
2. このフォルダの中身を push
3. Settings → Pages → Source: `main` ブランチを選択
4. `_config.yml` の `url:` を `https://<account>.github.io` に設定
   - プロジェクトページ（`<account>.github.io/reponame`）にする場合は `baseurl: "/reponame"` も設定

ローカル確認（任意）: `bundle install && bundle exec jekyll serve`

## 更新方法（3つの入口だけ覚えればOK）

| やりたいこと | 触るファイル |
|---|---|
| 論文を追加 | `_data/publications.yml` に1ブロック追記 |
| Newsを追加 | `_data/news.yml` に1ブロック追記 |
| 日記を書く | `_diary/YYYY-MM-DD-slug.md` を1ファイル作成 |

HTMLやレイアウトは触る必要がありません。

### 論文エントリの書き方

```yaml
- category: journal          # journal / international / domestic / poster / misc
  authors: "Asahi Kurokawa, ..."
  title: "Paper Title"
  venue: "Journal of Robotics and Mechatronics"
  year: 2026
  status: "to appear"        # 掲載されたら行ごと削除
  doi: 10.20965/jrm.2026.pXXXX   # DOIが出たら追記 → 自動でリンク化
  in_japanese: true          # 日本語論文なら。"(in Japanese)" が自動付与
```

- `doi:` は **`10.` から始まる素のDOIだけ**書く（`https://doi.org/` は自動付与）
- `pdf:` に著者版PDFのパスを書けば PDF チップも出ます（出版社の規定を確認のこと）

### 日記の書き方

```markdown
---
title: "タイトル"
date: 2026-07-08
tags: [experiment, fem]   # 省略可
---

本文（Markdown）
```

コメント欄・評価機能は一切実装していません（静的サイトなので読者は読むだけです）。
今後も giscus / utterances 等のコメントウィジェットは**追加しない**でください。

## 小説ポートフォリオとの分離方針（重要）

同一人物と辿れなくするため、技術的に以下を徹底してください。

1. **GitHubアカウントを完全に分ける。** 同一アカウントの別リポジトリでは、プロフィールページから両方が一覧できてしまうため不可。
2. 小説側アカウントは **別メールアドレスで登録**し、`git config user.email` / `user.name` もアカウントごとに切り替える（コミットログから紐づくため）。リポジトリごとに `git config --local` で設定するのが安全。
3. **アクセス解析・広告・フォント等の共通IDを使わない。** 同じ Google Analytics ID や AdSense ID を両サイトに入れると機械的に紐づけられます（本サイトには解析タグを入れていません）。
4. **カスタムドメインを共有しない。** 同一ドメインのサブドメイン同士は当然辿れます。
5. 相互リンク・同一の画像素材・同一のファビコン・特徴的な文体の使い回しを避ける。
6. 小説側では本名・所属・ORCID・研究語彙（haptics等）を出さない。

この6点を守れば、公開情報から相互に到達する経路はなくなります。
