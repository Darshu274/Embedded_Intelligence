# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Environment

Python 3.9 (via `/Library/Frameworks/Python.framework/Versions/3.9/bin/python3.9`) is the working interpreter — it has compatible versions of `numpy` (2.0.2) and `matplotlib` (3.9.4). The Anaconda Python (3.12) has a NumPy ABI conflict with matplotlib and should not be used.

## Running Notebooks

Execute a notebook non-interactively:
```bash
/Library/Frameworks/Python.framework/Versions/3.9/bin/python3.9 -m jupyter nbconvert --to notebook --execute --inplace <notebook>.ipynb
```

Launch interactive Jupyter:
```bash
/Library/Frameworks/Python.framework/Versions/3.9/bin/python3.9 -m jupyter lab
```

## Dependencies

```bash
/Library/Frameworks/Python.framework/Versions/3.9/bin/python3.9 -m pip install numpy matplotlib jupyterlab
```

## Repository Structure

| File | Purpose |
|------|---------|
| `multilateration_exercise.ipynb` | Student-facing worksheet — all solution cells contain `None` placeholders |
| `multilateration_exercise_solution.ipynb` | Completed solution notebook |

## Notebook Architecture

Both notebooks implement the same 7-task flow:

1. **Setup** — define 4 anchor positions and true mobile node position `M_true`
2. **True distances** — `np.linalg.norm(anchors - M_true, axis=1)`
3. **`multilaterate(anchors, distances)`** — linearises the multilateration system into `Ax = b` (subtracting anchor-1 equation from each other), solves with `np.linalg.lstsq`
4. **Noise simulation** — additive Gaussian noise on distances via `np.random.normal`
5. **Visualisation** — anchors, true/estimated positions, dashed distance circles
6. **Statistical analysis** — 1000-trial Monte Carlo over 8 σ values, mean ± std error plot
7. **RSSI model** — path-loss forward/inverse (`rssi_from_distance`, `distance_from_rssi`), scatter comparison of RSSI-based vs. direct-noise estimates over 200 trials

The `multilaterate` function defined in Task 3 is reused by all subsequent tasks — it must remain in scope.
