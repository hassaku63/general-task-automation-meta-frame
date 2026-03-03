# setup: 環境セットアップスキル

リポジトリの初回セットアップを行う。
`/setup` を実行するだけで、必要なスキルをユーザー環境にコピーする。

## 使い方
```
/setup
```

## 実行手順

### 1. スキルのインストール

対象スキル: `task-implement`, `task-review`

各スキルについて以下を実行する:

1. リポジトリのルートディレクトリを特定する（CLAUDE.md が存在するディレクトリ）
2. `~/.claude/skills/{skill-name}` が既に存在するか確認する
   - 存在しない → そのままコピー
   - 存在する → リポジトリ側の内容と差分を確認し、差分があればユーザーに上書きするか確認する。差分がなければ「既に最新です」と報告してスキップ
3. `~/.claude/skills/` ディレクトリが存在しない場合は作成する
4. ファイルをコピーする:
   ```bash
   cp -r {リポジトリルート}/skills/task-implement ~/.claude/skills/task-implement
   cp -r {リポジトリルート}/skills/task-review ~/.claude/skills/task-review
   ```

### 2. 結果報告

セットアップ結果を報告する:

- コピーしたファイルの一覧
- `/task-implement` と `/task-review` が使えるようになったこと

### 注意事項

- `~/.claude/skills/` に既存のファイルがある場合は、差分を確認してから操作する
- スキルを更新したい場合は `/setup` を再実行する（リポジトリ側が正本）
