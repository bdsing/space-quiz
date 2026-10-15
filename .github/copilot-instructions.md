# Repository guidance

## Project shape

This repository is a dependency-free, single-page space quiz. The entire application lives in `index.html`: semantic markup provides the page and quiz/result views, an inline `<style>` block defines responsive and light/dark styling, and an inline `<script>` contains the question data and quiz behavior. There is no framework, module bundler, or separate application layer.

## Build, run, and tests

There is no configured build, lint, or automated test command. There is also no test runner or single-test command.

To preview the page locally, run `python -m http.server 8000` from the repository root and open `http://localhost:8000`.

## Application conventions

- Keep the application self-contained in `index.html`; there are currently no package manifests or external runtime dependencies.
- Quiz content is defined in the `questions` array. Each entry has a category, question, four answer strings, a zero-based `correct` answer index, and an explanatory `fact`. Rendering and scoring use this data.
- The quiz is driven by the `current`, `score`, and `answered` state variables and the `renderQuestion`, `chooseAnswer`, and `showResults` functions. Keep answer selection, progress updates, feedback, and result transitions consistent across these paths.
- Use the existing DOM IDs as the interface between markup and script. Insert question and feedback text with `textContent`; build answer controls as buttons and attach their click handlers when rendering.
- Preserve the existing accessibility behavior: semantic sections, labelled answer group, live score/feedback updates, progress-bar values, visible keyboard focus, focus movement between questions/results, and reduced-motion styling.
- Styling is inline and uses CSS custom properties for theme colors, with dark-mode, small-screen, and reduced-motion overrides in media queries. Reuse these patterns when changing the presentation.
