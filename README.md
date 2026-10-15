# Beyond Earth

A dependency-free space exploration quiz with 10 multiple-choice questions,
instant answer feedback, space facts, a final score, and an answer review.
The responsive interface supports light and dark themes, keyboard navigation,
and reduced-motion preferences.

## Play online

Visit **[Beyond Earth](https://bdsing.github.io/space-quiz/)**.

## Run locally

Install Python 3, then run this command from the repository root:

```sh
python -m http.server 8000
```

Open <http://localhost:8000> in your browser. Stop the server with `Ctrl+C`.
No dependency installation or build step is needed. You can also open
`index.html` directly in a browser.

## Project structure

The entire application, including its styles, question data, and quiz logic,
lives in `index.html`. Edit the `questions` array to change the quiz content.
There is currently no configured automated test runner.

## Deployment

GitHub Pages uses **GitHub Actions** as its deployment source. The workflow in
`.github/workflows/pages.yml` prepares and uploads only `index.html`; it does
not publish repository documentation or configuration files.

Pull requests targeting `master` run the static-site preparation check without
deploying. Pushes to `master` deploy the site automatically. To redeploy
manually, run **Deploy GitHub Pages** from the repository's Actions tab with
the `master` branch selected.
