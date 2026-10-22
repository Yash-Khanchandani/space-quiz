# Copilot instructions

## Project facts

- The quiz is a single `index.html` with inline CSS and JavaScript. It runs directly in a browser without a build step, server, framework, CDN, or external font.
- Quiz data is in one JavaScript array. Each object currently uses `difficulty`, `question`, `options`, `answer`, and `explanation`; `answer` is the zero-based index of the correct option.
- The page renders one question at a time. `renderQuestion()`, `selectAnswer()`, `advance()`, `showResults()`, and `resetQuiz()` manage rendering, scoring, progression, results, and replay.
- There are no repository-defined build, test, or lint commands, package manifest, or automated test suite.

## Code conventions

- Use vanilla ES6+, `const`/`let` (never `var`), strict equality, small single-purpose functions, and descriptive `camelCase` names, consistent with the inline script.
- Keep quiz questions in the existing array and preserve its current field names and zero-based `answer` index.
- Use the existing CSS custom properties for colors and add new color or spacing values as custom properties rather than scattering literals. Avoid unexplained numeric constants; where a value is tied to the quiz, derive it from the questions array when practical.
- Insert question, answer, and feedback text with `textContent` or text nodes, not `innerHTML`. Attach behavior with `addEventListener`, not inline event attributes.
- Add comments only when they explain a non-obvious reason; do not restate the code.

## Accessibility and content

- Keep interactive controls keyboard reachable and visibly focused. Preserve the quiz's native buttons, 1–4 answer shortcuts, and focus movement to question and result headings.
- Do not communicate correctness through color alone: retain the check/incorrect icon and written feedback alongside color highlights.
- Respect `prefers-reduced-motion`; any pulse or shake animation needs a reduced-motion alternative or override.
- Maintain at least 4.5:1 contrast for text in both color schemes when changing colors.
- Quiz facts must be verifiable. Verify uncertain claims before adding them, and flag any claim that cannot be substantiated.

## Workflow

- Make the smallest change that solves the request; avoid unrelated refactors.
- Before finishing, identify which accessibility checks above the change could affect.
- Do not add dependencies or extra files without asking.
