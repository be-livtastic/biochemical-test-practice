# Biochemical Organism Quiz

Biochemical Organism Quiz is a browser-based microbiology revision tool built around
recognition-first recall: the app presents morphology clues for an unknown organism,
and you identify it from six answer options.

## Features

- One-loop quiz flow: question → optional hint → result.
- Six-organism morphology-focused revision set.
- Keyboard support (`1-6` to answer, `Backspace` to go back one question).
- Full result cards with features, clinical context, distinction insight, and RFLP notes where relevant.
- End-of-round summary with missed-organism retry.

## Project structure

- `index.html` — single-page quiz UI and logic.
- `data/quiz-organisms.json` — flat organism quiz dataset.
- `styles/quiz.css` — quiz-specific styling.

## Run locally

Because the app fetches JSON, run from a local web server:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/`.

## Extending the quiz

1. Add or edit organism objects in `data/quiz-organisms.json`.
2. Keep morphology clues concise and visual (colony, shape, arrangement, special cues).
3. Provide wrong-answer feedback keyed by organism name for targeted correction.
4. Add RFLP notes only where molecular interpretation is assessed.
