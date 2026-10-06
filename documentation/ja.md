<!-- ELUCENIA technical documentation · intervalo-post-mortem-henssge · ja · no clinical/professional/rights approval -->

# 体温による死後経過時間（Henssge）

[条件・出典・許諾](https://elucenia.org/ja/tools/intervalo-post-mortem-henssge)

## 使い方

ポータルでツールを使用するか、ローカルHTTPサーバー経由でindex.htmlを開いてください。言語を選択し、項目を入力して計算してください。

## 入力項目と単位

### 深部直腸温

`tr`

°C · 範囲: 5–42

### 周囲温度（現場の平均）

`ta`

°C · 範囲: -10–35

### 体重

`peso`

kg · 範囲: 1–250

### 体重補正係数（1.0 = 裸体・乾燥・静止空気）

`fc`

任意 · 範囲: 0.3–3

## 方法の版

Henssge：Otatsumeら2024年の技術的方程式（23 °C以下：5/4と1/4、23 °C超：10/9と1/9）；数値的二分法；1988年の原著は全文を読んでいない

## 記載された計算式

標準化温度: Q = (T直腸 − T周囲) / (37.2 − T周囲).

周囲温度が23 °C以下: Q = 1.25 × eBt − 0.25 × e5Bt. 周囲温度が23 °Cを超える: Q = (10/9) × eBt − (1/9) × e10Bt.

B = −1.2815 × (係数 × 体重)−0.625 + 0.0284. 時間t（時間）はノモグラムと同様に式を数値的に解いて求めます。

## 限界・対象集団

Henssgeの推定は、冷却モデルと直腸での測定に依存し、その版で定められた環境条件と補正係数を伴います。正確な死亡時刻ではありません。数値解と不確実性は、事例の条件と出典に対応する必要があります。原抄録だけでは、これらの基準の全てを確認できません。 この版ではOtatsumeら2024年の技術的方程式を明示しており、論文2ページの式1–4を読んだ。周囲温度が23 °C以下ではA = 5/4、23 °Cを超える場合はA = 10/9である。係数10/9は分数として用い、1.11に置き換えない。Bの項、体重に適用する係数、入力範囲、数値解法は、この画面の従来の実装を保持する。2019年の論文には1.11と0.11が印刷され、周囲温度の境界と補正係数の位置が異なる。その版は比較として記録し、完全な同等性の証明とはしない。1988年の原著は全文を読んでいない。この照合は個人の死亡時刻、補正係数の選択、不確実性、信頼区間、法医学的利用を承認しない。

## 参考文献

- [Henssge C. Death time estimation in case work. I. The rectal temperature time of death nomogram. Forensic Sci Int, 1988.](https://doi.org/10.1016/0379-0738(88)90168-5)

- [Henssge C, Madea B. Estimation of the time since death in the early post-mortem period. Forensic Sci Int, 2004.](https://doi.org/10.1016/j.forsciint.2004.04.051)

- [Schweitzer W, Thali MJ. Computationally approximated solution for the equation for Henssge's time of death estimation. BMC Med Inform Decis Mak, 2019.](https://doi.org/10.1186/s12911-019-0920-y)

- [Otatsume et al.2024, technical equations1–4, printedp2; not full original1988 nomogram review.](https://miyazaki-u.repo.nii.ac.jp/record/2000525/files/1-s2.0-S1752928X2300152X-main.pdf)

## 技術テストの再現

このリポジトリのルートディレクトリでnode test.cjsを実行すると、記録された合成ケースを再実行できます。元の入力、期待結果、許容誤差は保持されています。技術テストは臨床的検証を意味しません。

```sh
node test.cjs
```

tool.jsonには出典、版、確認範囲が記録されています。examples.jsonには合成入力と期待結果が保持され、results.jsonには実際に得られた結果が記録されています。

[記録・参考文献](../tool.json) · [JavaScriptコード](../calculator.js) · [参照ケース](../examples.json) · [results.json](../results.json)

## 確認状況と使用条件

独立した臨床レビューは実施されていません。

このインターフェースは独自に作成した翻訳であり、公式版や認証済みの版ではありません。独立した臨床レビュー、専門家による言語レビュー、評価尺度等の権利許諾の確認は実施されていません。

式または分類の結果です。解釈、対応、適用可能性は専門家による評価と選択した出典に依存します。

## ライセンスと帰属表示

Apache-2.0はELUCENIAのコードにのみ適用されます。評価尺度等、出版物、翻訳、データの権利は、それぞれの権利者に帰属します。LICENSEとNOTICEを保持してください。

ELUCENIA · Felipe Guedes · Copyright © 2026

## 記録された結果

以下の情報は、合成例に対する手法の出力を保持したものです。独立した臨床的検証を示すものではありません。

### 1

約10時間前の死亡（モデルの点推定）

| 結果の詳細 | |
| --- | --- |
| 使用した式 | 23 °Cまでの環境 (1,25 / 0,25) |
| 補正体重（係数 × 体重） | 70.0 kg |
| 冷却定数 B | -0.0617 h⁻¹ |
| 標準化温度 Q | 0.663 |

標準条件（係数1）では、この方法の最も狭い95%信頼区間は±2,8 hです。補正係数がある場合、長い間隔の場合、または環境が不安定な場合は、限界はより広くなります。元のノモグラムで限界を確認してください。


### 2

死亡は約6 h 1 min前（モデルの点推定）

| 結果の詳細 | |
| --- | --- |
| 使用した式 | 周囲温度が23 °Cを超える（10/9 / 1/9） |
| 補正体重（係数 × 体重） | 80.0 kg |
| 冷却定数 B | -0.0544 h⁻¹ |
| 標準化温度 Q | 0.797 |

標準条件（係数1）では、この方法の最も狭い95%信頼区間は±2,8 hです。補正係数がある場合、長い間隔の場合、または環境が不安定な場合は、限界はより広くなります。元のノモグラムで限界を確認してください。

