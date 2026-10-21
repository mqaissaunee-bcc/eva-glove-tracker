# EVA Glove Hydraulic Assist — Project Tracker

A single-page tracker for Cristian Fama's passive hydraulic grip-assistance project (advisor: Prof. Qaissaunee). It runs on GitHub Pages and saves its data back to this repository.

## Files

- `index.html` — the tracker
- `access.json` — created by setup; holds the GitHub token encrypted separately with each person's password
- `data.json` — created by setup; all tracker data. Every save is a commit, so the history is the version log.

## Using it

- **Edit content** (top right) turns on editing for the project summary, task and phase names, the materials list, the SWOT, and the suggestions. Changes save when you leave a field.
- **Presentation** builds slides from everything in the tracker. Add Cristian's own text (design decisions, challenges, conclusions) and speaker notes under each slide, hide slides you don't need, then **Present** (arrow keys, Esc to exit, N for notes) or **Print or save as PDF** (choose "Save as PDF" in the print dialog; one slide per page).
- Existing data from earlier versions carries over; the new content is added the first time someone edits it.

## One-time setup

1. Put `index.html` in a dedicated repository (for example `eva-glove-tracker`) and turn on GitHub Pages (Settings → Pages → deploy from branch `main`, folder `/`).
2. Create a fine-grained personal access token (Settings → Developer settings → Personal access tokens → Fine-grained tokens):
   - Repository access: only this repository
   - Repository permissions: Contents → Read and write
   - Expiration: end of the project (for example June 30, 2027)
3. Open the Pages address with `?setup` at the end, for example
   `https://<owner>.github.io/eva-glove-tracker/?setup`
4. Fill in the repository details, paste the token, and choose a password for each person (12+ characters; a few random words works well). Click **Save access file to GitHub**.
5. Wait a minute or two for Pages to publish `access.json`, then share the plain address and Cristian's password with him.

## Renewing or changing passwords

Open the page with `?setup` again and enter a new token and/or new passwords. This overwrites `access.json`; `data.json` is untouched.

## Security notes

- The token is never stored in plain text in the repository. Anyone can download `access.json`, though, so strong passwords matter.
- `data.json` is readable by anyone who finds it in a public repository. Don't put anything private in the tracker.
- Keep the token limited to this one repository so it can't touch anything else.
- "Stay signed in on this device" keeps the token in that browser's storage. Use it only on your own devices.
