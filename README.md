# markdown-docs

個人用のドキュメントを Markdown で管理するためのリポジトリです。

メモ、ガイド、チュートリアル、スライド原稿を 1 か所にまとめ、
フォーマットと文章品質のチェックをかけながら保守できるようにして
います。

## このリポジトリで管理するもの

- 普段使う Markdown の書き方や運用ルール
- 手順書や覚え書き
- 学習用のサンプル文書
- Marp を使ったスライド原稿

公開用サイトを生成するためのリポジトリではなく、Markdown ファイルを
継続的に整理・更新していくための個人用ストックとして使う想定です。

## docs 配下の役割

- `docs/README.md`: ドキュメント置き場の入口
- `docs/guides/`: 執筆ルールや運用ガイド
- `docs/tutorials/`: 基本操作やサンプル
- `docs/marp/`: Marp スライド関連の資料
- `themes/`: スライド用テーマなどの補助ファイル

## セットアップ

### 前提条件

- Node.js 16 以上
- npm

### インストール

```bash
npm install
```

依存関係をインストールすると、`simple-git-hooks` により pre-commit hook が
設定されます。コミット前には `npm run lint` が実行されます。

## 使い方

文書は主に `docs/` 配下に追加・編集します。整形や品質チェックの対象も
`docs/**/*.md` です。

```bash
# Markdown を整形
npm run format

# 整形結果をチェック
npm run format:check

# markdownlint + textlint を実行
npm run lint

# markdownlint + textlint を自動修正
npm run lint:fix
```

## 品質管理

このリポジトリでは、Markdown を書きっぱなしにせず、最低限の自動チェック
を入れています。

- Prettier: 体裁の統一
- markdownlint: Markdown 記法のチェック
- textlint: 日本語文章のチェック
- simple-git-hooks: pre-commit 時の lint 実行

## 編集メモ

- 追加する文書は `docs/` 配下に置く
- 既存の分類に合わない場合は、必要に応じてディレクトリを見直す
- スライドを書く場合は `docs/marp/` と `themes/` を使う
- 長文を書いたあとに `npm run lint:fix` を先に通すと差分を整理しやすい

## 関連ドキュメント

- [docs/README.md](docs/README.md)
- [docs/guides/writing-guide.md](docs/guides/writing-guide.md)
- [docs/tutorials/markdown-basics.md](docs/tutorials/markdown-basics.md)
- [docs/marp/README.md](docs/marp/README.md)
