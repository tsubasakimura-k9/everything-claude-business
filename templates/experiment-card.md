# Experiment Card / 実験カード

> One experiment tests one assumption. Keep it small, fast, and falsifiable.
> Inspired by TDD's Arrange-Act-Assert structure: Hypothesis-Method-Criteria.

**Status Markers / ステータスマーカー:**
- `[A]` = Assumption (未検証の仮定)
- `[E]` = Evidence-based (エビデンスあり)
- `[?]` = Unknown (不明 -- 調査が必要)

---

## メタデータ / Metadata

| Field | Value |
|-------|-------|
| **実験名 / Experiment Name** | [FILL: descriptive name for this experiment] |
| **作成日 / Date Created** | [FILL: YYYY-MM-DD] |
| **完了日 / Date Completed** | [FILL: YYYY-MM-DD] |
| **責任者 / Owner** | [FILL: who is running this experiment] |
| **関連キャンバスブロック / Related Canvas Block** | [FILL: Problem / Customer Segments / UVP / Solution / Channels / Revenue / Cost / Metrics / Unfair Advantage] |
| **実験番号 / Experiment Number** | [FILL: #XXX] |

---

## 仮説 / Hypothesis (Arrange)

> Write a falsifiable statement. If you cannot imagine a result that would prove you wrong, this is not a good hypothesis.

**We believe that** [FILL: specific customer segment]
**experiences** [FILL: specific problem/need]
**and would** [FILL: specific behavior: pay, sign up, use, share]
**if we** [FILL: specific action we take].

**テストする最もリスクの高い仮定 / Riskiest Assumption Being Tested:**
> [FILL: the single assumption this experiment is designed to validate or invalidate]

---

## 検証方法 / Method (Act)

**実験タイプ / Experiment Type:**
- [ ] Customer Interview / 顧客インタビュー (Problem validation)
- [ ] Landing Page / Smoke Test / LP・スモークテスト (Demand validation)
- [ ] Concierge / Wizard of Oz / コンシェルジュ型 (Solution validation)
- [ ] Prototype / Usability Test / プロトタイプ (UX validation)
- [ ] A/B Test / ABテスト (Optimization)
- [ ] Pre-sale / Letter of Intent / 事前販売・意向表明書 (Willingness to pay)
- [ ] Other / その他: [FILL: description]

**手順 / Steps:**
1. [FILL: first step]
2. [FILL: second step]
3. [FILL: third step]

**サンプルサイズ / Sample Size / Reach:**
> [FILL: how many people/data points? e.g., "Interview 10 freelance designers" or "Drive 200 visitors to landing page"]

**タイムボックス / Time Box:** [FILL: ___ days/weeks]
> Hard deadline. If not completed by this date, evaluate why and decide: extend, modify, or kill.

**予算 / Budget:** [FILL: $___]
> Include time cost. If "free," still estimate hours spent.

---

## 成功基準 / Success Criteria (Assert)

> Define BEFORE running the experiment. Do not move the goalposts after.

**成功 / Success (GO):**
> [FILL: quantitative threshold that would validate the hypothesis]

**判断保留 / Inconclusive (LEARN MORE):**
> [FILL: range that means we need more data or a different experiment design]

**失敗 / Failure (PIVOT/KILL):**
> [FILL: quantitative threshold that would invalidate the hypothesis]

---

## データ収集 / Data Collection

**方法 / Method:**
> [FILL: how will you capture data? e.g., spreadsheet, analytics tool, interview notes, Stripe dashboard]

**生データの保存先 / Raw Data Location:**
> [FILL: link or path to raw data]

---

## 結果 / Results

**完了日 / Date Completed:** [FILL: YYYY-MM-DD]

**定量的結果 / Quantitative Result:**
> [FILL: the numbers. Be precise.]

**定性的観察 / Qualitative Observations:**
> [FILL: surprises, patterns, quotes, edge cases]

**判定 / Verdict:**
- [ ] SUCCESS / 成功 -- Hypothesis validated
- [ ] INCONCLUSIVE / 判断保留 -- Need more data
- [ ] FAILURE / 失敗 -- Hypothesis invalidated

---

## 学び / Learning

> What did we learn that we did not know before? Write this even (especially) if the experiment failed.

**重要な洞察 / Key Insight:**
> [FILL: one sentence summary of the most important thing learned]

**予期しなかった発見 / Unexpected Findings:**
> [FILL: anything surprising that might open new directions]

**改善点 / What Would We Do Differently?**
> [FILL: if we ran this experiment again, what would we change about the design?]

---

## 次のアクション / Next Action

Based on the result, our next step is:

- [ ] **深掘り / Double Down** -- Run a deeper experiment on the same assumption
- [ ] **次へ / Move On** -- This assumption is validated; test the next riskiest assumption
- [ ] **ピボット / Pivot** -- Evidence suggests a different direction; update the canvas
- [ ] **中止 / Kill** -- Fundamental assumption invalidated; run /kill evaluation

**次の実験 / Specific Next Experiment:**
> [FILL: name or brief description of what comes next]

---

## 監査証跡 / Audit Trail

| Date | Event | Notes |
|------|-------|-------|
| [FILL] | Created | |
| [FILL] | Started | |
| [FILL] | Data point collected | |
| [FILL] | Completed | |
| [FILL] | Reviewed | |

---

## 記入例 / Filled Example

> Scenario: Testing whether Japanese SMB accountants will use AI receipt scanning

| Field | Value |
|-------|-------|
| **実験名** | 経理担当者の領収書手入力時間調査 |
| **作成日** | 2026-01-15 |
| **完了日** | 2026-01-29 |
| **責任者** | 木村 |
| **関連キャンバスブロック** | Problem |
| **実験番号** | #001 |

**仮説 / Hypothesis:**
**We believe that** 従業員10-50名の中小企業の経理担当者
**experiences** 月次の領収書入力に月40時間以上を費やす問題
**and would** 月額9,800円を支払って
**if we** スマホ撮影だけで自動仕訳できるツールを提供する.

**テストする最もリスクの高い仮定:** 「経理担当者が実際に月40時間以上を手入力に費やしている」

**実験タイプ:** Customer Interview / 顧客インタビュー

**手順:**
1. 税理士パートナー経由で中小企業の経理担当者10名にアポ取得
2. 30分の半構造化インタビュー（Mom Test形式）実施
3. 「先月の経費精算、どうやりましたか？」から始め、具体的な時間・手順を聞き出す

**サンプルサイズ:** 10名の経理担当者（業種を分散）
**タイムボックス:** 2週間
**予算:** 交通費・謝礼で約5万円

**成功基準:**
- **成功 (GO):** 10名中7名以上が月20時間以上の手入力時間を報告
- **判断保留:** 10名中4-6名が月20時間以上を報告
- **失敗 (PIVOT/KILL):** 10名中3名以下が月20時間以上を報告

**結果:**
- 10名中8名が月25-50時間の手入力を報告 [E]
- 3名は既にfreeeのOCR機能を試したが精度に不満で手入力に戻った
- インボイス制度対応で作業量が約1.5倍に増えたという声が複数

**判定:** SUCCESS

**重要な洞察:** 問題は想定以上に深刻。特にインボイス制度対応が追い風。ただし既存OCR（freee等）との差別化が鍵。

---

## この記入テンプレートの使い方 / How to Fill This Template

1. **Start with the hypothesis**: If you cannot write a clear, falsifiable hypothesis, you are not ready to experiment.
2. **Define success criteria BEFORE running**: This prevents moving the goalposts after seeing results.
3. **One assumption per experiment**: Do not try to test multiple things at once.
4. **Time box everything**: If the experiment drags on, it's a sign the design needs fixing.
5. **Fill the Learning section even on failure**: Failed experiments are only wasted if you don't capture what you learned.
6. **Link to canvas**: Every experiment should trace back to a specific Lean Canvas block.
