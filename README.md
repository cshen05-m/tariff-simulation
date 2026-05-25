# iPhone Supply Chain Tariff Simulation

**Course:** Mathematical Modeling Final Project — Tufts University  
**Author:** Chengyi (Mark) Shen  
**Date:** May 2025

---

## Overview

On April 3, 2025, the United States imposed a sweeping new set of tariffs on major trading partners. This project uses a **minimum-cost network flow model** built in Python to simulate how those tariffs ripple through the iPhone 16 Pro's global supply chain — and what they mean for Apple's profit margins and consumer prices.

The model treats each major iPhone component (processor, display, battery, modem, memory, storage, camera, enclosure) as a node in a supply chain network, with edges representing costs and tariff burdens depending on country of origin.

---

## Key Findings

| Scenario | Component Cost | Profit Margin | Retail Price to Hold Margin |
|---|---|---|---|
| Pre-tariff (China assembly) | $549.73 | 81.7% | $999 (current) |
| Post-tariff (China assembly, 34%) | $736.63 | 35.6% | ~$1,338 |
| Made in USA (parts imported, US assembly) | $678.28 | — | ~$1,232 |

- A **34% tariff** on China-assembled iPhones cuts Apple's profit margin from **81.7% to 35.6%**
- To restore the original margin, Apple would need to raise the retail price to approximately **$1,338 — a 34% increase**
- Shifting assembly to the US (while importing parts) results in a **27% cost increase**, bringing retail price to ~$1,232 just to maintain margins
- No alternative Asian supply chain configuration was found to be more cost-effective than the existing China-based structure

---

## Files

| File | Description |
|---|---|
| `Tariff_Simulation.ipynb` | Full Python notebook with network flow model, all three scenarios, and cost calculations |
| `Tariff-Simulation-Report.pdf` | Written report with methodology, results, analysis, and conclusions |

---

## How to Run

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install numpy scipy jupyter
   ```
3. Open the notebook:
   ```bash
   jupyter notebook Tariff_Simulation.ipynb
   ```
4. Run all cells in order. Each scenario is clearly labelled within the notebook.

---

## Limitations

- Component costs sourced from WSJ reporting — exact figures are Apple trade secrets
- Tariff applied at the assembly country level, not per-component shipment
- Assembly cost difference between US and China not modelled (assumed equal as a conservative estimate)
- Quality, logistics, and transportation costs not included as edge weights
- Model is linear with respect to tariff rate — real-world supply chains involve far more dynamic variables

---

## Data Sources

- [WSJ — iPhone cost breakdown](https://www.wsj.com/tech/personal-tech/iphone-apple-tariffs-china-bb20c7a3)
- [Simply Mac — iPhone manufacturing cost](https://www.simplymac.com/iphone/how-much-does-it-cost-to-make-an-iphone)
- [NY Post — Tariff impact on iPhone prices](https://nypost.com/2025/04/06/us-news/heres-how-trumps-tariffs-could-send-iphone-prices-over)
- April 3, 2025 US tariff schedule (country-specific rates)
