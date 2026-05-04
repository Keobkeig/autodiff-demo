# Automatic Differentiation Interactive Demo

This repo is a single-page, self-contained HTML demo that visualizes
computational graphs, forward/reverse mode AD, and gradient descent.

## Run locally

Option 1: open the file directly

- Open `index.html` in any modern browser.

Option 2: serve with a local web server

```bash
python3 -m http.server
```

Then visit `http://localhost:8000` and open `index.html`.

## What to test

### 1) Optimization oscillation with high learning rate

- Go to the "Gradient Descent" tab.
- Pick optimizer: `SGD` or `Momentum`.
- Set learning rate to a high value (try `0.5`).
- Click `Start` or use `Step x10` to watch the loss curve oscillate or
  diverge and the parameters jump around.
- Compare with `Adam` at `0.05` to see smoother convergence.

### 2) Step-through of common ML functions in the graph

- Go to the "Computational Graph" tab.
- Use presets under "Activations" and "Loss terms" (sigmoid, softplus,
  tanh, logistic loss, etc.).
- Click `Build Graph`.
- Use `Step` and `Run Forward` / `Run Backward` to walk through values
  and gradients node-by-node in the step log.

### 3) Forward pass calculations with various functions

- In the "Computational Graph" tab, build a graph and press
  `Run Forward` to see a pure forward pass for different expressions.
- In the "Forward Mode" tab, pick presets and click `Compute` to get
  the dual-number forward result and derivative side-by-side.

## Notes

- Supported ops: `+ - * / ^ sin cos exp ln tanh`.
- All logic and styling live in `index.html`.
