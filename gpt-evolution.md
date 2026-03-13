---
marp: true
theme: custom
paginate: true
---

<!-- _class: cover -->

# OpenAI GPTモデルの進化
## GPT-1 から GPT-5 まで

2026-03-13

---

## GPTとは？

- **GPT**（Generative Pre-trained Transformer）はOpenAIが開発する大規模言語モデルのシリーズ
- **Transformer**アーキテクチャをベースに、大量のテキストデータで事前学習
- 2018年の初代GPT-1から、わずか<span style="color: #2563EB; font-weight: bold;">7年</span>でGPT-5まで急速に進化
- 各世代でパラメータ数・能力・安全性が大幅に向上

<svg width="580" height="100">
  <rect x="10" y="30" width="80" height="40" rx="6" fill="#4A5568"/>
  <text x="50" y="55" text-anchor="middle" fill="white" font-size="13">GPT-1</text>
  <text x="103" y="55" text-anchor="middle" fill="#AAAAAA" font-size="20">→</text>
  <rect x="120" y="30" width="80" height="40" rx="6" fill="#4A5568"/>
  <text x="160" y="55" text-anchor="middle" fill="white" font-size="13">GPT-2</text>
  <text x="213" y="55" text-anchor="middle" fill="#AAAAAA" font-size="20">→</text>
  <rect x="230" y="30" width="80" height="40" rx="6" fill="#4A5568"/>
  <text x="270" y="55" text-anchor="middle" fill="white" font-size="13">GPT-3/3.5</text>
  <text x="323" y="55" text-anchor="middle" fill="#AAAAAA" font-size="20">→</text>
  <rect x="340" y="30" width="80" height="40" rx="6" fill="#4A5568"/>
  <text x="380" y="55" text-anchor="middle" fill="white" font-size="13">GPT-4</text>
  <text x="433" y="55" text-anchor="middle" fill="#AAAAAA" font-size="20">→</text>
  <rect x="450" y="30" width="80" height="40" rx="6" fill="#2563EB"/>
  <text x="490" y="55" text-anchor="middle" fill="white" font-size="13">GPT-5</text>
</svg>

> GPTシリーズはAI技術の急速な進化を象徴するOpenAIの代表的なモデル群である。

---

## GPT-1：すべての始まり（2018年6月）

- **発表日**：<span style="color: #2563EB; font-weight: bold;">2018年6月</span>（論文「Improving Language Understanding by Generative Pre-Training」）
- **パラメータ数**：<span style="color: #2563EB; font-weight: bold;">1億1700万（117M）</span>
- TransformerアーキテクチャをNLP（自然言語処理）に初めて本格適用
- **教師なし事前学習 → 教師ありファインチューニング**という二段階学習を提唱
- BooksCorpus（約8億語）で事前学習し、当時の主要NLPベンチマークで最高水準を記録

> GPT-1はTransformerを用いた生成的事前学習の有効性を初めて示した、GPTシリーズの礎となるモデルである。

---

## GPT-2：テキスト生成の衝撃（2019年2月）

- **発表日**：<span style="color: #2563EB; font-weight: bold;">2019年2月14日</span>（フルモデルは同年11月に段階公開）
- **パラメータ数**：<span style="color: #2563EB; font-weight: bold;">15億（1.5B）</span> ― GPT-1の約13倍
- WebTextデータセット（約40GBのWebページ800万件）で学習
- タスク固有の学習なし（**ゼロショット**）で高品質なテキスト生成を実現
- 悪用リスクを懸念し、OpenAIが<span style="color: #2563EB; font-weight: bold;">段階的リリース</span>という慎重なアプローチを初採用
- フェイクニュース生成リスクが社会的に議論される契機となった

> GPT-2は高品質なテキスト生成能力でAIの社会的影響を初めて広く認識させ、段階的リリースという慎重なアプローチをとったモデルである。

---

## GPT-3：スケールが変えた常識（2020年5月）

- **発表日**：<span style="color: #2563EB; font-weight: bold;">2020年5月28日</span>（論文公開）、同年6月にAPIベータ公開
- **パラメータ数**：<span style="color: #2563EB; font-weight: bold;">1750億（175B）</span> ― GPT-2の約117倍
- Common Crawl等のWebデータ（約570GB）で学習
- **フューショット学習**（Few-shot learning）：少数例を示すだけで多様なタスクに対応
- 文章生成・質問応答・コード生成・翻訳などを高精度で実行
- GPT-3 APIを通じて多数のスタートアップ・サービスが誕生

> GPT-3は桁違いのスケールによってフューショット学習を実現し、LLM活用の産業的可能性を世界に示した転換点となるモデルである。

---

## GPT-3.5：対話AIの夜明け（2022年）

- **GPT-3.5 API公開**：<span style="color: #2563EB; font-weight: bold;">2022年3月</span>
- **ChatGPTとして一般公開**：<span style="color: #2563EB; font-weight: bold;">2022年11月30日</span>
- **RLHF**（人間のフィードバックによる強化学習）を導入し、指示への追従性を大幅改善
- 有害なコンテンツの拒否・倫理的配慮が向上
- ChatGPT公開後5日で**100万ユーザー**、2ヶ月で**1億ユーザー**を突破
- <span style="color: #2563EB; font-weight: bold;">史上最速</span>で1億ユーザーを獲得したコンシューマーアプリとなった

> GPT-3.5はRLHFによる人間との対話最適化でChatGPTを生み出し、生成AIを一般社会に普及させた歴史的なモデルである。

---

## GPT-4：マルチモーダルへの進化（2023年3月）

- **発表日**：<span style="color: #2563EB; font-weight: bold;">2023年3月14日</span>
- テキストだけでなく**画像も入力として理解**できるマルチモーダルモデル
- 複雑な推論・長文理解・コード生成の精度が大幅向上
- 安全性・信頼性の向上（ハルシネーション低減、有害コンテンツ抑制）
- <span style="color: #2563EB; font-weight: bold;">Microsoft Copilot・GitHub Copilot・Duolingo・Khan Academy</span>などに採用
- 後にGPT-4o（2024年5月・音声/画像/テキストのリアルタイム処理）へと発展

> GPT-4は画像理解を備えたマルチモーダル能力と高度な推論で、企業・教育・開発など幅広い分野のAI活用を加速させたモデルである。

---

## GPT-5：統合知性の時代（2025年8月）

- **発表日**：<span style="color: #2563EB; font-weight: bold;">2025年8月7日</span>
- テキスト・画像・音声・動画を統合的に処理する**フルマルチモーダル**
- **スマートルーティング**：問いの複雑さに応じて高速モードと推論モードを自動切替
- ハルシネーション率がGPT-4o比で<span style="color: #2563EB; font-weight: bold;">約45%低減</span>（Web検索有効時）
- コンテキストウィンドウ：ChatGPTで最大256Kトークン、APIで最大400Kトークン
- 数学(AIME 2025: 94.6%)・コーディング(SWE-bench: 74.9%)でSoTA達成
- 全ユーザーに無料提供（Plusは高使用上限、Proは無制限）

> GPT-5は推論・マルチモーダル・エージェント機能を統合した統一モデルで、AIがより自律的に複雑な課題を解決する新時代を切り開いた。

---

## GPTモデル進化の全体像

<svg width="580" height="150">
  <line x1="50" y1="125" x2="560" y2="125" stroke="#AAAAAA" stroke-width="2"/>
  <rect x="55" y="110" width="55" height="15" rx="3" fill="#4A5568"/>
  <text x="82" y="122" text-anchor="middle" fill="white" font-size="11">GPT-1</text>
  <text x="82" y="143" text-anchor="middle" fill="#333333" font-size="11">2018/6</text>
  <rect x="145" y="98" width="55" height="27" rx="3" fill="#4A5568"/>
  <text x="172" y="116" text-anchor="middle" fill="white" font-size="11">GPT-2</text>
  <text x="172" y="143" text-anchor="middle" fill="#333333" font-size="11">2019/2</text>
  <rect x="235" y="70" width="55" height="55" rx="3" fill="#4A5568"/>
  <text x="262" y="102" text-anchor="middle" fill="white" font-size="11">GPT-3</text>
  <text x="262" y="143" text-anchor="middle" fill="#333333" font-size="11">2020/5</text>
  <rect x="325" y="55" width="55" height="70" rx="3" fill="#4A5568"/>
  <text x="352" y="94" text-anchor="middle" fill="white" font-size="11">GPT-3.5</text>
  <text x="352" y="143" text-anchor="middle" fill="#333333" font-size="11">2022/11</text>
  <rect x="415" y="35" width="55" height="90" rx="3" fill="#4A5568"/>
  <text x="442" y="84" text-anchor="middle" fill="white" font-size="11">GPT-4</text>
  <text x="442" y="143" text-anchor="middle" fill="#333333" font-size="11">2023/3</text>
  <rect x="495" y="10" width="55" height="115" rx="3" fill="#2563EB"/>
  <text x="522" y="71" text-anchor="middle" fill="white" font-size="11">GPT-5</text>
  <text x="522" y="143" text-anchor="middle" fill="#333333" font-size="11">2025/8</text>
  <text x="30" y="128" text-anchor="middle" fill="#AAAAAA" font-size="10">能力</text>
</svg>

| モデル | 発表 | パラメータ | キーワード |
|--------|------|-----------|-----------|
| GPT-1 | 2018/6 | 117M | 事前学習＋ファインチューニング |
| GPT-2 | 2019/2 | 1.5B | ゼロショット・段階的リリース |
| GPT-3 | 2020/5 | 175B | フューショット・LLM時代の幕開け |
| GPT-3.5 | 2022/11 | 非公開 | RLHF・ChatGPT誕生 |
| GPT-4 | 2023/3 | 非公開 | マルチモーダル・高精度推論 |
| GPT-5 | 2025/8 | 非公開 | 統合知性・エージェント機能 |

> GPT-1から7年で、研究実証モデルからフルマルチモーダルの統合AIへと劇的に進化した。

---

## 参考文献

- [Introducing GPT-5 | OpenAI](https://openai.com/index/introducing-gpt-5/) — GPT-5の発表日・機能の確認
- [GPT-5 - Wikipedia](https://en.wikipedia.org/wiki/GPT-5) — GPT-5のベンチマーク・コンテキストウィンドウの確認
- [GPT-3 - Wikipedia](https://en.wikipedia.org/wiki/GPT-3) — GPT-3のパラメータ数・発表日の確認
- [Generative pre-trained transformer - Wikipedia](https://en.wikipedia.org/wiki/Generative_pre-trained_transformer) — GPT-1〜GPT-4の概要・歴史の確認
- [The Complete History of OpenAI Models | Data Science Dojo](https://datasciencedojo.com/blog/the-complete-history-of-openai-models/) — 各モデルの発表日・主要特徴の確認
- [OpenAI & ChatGPT Timeline | scriptbyai.com](https://www.scriptbyai.com/timeline-of-chatgpt/) — GPT各世代の年表確認

> 本資料の参考文献一覧

---

<!-- _class: closing -->

<div class="logo-box">LOGO</div>
