# Quantum Randomness Analysis

Analytical framework for uncertainty propagation in beam-splitter-based quantum random number generators (QRNGs) and its impact on computational efficiency, throughput, and Gaussian random number generation.

<p align="center">
  <img src="images/qrng_pipeline.png" width="1000"/>
</p>

---

# Overview

This project investigates how uncertainty in beam-splitter-based quantum random number generators propagates through randomness extraction and downstream computational processes.

The work focuses on:
- Bernoulli modeling of QRNG sources
- Randomness extraction efficiency
- Uncertainty propagation
- Throughput degradation
- Latency analysis
- Gaussian random number generation cost

The analysis establishes a unified relationship between physical source imperfections and computational overhead.

---

# QRNG Processing Pipeline

<p align="center">
  <img src="images/qrng_pipeline.png" width="1000"/>
</p>

The system pipeline consists of:

1. Beam-splitter quantum source
2. Bernoulli process modeling
3. Parameter estimation
4. Randomness extraction
5. Uniform bit generation
6. Gaussian random number generation
7. System-level performance analysis

---

# Extraction Efficiency Analysis

## Core Efficiency Equation

The von Neumann extraction efficiency is defined as:

```math
\eta(p) = p(1-p)
```

where:

- \( p \) represents the Bernoulli source parameter
- \( \eta(p) \) represents extraction efficiency

The function reaches maximum efficiency at:

```math
p = 0.5
```

which corresponds to an ideal unbiased quantum source.

<p align="center">
  <img src="images/extraction_efficiency.png" width="900"/>
</p>

## Sensitivity Approximation

Near the optimal operating point:

```math
p = 0.5 - \delta p
```

the extraction efficiency becomes:

```math
\eta(0.5-\delta p) \approx 0.25 - (\delta p)^2
```

This demonstrates the quadratic degradation in efficiency caused by parameter uncertainty.

---

# Cost & Performance Analysis

## Uniform Bit Generation Cost

The expected raw-bit cost for generating one unbiased random bit is:

```math
C_u(p) = \frac{1}{p(1-p)}
```

At the optimal operating point:

```math
C_u(0.5) = 4
```

meaning four raw quantum measurements are required on average for one unbiased output bit.

<p align="center">
  <img src="images/cost_analysis_table.png" width="850"/>
</p>

The framework quantifies:
- raw-bit cost
- extraction efficiency
- computational overhead
- throughput degradation
- latency increase

under varying source uncertainty conditions.

---

# Throughput & Latency Analysis

## Estimation Precision Bound

Parameter estimation uncertainty is bounded by the Cramér–Rao inequality:

```math
Var(\hat{p}) \geq \frac{p(1-p)}{N}
```

where:

- \( \hat{p} \) is the estimated source parameter
- \( N \) is the number of collected samples

This establishes the throughput–precision trade-off analyzed throughout the project.

<p align="center">
  <img src="images/throughput_analysis.png" width="900"/>
</p>

The project evaluates how uncertainty affects:
- randomness throughput
- extraction efficiency
- Gaussian generation latency
- system-level performance stability

The analysis connects physical QRNG imperfections directly to computational resource cost.

---

# Key Contributions

- Unified analytical framework for QRNG uncertainty propagation
- Closed-form efficiency approximations
- Cost models for uniform and Gaussian random generation
- Throughput–precision trade-off analysis
- System-level interpretation of uncertainty effects

---

# Technologies & Methods

## Mathematical & Statistical Methods

- Bernoulli modeling
- Shannon entropy analysis
- Fisher information
- Cramér–Rao bounds
- Taylor approximation
- Uncertainty propagation

## Computational Analysis

- Python
- Numerical evaluation
- Performance modeling
- Throughput analysis

---

# Results

| Metric | Observation |
|---|---|
| Extraction Efficiency | Governed by \( p(1-p) \) |
| Sensitivity | Quadratic near \( p = 0.5 \) |
| Uniform Bit Cost | Increases under source bias |
| Gaussian Cost | Strongly affected by uncertainty |
| Throughput | Degrades with estimation uncertainty |
| Latency | Increases as uncertainty grows |

---

# Key Research Concepts

- Quantum random number generation
- Randomness extraction
- Entropy analysis
- Statistical estimation
- Throughput–precision trade-offs
- Computational cost modeling
- Uncertainty propagation

---

# Source Structure

```text
src/
├── efficiency_analysis.py
├── uncertainty_propagation.py
├── throughput_model.py
└── README.md
```

---

# Documentation

- [Full Technical Report](docs/qrng_uncertainty_report.pdf)

---

# Authors

- Hasan Al Hussein
- Omar Yousef
- Ahmad Alhawamdeh

Khalifa University
