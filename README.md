# 🧠 LogicGraphNet: Learning from Failure to Build Efficient AI Theorem Provers

[![arXiv](https://img.shields.io/badge/arXiv-2025.xxxxx-b31b1b.svg)](https://arxiv.org/abs/xxxx.xxxxx)
[![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF.svg)](https://www.kaggle.com/datasets/a7medsleem/leandojo-benchmark-4-creators)

Official implementation of **LogicGraphNet**, a compact neural theorem prover that learns from failures to achieve remarkable efficiency.

> **"Failing Forward: How Analyzing Mistakes Creates More Efficient and Robust AI Theorem Provers"**  
> Ahmed Sleem, Nihal Ahmed Adly  
> Egypt-Japan University of Science and Technology (E-JUST)

## 🎯 Key Results

- **65.0% success rate** on LeanDojo Benchmark 4 (vs 67.0% for 125M-parameter LLM)
- **71.2% on novel premises** (surpassing LLM's 66.7%)
- **63× smaller** than LLM (1.98M vs 125M parameters)
- **14× faster** inference (0.047s vs 0.658s per proof)
- Trained in **223 seconds** on free Kaggle CPU

## 💡 Core Innovation

**Counterfactual-Guided Policy Improvement (CGPI)**: Instead of just learning from successful proofs, we teach the model to analyze failures by:
1. Generating diverse "what if" scenarios from failed attempts
2. Learning the direction from failure to success
3. Applying corrections through gated updates
4. Looking ahead to evaluate recovery paths before committing


## 📊 Performance Comparison

| Model | Success Rate | Parameters | Inference Time | Generalization (Novel) |
|-------|-------------|------------|----------------|----------------------|
| **LogicGraphNet** | **65.0%** | **1.98M** | **0.047s** | **71.2%** ✨ |
| LLM (Galactica-125M) | 67.0% | 125M | 0.658s | 66.7% |
| Neural Search | 29.5% | 0.97M | 0.041s | 37.9% |

✨ *LogicGraphNet improves on novel problems—a rare property showing true reasoning*

## 📄 Citation
```bibtex
@article{sleem2025failing,
  title={Failing Forward: How Analyzing Mistakes Creates More Efficient and Robust AI Theorem Provers},
  author={Sleem, Ahmed and Adly, Nihal Ahmed},
  journal={arXiv preprint arXiv:2025.xxxxx},
  year={2025}
}
```
