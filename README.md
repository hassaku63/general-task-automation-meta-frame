# タスク自動化メタフレームワーク

あらゆる業務自動化を体系的に設計・実装するための「メタフレームワーク」。
特定の業務ではなく、**業務自動化そのものを効率化する仕組み**。

## 核心思想: 半自動化

AI が得意な部分を自動化し、人間の判断が必要な部分は人間に委ねる。
SPEC.md の「自動化の境界」セクションで AI/人間の役割分担を常に明示する。

## ディレクトリ構成

```
task-automation/
├── CLAUDE.md              # Claude への行動指示・コンベンション
├── tasks/
│   ├── _template/         # 4文書テンプレート (PLAN/SPEC/TODO/KNOWLEDGE)
│   └── {task-name}/       # 各タスクのワークスペース
├── snippets/              # 再利用可能なスクリプト・コード片
├── docs/                  # 調査メモ・参考資料
└── attendance/            # 勤怠関連
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

## 4文書テンプレート

| ファイル | 役割 |
|----------|------|
| PLAN.md | ゴール・課題の言語化 |
| SPEC.md | 仕様の精緻化（自動化の境界を含む） |
| TODO.md | フェーズ分けされたタスク管理 |
| KNOWLEDGE.md | 知見・ハマりポイントの蓄積 |

## 参考

- [Claude Codeですべての日常業務を爆速化しよう！](https://qiita.com/minorun365/items/114f53def8cb0db60f47) - 本フレームワークの着想元
