# Group-Exercise-Agentic-AI-in-Marketing-1

# Ad Optimization Agent

## Project Overview

This project prototypes a lightweight ad optimization agent that allocates a fixed daily advertising budget across Search, Social, and Display. The agent analyzes channel performance, recommends budget changes, applies guardrails, and explains the reason for each decision.

## Objective

The agent’s primary goal is to maximize conversions while keeping cost per acquisition (CPA) low.

The prototype uses a total daily budget of $300 and begins with an equal allocation:

- Search: $100
- Social: $100
- Display: $100

## How to Run

1. Open `Group_Work_|_Ad_Optimization_Agent.ipynb` in Google Colab or Jupyter Notebook.
2. Run the notebook cells from top to bottom.
3. The notebook generates 21 days of mock advertising data.
4. It calculates performance metrics, recommends new budgets, creates a decision log, and compares the optimized allocation with an equal-split baseline.

### Requirements

- Python 3
- pandas
- Google Colab or Jupyter Notebook

The notebook creates these files during execution:

- `ad_performance.csv`
- `decision_log.csv`

## Agent Approach

The agent:

1. Reads daily advertising data for three channels.
2. Calculates CTR, conversion rate, CPA, and conversions per dollar.
3. Ranks channels using conversion rate, with CPA as a supporting metric.
4. Increases the budget for the strongest channel.
5. Reduces the budget for the weakest channel.
6. Keeps the middle-performing channel stable.
7. Logs the budget recommendation and reason for every channel.

## Guardrails

The agent applies the following rules:

- No channel changes by more than 20% per day.
- Every channel receives at least $50.
- The total daily budget remains $300.
- No channel is completely removed from the allocation.
- Every budget decision includes an explanation.
- The prototype uses aggregate mock data and does not use personal information.

## Evaluation Results

The agent was compared with an equal-split baseline.

| Metric | Equal-Split Baseline | Optimized Agent |
|---|---:|---:|
| Expected conversions | 47.93 | 50.16 |
| Expected CPA | $6.26 | $5.98 |
| Daily budget | $300 | $300 |

The optimized allocation produced a modeled conversion improvement of **4.64%**.

Recommended budget:

- Search: $120
- Social: $100
- Display: $80

## Assumptions and Limitations

The dataset contains 21 days of simulated advertising data. The channels are treated as independent, conversion delays and diminishing returns are not modeled, and the evaluation produces expected results rather than live campaign outcomes. The prototype is intended to demonstrate the agent’s budget allocation logic and guardrails.
