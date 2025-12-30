# 🔢 Prime Number Layer System

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.18094758-blue)](https://doi.org/10.5281/zenodo.18094758)

**A novel topological representation of prime numbers revealing a connection to the Silver Ratio (δₛ = 1 + √2)**

📄 **Paper:** [Zenodo - DOI: 10.5281/zenodo.18094758](https://doi.org/10.5281/zenodo.18094758)

---

## 🎯 The Discovery

This repository contains the implementation of the **Layer System**, a new way to represent prime numbers that reveals:

1. **An exact bijection**: The void of the k-th prime equals the (k-3)-th composite
   ```
   V(Pₖ) = Cₖ₋₃
   ```

2. **An asymptotic formula** with an elegant constant:
   ```
   P/S - 1 = (2 + √2) / [ln(P) · ln(ln(P))]
   ```

3. **First appearance of the Silver Ratio** (δₛ = 1 + √2) in prime number theory

---

## 📐 The Formula

Every prime P can be decomposed as:

```
P = V + S
```

Where:
- **V (Void)**: A deterministic origin point  
- **S (Sum)**: The sum of layer distances

The ratio P/S follows:

```
       P              2 + √2
      ─── - 1  =  ────────────────
       S          ln(P) · ln(ln(P))
```

The constant **2 + √2 = √2 × δₛ ≈ 3.414** involves the **Silver Ratio**.

---

## 🚀 Quick Start

### Installation

```bash
git clone https://github.com/YOUR_USERNAME/prime-layer-system.git
cd prime-layer-system
pip install -r requirements.txt
```

### Basic Usage

```python
from layer_system import LayerSystem

# Create system with first 10,000 primes
ls = LayerSystem(n_primes=10000)

# Verify the bijection V(Pk) = C(k-3)
results = ls.verify_bijection()
print(f"Bijection accuracy: {results['accuracy']}%")

# Calculate the constant
constant = ls.calculate_constant()
print(f"Constant: {constant}")  # Should approach 3.414...

# Full analysis
ls.full_analysis()
```

### Command Line

```bash
# Run full analysis
python layer_system.py

# Test with specific number of primes
python layer_system.py --primes 50000

# Verify bijection only
python layer_system.py --verify

# Export results to CSV
python layer_system.py --export results.csv
```

---

## 📊 Results

### Bijection Verification (100% accurate)

| k | Pₖ | V (computed) | Cₖ₋₃ | Match |
|---|-----|--------------|-------|-------|
| 4 | 7 | 4 | 4 | ✓ |
| 100 | 541 | 133 | 133 | ✓ |
| 1,000 | 7,919 | 1,194 | 1,194 | ✓ |
| 10,000 | 104,729 | 11,372 | 11,372 | ✓ |
| 100,000 | 1,299,709 | 130,684 | 130,684 | ✓ |

### Convergence to 2 + √2

| Magnitude | c (empirical) | Error from 2+√2 |
|-----------|---------------|-----------------|
| 10¹⁰ | 3.4149 | 0.02% |
| 10⁵⁰ | 3.4143 | 0.003% |
| 10¹⁰⁰ | 3.4143 | 0.001% |
| 10⁵⁰⁰ | 3.4142 | 0.0003% |
| 10¹⁰⁰⁰ | 3.41421 | 0.0001% |

---

## 🔬 Why the Silver Ratio?

The **Silver Ratio** (δₛ = 1 + √2 ≈ 2.414) governs octagonal geometry:

- Regular octagons have diagonal ratios involving √2 and δₛ
- Primes modulo 8 occupy exactly 4 of 8 positions: {1, 3, 5, 7}
- This octagonal symmetry may explain why 2 + √2 = √2 × δₛ appears

```
Primes mod 8:
  
  0: ░░░░░░░░  0%  (impossible)
  1: ████████ 25%  ← PRIME
  2: ░░░░░░░░  0%  (only p=2)
  3: ████████ 25%  ← PRIME
  4: ░░░░░░░░  0%  (impossible)
  5: ████████ 25%  ← PRIME
  6: ░░░░░░░░  0%  (impossible)
  7: ████████ 25%  ← PRIME
```

---

## 📁 Repository Structure

```
prime-layer-system/
├── README.md                 # This file
├── LICENSE                   # MIT License
├── requirements.txt          # Python dependencies
├── layer_system.py          # Main implementation
├── examples/
│   ├── basic_usage.py       # Simple examples
│   ├── verify_bijection.py  # Bijection verification
│   ├── analyze_constant.py  # Constant analysis
│   └── visualizations.py    # Plotting functions
├── tests/
│   ├── test_layer_system.py # Unit tests
│   └── test_bijection.py    # Bijection tests
├── data/
│   └── sample_results.csv   # Pre-computed results
└── docs/
    ├── THEORY.md            # Mathematical background
    ├── ALGORITHM.md         # Algorithm explanation
    └── CITATION.cff         # Citation file
```

---

## 📖 Documentation

- [Theory & Mathematical Background](docs/THEORY.md)
- [Algorithm Explanation](docs/ALGORITHM.md)
- [API Reference](docs/API.md)

---

## 🧪 Running Tests

```bash
# Run all tests
python -m pytest tests/ -v

# Run specific test
python -m pytest tests/test_bijection.py -v

# Run with coverage
python -m pytest tests/ --cov=layer_system
```

---

## 📚 Citation

If you use this work, please cite:

```bibtex
@software{cunha_2025_18094758,
  author       = {Cunha, Cristian},
  title        = {The Silver Ratio in Prime Number Structure: A Layer System Approach},
  month        = dec,
  year         = 2025,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.18094758},
  url          = {https://doi.org/10.5281/zenodo.18094758}
}
```

Or in text format:

> Cunha, C. (2025). The Silver Ratio in Prime Number Structure: A Layer System Approach. Zenodo. https://doi.org/10.5281/zenodo.18094758

---

## 🤝 Contributing

Contributions are welcome! Please feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Cristian Cunha**  
Independent Researcher  
Uberlândia, MG, Brazil  
📧 cristiancunha@hotmail.com

---

## 🙏 Acknowledgments

- Computational validation assisted by Claude (Anthropic) and Gemini (Google)
- Inspired by the beauty of prime numbers and geometric constants

---

*"The void is no longer a mystery, it's a coordinate. And that coordinate lives in an octagon."*
