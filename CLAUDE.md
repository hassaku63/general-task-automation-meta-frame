# タスク自動化メタフレームワーク

## 目的
あらゆる業務自動化を体系的に設計・実装するための「メタフレームワーク」。
特定の業務ではなく、**業務自動化そのものを効率化する仕組み**。

## 核心思想: 半自動化
- AI が得意な部分を自動化し、人間の判断が必要な部分は人間に委ねる
- SPEC.md の「自動化の境界」セクションで AI/人間の役割分担を常に明示する
- 判断ポイントでは必ず人間に確認を求める

## ディレクトリ構成

```
task-automation/
├── CLAUDE.md              # この文書
├── tasks/
│   └── {task-name}/       # 各タスクのワークスペース (PLAN/SPEC/TODO/KNOWLEDGE)
├── snippets/              # 再利用可能なスクリプト・コード片
├── docs/                  # 調査メモ・参考資料
└── attendance/            # (既存) 勤怠関連

~/.claude/skills/new-task/
├── SKILL.md               # タスクスキャフォールドスキル
└── templates/             # 4文書テンプレート (PLAN/SPEC/TODO/KNOWLEDGE)
```

## ワークフロー

```
/new-task {name}  →  PLAN.md 作成(ヒアリング)
                  →  SPEC.md 精緻化(自動化の境界を議論)
                  →  TODO.md 生成(タスク分解)
                  →  /task-implement {name} で実装
                  →  /task-review {name} でレビュー
                  →  KNOWLEDGE.md に学びを記録
```

## コンベンション
- タスク名はケバブケース (`expense-report`, `attendance-automation`)
- 各タスクは `tasks/{task-name}/` に4文書を配置
- 再利用可能なコード片は `snippets/` に切り出す
- 調査結果は `docs/` に蓄積
- 日本語で記述する（コード中のコメント・変数名は英語可）
