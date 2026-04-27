# Biochemical ID Quest

Biochemical ID Quest is a browser-based teaching tool for microbiology practical revision.
It models Gram-positive cocci, Gram-positive rods, and Gram-negative decision trees using
real lab-style biochemical tests, then explains both mechanism and clinical significance.

## Features

- Guided and quiz/test modes.
- Keyboard navigation (`Y`, `N`, `Backspace`, `R`).
- Session persistence in `localStorage` with schema validation.
- Session history tracking and export (`.json` and `.txt`).
- Accessibility support via ARIA live region updates.
- Data-driven trees from `data/decision-trees.json`.

## Project structure

- `index.html` — app UI and logic.
- `data/decision-trees.json` — test nodes, trees, and organism cards.
- `styles/decision-tree.css` — visual styling.
- `biochemical_id_decision_tree.html` — redirect entrypoint.

## Run locally

Because the app fetches JSON, run from a local web server:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/`.

## Extending the tree

1. Add or update test nodes in `NODES` with `yes`/`no` links.
2. Add organism cards in `ORGS` with `path`, `features`, and `distinction` text.
3. Add any new terminal mapping node in `NODES` (`ORG_*` entries).
4. Reload and test pathways in both Guided and Test modes.
