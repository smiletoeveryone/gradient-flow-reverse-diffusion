
# Gradient Flow as Reverse Diffusion

This repository contains the LaTeX source code and figures for the paper:

**Viewing Gradient Flow as Reverse Diffusion: A Thermodynamic and Probabilistic Perspective**

## Abstract

Gradient descent can be viewed as a reverse-time probability flow ODE — a deterministic interpretation of score-based diffusion. This theoretical lens connects optimization with stochastic generative modeling, grounded in the thermodynamics of learning and Wasserstein flows.

## Files

- `main.tex`: The full LaTeX source of the paper
- `refs.bib`: BibTeX references
- `figures/`: Contains figure(s) used in the paper
- `trajectory.png`: Gradient flow vs reverse diffusion visualization

## How to Compile

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## License

MIT License
