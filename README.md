# Bridge Suit Extremal Analysis: Probabilities of Longest & Shortest Suits

## 📊 Overview
This repository contains a complete computational analysis of extremal suit lengths in contract bridge hands. The analysis determines the exact probabilities for the **longest** and **shortest** suits in a 13-card bridge hand, providing a mathematical foundation for bidding strategy, defensive planning, and distributional evaluation.

All calculations are performed via **exhaustive enumeration** rather than simulation, ensuring precise and reproducible results.

---

## 🧮 Key Results

### Longest Suit Distribution
| Longest Suit | Probability | Frequency | Odds (1 in X hands) |
|--------------|-------------|-----------|---------------------|
| 5            | 44.34%      | 281,562,853,572 | 2.3 |
| 4            | 35.08%      | 222,766,089,260 | 2.9 |
| 6            | 16.55%      | 105,080,049,360 | 6.0 |
| 7            | 3.53%       | 22,394,644,272  | 28.4 |
| 8            | 0.47%       | 2,963,997,036   | 214.2 |
| 9            | 0.04%       | 235,237,860     | 2,699.5 |
| 10           | 0.0016%     | 10,455,016      | 60,737.7 |
| 11           | 0.000036%   | 231,192         | 2,746,693.5 |
| 12           | 3.19×10⁻⁷%  | 2,028           | 313,123,057.0 |
| 13           | 6.30×10⁻¹⁰% | 4               | 158,753,389,900.0 |

### Shortest Suit Distribution
| Shortest Suit | Probability | Frequency | Odds (1 in X hands) |
|---------------|-------------|-----------|---------------------|
| 2             | 53.80%      | 341,657,192,448 | 1.9 |
| 1             | 30.55%      | 194,023,212,812 | 3.3 |
| 3             | 10.54%      | 66,905,856,160  | 9.5 |
| 0             | 5.11%       | 32,427,298,180  | 19.6 |

---

## 📈 Highlights

- **Most common longest suit:** 5 cards (**44.34%**)
- **Most common shortest suit:** 2 cards (**53.80%**)
- **Extremely unbalanced hands** (longest suit ≥ 8 cards) occur in only **0.51%** of cases.
- **Voids** (shortest suit = 0) appear in **5.11%** of hands.
- **Balanced hands** (longest suit = 4) occur in **35.08%** of hands.

---

## 🧠 Strategic Implications

### Bidding Strategy
- **1-level openings** typically have a 5‑card suit (44.34%).
- **Weak two bids** are statistically justified with a 6‑card suit (16.55%).
- **Game‑level preempts** require an 8+ card suit (0.51%).

### Defensive Planning
- **Singleton probability:** 30.55%
- **Void probability:** 5.11%
- **Doubleton or longer:** 94.89%

### Partnership Evaluation
- Both partners holding 4‑card suits is common (35.08%).
- Combined fits of 8+ cards are rare (0.51%), affecting slam and grand‑slam decisions.

---

## ⚙️ Methodology

The algorithm uses **three nested loops** to enumerate all possible suit distributions (`spades`, `hearts`, `diamonds`, `clubs`) that sum to 13, then computes:

```python
L = max(spades, hearts, diamonds, clubs)  # longest suit
S = min(spades, hearts, diamonds, clubs)  # shortest suit



Each distribution’s probability is calculated using the multinomial coefficient:
Probability=(13s,h,d,c)⋅(3913−s,13−h,13−d,13−c)(5213)
Probability=(1352​)(s,h,d,c13​)⋅(13−s,13−h,13−d,13−c39​)​

All frequencies are exact integers; probabilities are derived from the total number of possible 13‑card hands:
(5213)=635,013,559,600
(1352​)=635,013,559,600
📂 Code Output Example
text

Maximum cards in bridge hand:
Max cards: 5 | Probability: 44.34 % from total | 281_562_853_572 frequency  | 1 from 2.3 hands
Max cards: 4 | Probability: 35.08 % from total | 222_766_089_260 frequency  | 1 from 2.9 hands
...
Minimum cards in bridge hand:
Min cards: 2 | Probability: 53.80 % from total | 341_657_192_448 frequency | 1 from 1.9 hands
Min cards: 1 | Probability: 30.55 % from total | 194_023_212_812 frequency | 1 from 3.3 hands
...

🔗 Repository & License

    Full code: https://github.com/DinkoTrendafilov/Probability-Distribution-of-Max-and-Min-Cards-Counts/blob/main/probability_distribution_of_maximum_and%20_minimum_suit_counts.ipynb

    License: MIT License (code) / CC BY 4.0 (documentation)

📚 References

    Kantar, E. (1999). Modern Bridge Defense. Master Point Press.

    Kelsey, H. W., & Glauert, M. (1980). Bridge Odds for Practical Players. Victor Gollancz Ltd.

    Borel, É., & Chéron, A. (1955). Théorie mathématique du bridge. Éditions Jacques Gabay.

📬 Contact

For questions or collaboration, contact: dinkino79@gmail.com

Keywords: Contract bridge, suit distribution, extremal analysis, longest suit, shortest suit, preemptive bidding, probability distribution
