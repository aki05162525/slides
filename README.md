# Slides

複数の発表スライドを 1 リポジトリで管理する [Slidev](https://sli.dev/) プロジェクト。

## 構成

```
slides/
  shared/                     # 全デッキ共通のテンプレ（Slidev addon）
    styles/index.css          #   日本語の行間調整・太字見出し・反転(.invert)クラス
    components/               #   共通コンポーネント
  template/                   # 新しい発表を作るときの雛形（コピー元）
    slides.md                 #   addons: slidev-addon-shared を参照
    snippets/ , pages/        #   サンプル素材
  decks/                      # 実際の発表（ここに増やしていく。最初は空）
```

共通テンプレ（フォント・色・スタイル）は `shared/` の 1 か所だけ直せば全デッキに反映されます。

## 新しい発表を作る

1. `template/` を `decks/` 配下にコピー
   ```bash
   cp -r template decks/2026-07-my-talk
   ```
2. `decks/2026-07-my-talk/slides.md` の中身を書き換える
   （headmatter の `addons: [slidev-addon-shared]` はそのまま残す）
3. プレビュー
   ```bash
   pnpm dev decks/2026-07-my-talk/slides.md
   ```

## コマンド

```bash
pnpm install

pnpm dev    <path/to/slides.md>   # 編集しながらプレビュー
pnpm build  <path/to/slides.md>   # 静的サイトに書き出し
pnpm export <path/to/slides.md>   # PDF 出力

# 雛形そのものを確認したいとき
pnpm dev template/slides.md
```

## 反転（疑問・区切り）ページ

headmatter に `class: invert` を足すと暗背景＋白文字になります（`shared/styles/index.css` で定義）。

```yaml
---
layout: center
class: text-center invert
---

# 問いたいことをここに
```
