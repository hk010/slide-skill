---
marp: true
theme: custom
paginate: true
---

<!-- _class: cover -->

# OpenAI GPTモデルの進化

GPT-1 から GPT-5 まで
2026-03-12

---

## GPTモデル 年表概要

- **2018年** — GPT-1: トランスフォーマーによる生成型事前学習の幕開け
- **2019年** — GPT-2: 安全性懸念から段階的公開された流暢な文章生成モデル
- **2020年** — GPT-3: 175Bパラメータのスケールで「few-shot学習」を実現
- **2022年** — GPT-3.5 / ChatGPT: RLHFを取り入れ対話AIが一般公開
- **2023年** — GPT-4: テキスト＋画像のマルチモーダル対応と高度な推論
- **2025年** — GPT-5: 統合マルチモーダル・自動ルーティング・大幅幻覚減少

> GPTシリーズは2018年から2025年にかけてパラメータ数・能力・安全性の面で急速に進化した。

---

## GPT-1（2018年）

- **発表**: 2018年（OpenAI初の大規模言語モデル）
- **パラメータ数**: <span style="color: #2563EB; font-weight: bold;">1億1700万（117M）</span>
- **アーキテクチャ**: Transformerへの生成的事前学習を初めて適用
- **特徴**:
  - 教師なし事前学習 → タスク別ファインチューニングという<span style="color: #2563EB; font-weight: bold;">2段階手法</span>を確立
  - 自然言語の構造・パターンを大量テキストから学習
  - 当時の主要NLPベンチマークで最高水準を記録

> GPT-1はTransformerを使った「事前学習→微調整」パラダイムを初めて実証した先駆的モデルである。

---

## GPT-2（2019年2月）

- **発表**: <span style="color: #2563EB; font-weight: bold;">2019年2月</span>（フルモデルは同年11月に段階公開）
- **パラメータ数**: <span style="color: #2563EB; font-weight: bold;">15億（1.5B）</span>（GPT-1の約13倍）
- **学習データ**: WebText（800万件の高品質Webページ）
- **特徴**:
  - ゼロショット学習に対応し、明示的な訓練なしにタスクを実行
  - 複数段落にわたる文脈の一貫した文章生成を実現
  - 誤情報生成リスクを懸念し、OpenAIが<span style="color: #2563EB; font-weight: bold;">段階的リリース</span>を初採用

> GPT-2はその流暢な文章生成能力が社会問題化し、AI安全性に関する世界的議論の端緒となった。

---

## GPT-3（2020年5月）

- **発表**: <span style="color: #2563EB; font-weight: bold;">2020年5月28日</span>（API公開: 2020年6月11日）
- **パラメータ数**: <span style="color: #2563EB; font-weight: bold;">1750億（175B）</span>（GPT-2の約117倍）
- **学習データ**: Common Crawl・WebText2・書籍・Wikipediaを混合
- **特徴**:
  - 「<span style="color: #2563EB; font-weight: bold;">Few-Shot学習</span>」を実現：数例を示すだけで多様なタスクに対応
  - 文章作成・Q&A・コード生成など幅広いタスクで高精度を達成
  - LLM（大規模言語モデル）時代の到来を象徴するパラダイムシフト

> GPT-3はスケールアップによるfew-shot学習能力で、ファインチューニングなしに多用途に対応できることを証明した。

---

## GPT-3.5 / ChatGPT（2022年）

- **発表**: GPT-3.5系: 2022年3月 / ChatGPT: <span style="color: #2563EB; font-weight: bold;">2022年11月30日</span>
- **パラメータ数**: 非公開
- **特徴**:
  - <span style="color: #2563EB; font-weight: bold;">RLHF（人間のフィードバックによる強化学習）</span>を導入
  - 対話フローへの最適化・不適切リクエストの拒否能力を向上
  - ChatGPTとして公開後、5日間で100万ユーザー獲得
  - 2023年2月には<span style="color: #2563EB; font-weight: bold;">史上最速</span>で月間ユーザー1億人を突破

> GPT-3.5はRLHFにより対話型AIの実用性を大幅に高め、AIを一般社会に広めた歴史的転換点となった。

---

## GPT-4（2023年3月）

- **発表**: <span style="color: #2563EB; font-weight: bold;">2023年3月14日</span>
- **パラメータ数**: 非公開
- **特徴**:
  - <span style="color: #2563EB; font-weight: bold;">マルチモーダル対応</span>: テキストと画像の両方を処理・理解
  - 推論能力・事実正確性・安全性を大幅強化
  - 各種専門試験（司法試験・医師試験等）で上位成績を達成
  - Microsoft Copilot・GitHub Copilot・Khan Academy等に統合
- **GPT-4o** (2024年5月): テキスト・画像・音声のリアルタイム統合処理を実現

> GPT-4はマルチモーダル能力と高度な推論で、AIの産業・教育への本格的な組み込みを加速させた。

---

## GPT-5（2025年8月）

- **発表**: <span style="color: #2563EB; font-weight: bold;">2025年8月7日</span>
- **コンテキスト**: ChatGPT最大256K・API最大400Kトークン
- **特徴**:
  - **自動ルーティング**: タスクに応じ高速モデル/推論モデルを自動選択
  - テキスト・画像・音声・動画のネイティブ統合処理
  - 幻覚（ハルシネーション）をGPT-4o比で<span style="color: #2563EB; font-weight: bold;">約45%削減</span>
  - 数学(AIME 2025: 94.6%)・コーディング(SWE-bench: 74.9%)でSoTA達成
  - 全ChatGPTユーザーに<span style="color: #2563EB; font-weight: bold;">無料提供</span>（Plusは高利用上限、Proは無制限）

> GPT-5は高速推論と深い思考を1モデルに統合し、精度・マルチモーダル・エージェント能力で前世代を大きく超えた。

---

## GPT各モデル比較まとめ

| モデル | 発表年月 | パラメータ数 | 主な革新 |
|--------|---------|------------|---------|
| GPT-1 | 2018年 | 117M | 事前学習＋ファインチューニング |
| GPT-2 | 2019年2月 | 1.5B | ゼロショット学習・安全性議論 |
| GPT-3 | 2020年5月 | 175B | Few-Shot学習・LLM時代の幕開け |
| GPT-3.5 | 2022年11月 | 非公開 | RLHF・ChatGPT公開 |
| GPT-4 | 2023年3月 | 非公開 | マルチモーダル・高度推論 |
| GPT-5 | 2025年8月 | 非公開 | 統合マルチモーダル・自動ルーティング |

> GPTシリーズは規模・学習手法・安全性・マルチモーダル性の面で一貫して進化し続けている。

---

## 参考文献

- [GPT Version Timeline: From GPT-1 to GPT-5.2 - Times of AI](https://www.timesofai.com/industry-insights/gpt-version-timeline/) — 各GPTモデルの発表日・パラメータ数・主要特徴を確認
- [Introducing GPT-5 | OpenAI](https://openai.com/index/introducing-gpt-5/) — GPT-5の公式発表・機能詳細を確認
- [GPT-5 - Wikipedia](https://en.wikipedia.org/wiki/GPT-5) — GPT-5の発表日（2025年8月7日）・スペックを確認
- [GPT-3 - Wikipedia](https://en.wikipedia.org/wiki/GPT-3) — GPT-3の発表日・パラメータ数・特徴を確認
- [The Complete History of OpenAI Models | Data Science Dojo](https://datasciencedojo.com/blog/the-complete-history-of-openai-models/) — GPT-1〜GPT-4の歴史的経緯を確認

> 本資料の参考文献一覧

---

<!-- _class: closing -->

<div class="logo-box">LOGO</div>
