# zenn-content

[Zenn](https://zenn.dev/syommy_program) の配信用リポジトリ。GitHub 連携により `main` への push で自動デプロイされる。

参考: [Zenn CLI の使い方](https://zenn.dev/zenn/articles/zenn-cli-guide)

## 執筆フロー

原本は Vault（プライベートリポジトリ）側で管理し、このリポジトリは配信専用。

```text
1. Vault: 03_Content/Drafts/記事ネタ.md からネタを選ぶ
2. Vault: 03_Content/Drafts/zenn/ に下書きを書く（レビュー・推敲）
3. ここ:  articles/{slug}.md に frontmatter を付けて変換コピー（published: false）
4. ここ:  npx zenn preview で表示確認（Mermaid・コードブロック）
5. ここ:  published: true にして main へ push → 自動デプロイ
6. Vault: Published/ に公開記録、記事ネタ.md のステータス更新
```

## コマンド

```bash
npx zenn new:article   # 新しい記事の雛形
npx zenn preview       # http://localhost:8000 でプレビュー
```

## frontmatter の型

```yaml
---
title: "記事タイトル"
emoji: "🔐"
type: "tech"        # tech / idea
topics: ["macos", "launchd"]   # 最大5個
published: false    # 公開時に true
---
```
