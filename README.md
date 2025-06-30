
# Gradient Flow as Reverse Diffusion

![banner](gradient_flow_banner.png)

> Gradient descent can be interpreted as a deterministic reverse-time diffusion process, connecting optimization to score-based generative modeling.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 📄 Paper Overview

This repository contains the full LaTeX source code, mathematical formulation, toy experiments, and figures for the paper:

**Viewing Gradient Flow as Reverse Diffusion: A Thermodynamic and Probabilistic Perspective**

Gradient descent in deep learning can be seen as a deterministic trajectory that mirrors the reverse process of a stochastic diffusion. By framing optimization dynamics using the language of probability flow ODEs, we build a theoretical bridge between score-based generative modeling, Wasserstein gradient flows, and thermodynamic interpretations of learning.

## 🧠 Highlights

- Interprets gradient descent as a reverse-time probability flow
- Links Fokker-Planck, diffusion models, and variational optimization
- Introduces toy experiments on 2D quadratic loss landscapes
- Includes LaTeX and figures to compile the full paper

## 📁 Repository Structure

```
├── main.tex                 # LaTeX source of the paper
├── refs.bib                # BibTeX references
├── gradient_flow_banner.png # GitHub header image
├── figures/
│   └── trajectory.png      # Toy experiment plot
├── arxiv_metadata.txt      # ArXiv abstract and categories
└── README.md               # This file
```

## 📊 Example Figure

![Trajectory](figures/trajectory.png)

## 📦 How to Compile the Paper

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

This will generate `main.pdf`, the full paper.

## 📖 License

MIT License

---

## 📜 Full Paper Content (Text Version)

### Abstract

Gradient-based optimization lies at the core of modern machine learning. In this paper, we provide a new perspective on gradient descent dynamics by interpreting them as reverse-time probability flows akin to those used in diffusion-based generative models. Drawing connections between Wasserstein gradient flows, Fokker-Planck equations, and score-based diffusion models, we propose that gradient descent trajectories in parameter space can be understood as the deterministic reversal of an underlying stochastic diffusion process.

---

### 1. Introduction

Einstein's 1905 theory of Brownian motion linked microscopic particle dynamics to macroscopic diffusive behavior. This formulation inspired the modern theory of stochastic processes and laid the groundwork for the Fokker-Planck equation. In parallel, recent advancements in generative modeling have harnessed stochastic differential equations (SDEs) to define forward noising processes and reverse-time sampling mechanisms, as in score-based diffusion models.

This paper explores an intriguing correspondence: **gradient descent dynamics in parameter space can be viewed as a special case of probability flow ODEs**, which themselves are the deterministic counterparts to stochastic diffusion processes.

---

### 2. Background

#### 2.1 Fokker-Planck and Brownian Motion

The classical diffusion equation:
```
∂t ρ(x,t) = D ∇² ρ(x,t)
```

A more general SDE:
```
dx = f(x,t)dt + g(t) dWt
```

has corresponding density evolution:
```
∂t ρ = -∇⋅(fρ) + ½ ∇²(g²ρ)
```

#### 2.2 Diffusion Models in ML

Forward process:
```
dx = f(x,t)dt + g(t) dWt
```

Reverse-time deterministic version (probability flow ODE):
```
dx = [f(x,t) - g(t)² ∇x log p_t(x)] dt
```

---

### 3. Gradient Descent as Reverse Diffusion

Gradient descent:
```
dθ/dt = -∇θ L(θ)
```

Can be interpreted as a flow over parameter density ρ(θ,t):
```
∂t ρ + ∇θ ⋅ (ρ ∇θ L) = 0
```

This form matches that of the probability flow ODE in generative modeling.

---

### 4. Constructing the Forward SDE

We hypothesize a forward SDE:
```
dθ = f(θ,t)dt + g(t)dWt
```

with reverse-time dynamics equivalent to gradient descent.

---

### 5. Toy Example

Using a 2D quadratic loss:
```
L(θ) = ½ θᵀ A θ
```

we simulate both the forward stochastic diffusion and reverse trajectory using score-based methods.

![Figure: Gradient Flow vs Reverse Diffusion](figures/trajectory.png)

---

### 6. Implications

- Theoretically unifies diffusion modeling and optimization
- Enables thermodynamic interpretation of learning
- Paves the way for diffusion-inspired optimizers and regularizations

---

### 7. Conclusion

We propose a new lens to view gradient descent as a reverse diffusion process. This bridges optimization, generative modeling, and thermodynamics under a single theoretical framework.

---

