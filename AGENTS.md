# AGENTS.md

## Project

This folder contains a static mortgage calculator site.

- Main published page: `index.html`
- Local mirror/alternate file: `mortgage_calculator.html`
- GitHub remote: `origin` (`https://github.com/uuu879/mortgage-site.git`)
- Default branch: `main`

## Working Rules

1. Read this file before editing the project.
2. Keep `index.html` and `mortgage_calculator.html` in sync when changing calculator UI or behavior, unless the user explicitly asks to change only one file.
3. Make small, focused edits. Do not rewrite unrelated layout, styling, or copy.
4. After any update that should affect the public GitHub site, commit the change and push it to `origin/main`.
5. Before pushing, run a quick check with `git diff` and `git status --short --branch`.
6. After pushing, confirm the commit hash and branch in the final response.

## Update Workflow

Use this flow whenever the user asks for an update:

```powershell
git status --short --branch
git diff
git add index.html mortgage_calculator.html AGENTS.md
git commit -m "Update mortgage calculator"
git push origin main
git status --short --branch
```

Adjust the commit message so it clearly describes the actual change.

## GitHub Desktop

The user has GitHub Desktop installed. It is useful for human review, but agents should still use command-line Git for routine updates.

- Use GitHub Desktop as a visual aid when the user wants to inspect changed files, commit history, or push status.
- Do not rely on GitHub Desktop being open before making updates.
- If command-line Git authentication fails, mention that GitHub Desktop may help the user confirm login status.
- Even when GitHub Desktop is available, completed updates should still be committed and pushed to `origin/main`.

## Validation

This is a static HTML project. For most text, default value, and simple UI changes:

- Check the relevant lines with `rg`.
- Review `git diff`.
- No build step is required.

For larger UI or JavaScript behavior changes:

- Open `index.html` in a browser or run a simple local static server.
- Verify the calculator still loads and updates results.
- Then commit and push.

## Deployment Expectation

`index.html` is the GitHub-published entry file. In this project, "update" means the change should go up to GitHub unless the user says otherwise.

Do not leave completed user-requested updates only in the local working tree.
