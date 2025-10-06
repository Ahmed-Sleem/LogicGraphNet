# 🧠 LogicTreeNet: Guiding Neural Provers with Counterfactual Foresight

This repository contains the official implementation of **LogicTreeNet**, a novel framework for training highly efficient neural theorem provers, introduced in the paper:

> **“Don't Just Try, Try Smarter: Guiding Neural Provers with Counterfactual Foresight”**

LogicTreeNet is a **graph-based reasoning agent** trained with **Counterfactual-Guided Policy Improvement (CGPI)** — a new methodology that teaches the model to anticipate and avoid unproductive reasoning paths.  
This results in an agent that is not only effective but also remarkably efficient, solving complex proofs with minimal search.

---

## 📘 Overview

The core idea behind LogicTreeNet is to move beyond reactive, brute-force search and towards a more **proactive, intuitive style of reasoning**.  
Instead of simply learning from successful proofs, our **CGPI training methodology** forces the model to learn from *failure* by:

- Generating diverse **counterfactual "good" states** from failed proof attempts.  
- Using a **multi-faceted loss function** (including a value ranking loss) to teach the model's value function to prefer these ideal states.  

This process produces a model with an **exceptionally accurate value function**, enabling it to solve proofs with state-of-the-art efficiency.  
At inference, this is complemented by a novel **Corrective Lookahead search**, which anticipates potential failures before committing to a step.

---

## 🧩 Key Features & Contributions

- **Counterfactual-Guided Policy Improvement (CGPI):**  
  A novel training paradigm that uses generated counterfactuals and a value ranking loss to create a highly accurate and proactive value function.

- **High-Efficiency Graph-Based Agent:**  
  A compact, structured reasoning model that outperforms larger, generalist LLM baselines in efficiency on the **LeanDojo Benchmark**.

- **Corrective Lookahead Search:**  
  A lightweight inference strategy that uses the model's trained corrective operator to make more robust decisions by anticipating and evaluating recovery paths.

- **State-of-the-Art Performance:**  
  Achieves a **65.0% success rate** on the **LeanDojo Benchmark 4 (novel premises)**, demonstrating strong generalization and effectiveness.

---

## 🚀 Results on LeanDojo Benchmark 4

| Model                                | Success Rate | Avg. Verifier Calls | Efficiency Score |
|--------------------------------------|---------------|----------------------|------------------|
| **LogicTreeNet (Corrective Lookahead)** | **65.0%**     | 1.42                 | 45.94            |
| LogicTreeNet (No Correction)         | 65.0%         | 1.41                 | 46.26            |
| LLM Baseline (galactica-125m)        | 60.0%         | 1.00                 | 60.00            |
| Neural Search Baseline               | 60.0%         | 6.50                 | 9.22             |
| Random                               | 17.5%         | 9.34                 | 1.87             |

---

## 📄 Citation

If you find this work useful in your research, please cite our paper:

```bibtex
@article{sleem2025logictreenet,
  title={Don't Just Try, Try Smarter: Guiding Neural Provers with Counterfactual Foresight},
  author={Sleem, Ahmed and Adly, Nihal Ahmed},
  journal={arXiv preprint},
  year={2025}
}
