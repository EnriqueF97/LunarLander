# Lunar Lander — Double DQN

Train a Deep-Q agent that reliably lands the rocket in Gymnasium’s **LunarLander-v3** environment. The codebase is short, fully-commented, and runs in real-time on CPUs (M-series Mac, Windows, Linux) or GPUs.

---

## Highlights

| Feature                               | Why it matters                                                            |
| ------------------------------------- | ------------------------------------------------------------------------- |
| **Double DQN update**                 | Reduces Q-value over-estimation ⇒ smoother learning, faster convergence.  |
| **Soft target sync (`τ = 0.005`)**    | Keeps the target network a slow-moving average; stabilises training.      |
| **Replay buffer + ε-greedy schedule** | Classic tricks for data efficiency and balanced exploration.              |
| **Early stopping & patience**         | Stops after the 100-episode average ≥ 200 _or_ no progress for _N_ evals. |
| **MP4 video recorder**                | Optional `RecordVideo` wrapper saves greedy flights to `./videos/`.       |
| **Tiny MLP (≈ 11 k params)**          | Fits on low-power laptops; reaches "solved" in ≈ 400–800 episodes.        |
| **Seed helper**                       | One call locks RNGs for reproducible curves.                              |

---

## What it accomplishes

- Solves LunarLander (≥ 200 avg reward) without GPU.
- Demonstrates how Double DQN differs from vanilla DQN in ≈ 200 lines.
- Serves as a template for any Box2D or Atari task—swap the env ID and go.

---

## Tech stack

| Package                                         | Purpose                                        | Docs              |
| ----------------------------------------------- | ---------------------------------------------- | ----------------- |
| **[Gymnasium](https://gymnasium.farama.org/)**  | Environments (`LunarLander-v3`, `RecordVideo`) | API, wrappers     |
| **[PyTorch](https://pytorch.org/docs/stable/)** | Neural network & optimiser                     | Tensors, autograd |
| **NumPy**                                       | Fast array math                                | —                 |
| **Matplotlib** _(optional)_                     | Reward‑curve PNG                               | —                 |
| **tqdm** _(optional)_                           | Progress bar                                   | —                 |
| **Box2D 2.3.10**                                | Physics engine (pre‑built arm64 wheels)        | —                 |

---

## Further reading and documentation

- **Double DQN paper** – _Deep Reinforcement Learning with Double Q‑learning_ (van Hasselt et al., 2016)
- **Gymnasium docs** – <https://gymnasium.farama.org/>
- **PyTorch docs** – <https://pytorch.org/docs/stable/>

---

## Demonstration

[Check the model performance as it progress its training!](https://youtu.be/l5ZGZeFIHQU)

---

## License

Apache License.
