# Everything Claude Business

> Code を書く代わりに、ビジネスを設計する。テストで検証する代わりに、市場で検証する。

Claude Code の設定体系を **ビジネス設計・検証** に転用した設定集。
[everything-claude-code](https://github.com/affaan-m/everything-claude-code) の構造的エッセンスを、スタートアップ・新規事業の文脈に再構成。

## 思想: Business-Driven Development (BDD)

ソフトウェアにおける TDD がそうであるように、ビジネスにも「先に検証基準を決めてから動く」規律が必要。

```
TDD:        Red → Green → Refactor
BDD:        Hypothesis → Validate → Pivot
```

| claude-code | claude-business |
|---|---|
| コードを書く | ビジネスを設計する |
| テストで検証 | 市場で検証 |
| バグを修正 | 仮説を修正 |
| code-reviewer | devil-advocate |
| console.log 警告 | 根拠なき楽観 警告 |
| build が通らないとデプロイしない | 検証が通らないと次に進まない |

## 構成

```
everything-claude-business/
├── agents/          # 専門家エージェント（10種）
├── skills/          # 方法論・フレームワーク（9種）
├── commands/        # スラッシュコマンド（7種）
├── rules/           # 常に守るルール（5種）
├── hooks/           # 自動トリガー（3種）
├── contexts/        # モード切替（4種）
└── templates/       # 出力テンプレート（5種）
```

## クイックスタート

```bash
# 1. クローン
git clone https://github.com/your-name/everything-claude-business.git

# 2. .claude/ にコピー（プロジェクト単位で使う場合）
cp -r everything-claude-business/{agents,skills,commands,rules,contexts,templates} your-project/.claude/

# 3. Claude Code セッションで使う
cd your-project
claude
# → /research, /validate, /pitch 等のコマンドが使える
```

## 主要ワークフロー

### 1. 探索フェーズ
```
/research → market-researcher + competitor-analyst が動く
         → customer-profiler でペルソナ設計
         → devil-advocate が楽観バイアスを指摘
```

### 2. 検証フェーズ
```
/validate → lean-validator が最小検証を設計
          → experiment-card テンプレートで実験定義
          → mom-test スキルでインタビュー設計
```

### 3. 実行フェーズ
```
/pricing → pricing-strategist が価格戦略を設計
/pitch   → pitch-writer がピッチ資料を生成
/kill    → 撤退基準に照らして Go/No-Go 判断
```

## ルール体系

すべてのエージェントに適用される5つの不変ルール:

1. **Intellectual Honesty** — 都合の良い解釈を禁止
2. **Evidence-Based** — 根拠なき楽観を禁止
3. **Customer-First** — 顧客視点必須
4. **Cost-Conscious** — コスト意識
5. **Time-Boxing** — 期限厳守

## ライセンス

MIT
