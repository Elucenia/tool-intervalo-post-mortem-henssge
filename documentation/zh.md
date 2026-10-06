<!-- ELUCENIA technical documentation · intervalo-post-mortem-henssge · zh · no clinical/professional/rights approval -->

# 根据体温估算死后间隔（Henssge）

[条件、来源与许可](https://elucenia.org/zh/tools/intervalo-post-mortem-henssge)

## 使用方法

在门户中使用工具，或通过本地 HTTP 服务器打开 index.html。选择语言，填写各字段，然后计算。

## 输入与单位

### 深部直肠温度

`tr`

°C · 范围: 5–42

### 环境温度（现场平均值）

`ta`

°C · 范围: -10–35

### 体重

`peso`

kg · 范围: 1–250

### 体重校正系数（1.0 = 裸体、干燥、静止空气中）

`fc`

选填 · 范围: 0.3–3

## 方法版本

Henssge：Otatsume等人2024年的技术方程（不高于23 °C：5/4与1/4；高于23 °C：10/9与1/9）；数值二分法；未完整阅读1988年原文

## 已记录的公式

标准化温度: Q = (T直肠 − T环境) / (37.2 − T环境).

环境温度至 23 °C: Q = 1.25 × eBt − 0.25 × e5Bt. 环境温度高于 23 °C: Q = (10/9) × eBt − (1/9) × e10Bt.

B = −1.2815 × (因子 × 体重)−0.625 + 0.0284. 时间t（小时）通过数值求解方程得出，与列线图方法一致。

## 限制与适用人群

Henssge估计依赖冷却模型及直肠温度测量，同时需要该版本规定的环境条件与校正因子。它并非确切死亡时间。数值解和不确定性须与个案条件及来源一致；原始摘要不足以确认全部标准。 本版本明确采用Otatsume及同事2024年的技术方程，已阅读论文第2页的方程1–4：环境温度不高于23 °C时A = 5/4，高于23 °C时A = 10/9。系数10/9以分数形式使用，不以1.11代替。B项、用于体重的系数、输入范围和数值求解方法保持本界面的原有实现。2019年论文印有1.11和0.11，并采用不同的环境温度边界及校正系数位置；该版本作为比较记录，不能证明完全等价。未完整阅读1988年原文。本次核对不认可个体死亡时间、校正系数选择、不确定性、置信区间或司法鉴定用途。

## 参考文献

- [Henssge C. Death time estimation in case work. I. The rectal temperature time of death nomogram. Forensic Sci Int, 1988.](https://doi.org/10.1016/0379-0738(88)90168-5)

- [Henssge C, Madea B. Estimation of the time since death in the early post-mortem period. Forensic Sci Int, 2004.](https://doi.org/10.1016/j.forsciint.2004.04.051)

- [Schweitzer W, Thali MJ. Computationally approximated solution for the equation for Henssge's time of death estimation. BMC Med Inform Decis Mak, 2019.](https://doi.org/10.1186/s12911-019-0920-y)

- [Otatsume et al.2024, technical equations1–4, printedp2; not full original1988 nomogram review.](https://miyazaki-u.repo.nii.ac.jp/record/2000525/files/1-s2.0-S1752928X2300152X-main.pdf)

## 复现技术测试

在此仓库的根目录中运行 node test.cjs，以重复已记录的合成案例。原始输入、预期结果和容差保持不变。技术测试不构成临床验证。

```sh
node test.cjs
```

tool.json 包含来源、版本和审查范围。examples.json 保留合成输入与预期结果；results.json 记录实际得到的结果。

[记录与参考文献](../tool.json) · [JavaScript代码](../calculator.js) · [参考案例](../examples.json) · [results.json](../results.json)

## 审查与使用条件

尚未开展独立临床审查。

此界面为自主编写的翻译，并非官方或认证版本。尚未完成独立临床审查、专业语言审查或工具权利授权。

公式或分类结果。解释、处理及适用性须结合专业评估和所选来源。

## 许可与署名

Apache-2.0 仅适用于 ELUCENIA 代码。工具、出版物、翻译和数据的权利仍归各自权利人所有。请保留 LICENSE 和 NOTICE。

ELUCENIA · Felipe Guedes · Copyright © 2026

## 已记录的结果

以下信息保留该方法对合成示例的输出，不构成独立的临床验证。

### 1

约 10 小时前死亡（模型的点估计）

| 结果详情 | |
| --- | --- |
| 所用方程 | 环境最高至 23 °C (1,25 / 0,25) |
| 校正后体重（因子 × 体重） | 70.0 kg |
| 冷却常数 B | -0.0617 h⁻¹ |
| 标准化温度 Q | 0.663 |

在标准条件（因子 1）下，该方法最窄的 95% 置信区间为 ±2,8 h。使用校正因子、较长时间间隔或环境不稳定时，界限更宽：请阅读原始列线图中的界限。


### 2

约于 6 h 1 min 前死亡（模型点估计）

| 结果详情 | |
| --- | --- |
| 所用方程 | 环境温度高于23 °C（10/9 / 1/9） |
| 校正后体重（因子 × 体重） | 80.0 kg |
| 冷却常数 B | -0.0544 h⁻¹ |
| 标准化温度 Q | 0.797 |

在标准条件（因子 1）下，该方法最窄的 95% 置信区间为 ±2,8 h。使用校正因子、较长时间间隔或环境不稳定时，界限更宽：请阅读原始列线图中的界限。

