# Deep Learning — Lab 2: GAN \& Diffusion

Practical exercise on generative models for MNIST. Covers vanilla GAN,
conditional GAN, alternative loss functions, adversarial attacks, and
diffusion models.

**Team:** \[Christos Palantzidis], \[Rafal Popiolek], \[Dasari]

**Wandb project:** [https://wandb.ai/YOUR\_TEAM/lab2-gan-diffusion](#)
(public dashboard with all training runs)

\---

## Repository structure

Each task is self-contained in its own folder with a Jupyter notebook
(runnable on Colab with free GPU) and a `results/` folder with the
rendered outputs. **You do not need to re-run anything** — the notebooks
on GitHub already show all outputs inline.

|Task|Description|Notebook|
|-|-|-|
|1|Vanilla GAN (Goodfellow et al., 2014)|[task1\_vanilla\_gan](task1_vanilla_gan/task1_vanilla_gan.ipynb)|
|2|Logistic loss variant + 5/10/50 epoch comparison|[task2\_logistic\_loss](task2_logistic_loss/task2_logistic_loss.ipynb)|
|3|Conditional GAN (class-conditional generation)|[task3\_cgan](task3_cgan/task3_cgan.ipynb)|
|4|CNN classifier + adversarial attack (4 → 9)|[task4\_adversarial](task4_adversarial/task4_adversarial.ipynb)|
|5|Stable diffusion for MNIST|[task5\_diffusion](task5_diffusion/task5_diffusion.ipynb)|
|Theory 2.1|Ethical assessment of generative LLM images|[theory/ethical\_assessment.pdf](theory/ethical_assessment.pdf)|

\---

## How to run (optional — outputs are already committed)

Open any notebook in Google Colab:

[!\[Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO)

Or run locally:

```bash
git clone https://github.com/YOUR\_USERNAME/YOUR\_REPO.git
cd YOUR\_REPO
pip install -r requirements.txt
jupyter notebook
```

**GPU is required** for reasonable training times.

\---

## Results summary

### Task 1 — Vanilla GAN

* Architecture: 4-layer MLP generator (100→256→512→1024→784), 4-layer MLP
discriminator with dropout
* Trained for 100 epochs on MNIST
* D(x) ≈ 0.5, D(G(z)) ≈ 0.5 at convergence → Nash equilibrium reached
* See samples: [task1\_vanilla\_gan/results/](task1_vanilla_gan/results/)

### Task 2 — Logistic Loss

* Compared BCE loss vs Logistic loss on 5/10/50 epoch runs
* \[Add key finding here]

### Task 3 — Conditional GAN

* Generator and Discriminator conditioned on class labels (0-9)
* Can generate specific digits on demand
* See grid: [task3\_cgan/results/generated\_digits\_per\_class.png](#)

### Task 4 — Adversarial Attack

* CNN classifier trained on MNIST → \[accuracy]%
* Successfully crafted adversarial 4s classified as 9s with
\[perturbation budget]
* Random noise images classified as 9 with \[confidence]%

### Task 5 — Diffusion Model

* Implemented DDPM-style diffusion on MNIST
* \[Comparison with cGAN: diffusion produces sharper/more diverse samples]

\---

## References

* Goodfellow et al., *Generative Adversarial Nets*, NeurIPS 2014
([arXiv:1406.2661](https://arxiv.org/abs/1406.2661))
* Mirza \& Osindero, *Conditional Generative Adversarial Nets*, 2014
([arXiv:1411.1784](https://arxiv.org/abs/1411.1784))
* Ho et al., *Denoising Diffusion Probabilistic Models*, NeurIPS 2020
([arXiv:2006.11239](https://arxiv.org/abs/2006.11239))
* Goodfellow et al., *Explaining and Harnessing Adversarial Examples*,
ICLR 2015 ([arXiv:1412.6572](https://arxiv.org/abs/1412.6572))

