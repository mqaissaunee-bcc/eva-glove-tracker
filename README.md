# EVA Glove Hydraulic Assist — Project Tracker

A single-page tracker for Cristian Fama's passive hydraulic grip-assistance project (advisor: Prof. Qaissaunee). It runs on GitHub Pages and saves its data back to this repository.

## Files

- `index.html` — the tracker
- `access.json` — created by setup; holds the GitHub token encrypted separately with each person's password
- `data.json` — created by setup; all tracker data. Every save is a commit, so the history is the version log.

## Using it

- **Edit content** (top right) turns on editing for the project summary, task and phase names, the materials list, the SWOT, and the suggestions. Changes save when you leave a field.
- **Settings** (top right) holds the project title and names, the Week 1 start date, presentation details, sign-out, a link to setup for renewing access, and backup download/restore.
- **Schedule:** with Edit content on, each phase on the Timeline tab gets start and end dates. The end date, week strip and slides follow. Milestones can be added on the Timeline tab and appear as diamonds on the week strip.
- **Glossary** lists technical terms from the project review with short starter definitions. Cristian checks and rewrites each one (Edit content), ticks it off, and picks which terms appear on the Key terms slide.
- **Presentation** builds slides from everything in the tracker. Add Cristian's own text (design decisions, challenges, conclusions) and speaker notes under each slide, hide slides you don't need, then **Present** (arrow keys, Esc to exit, N for notes) or **Print or save as PDF** (choose "Save as PDF" in the print dialog; one slide per page).
- Existing data from earlier versions carries over; the new content is added the first time someone edits it.

## People and access

Prof. Qaissaunee (the advisor account) sees a **People** section in Settings to add, remove, and reset passwords for others:

- **Editor** — same access as Cristian.
- **Viewer** — can see every tab, present, print, and download a backup, but can't change anything. Viewers use a second fine-grained token with **Contents: Read-only**, pasted once when adding the first viewer, so GitHub itself rejects any change they attempt.

Removing someone takes their password off the list. For an immediate cut-off on a device where they chose "Stay signed in," also replace the token (setup for the main token, People → Viewer token for viewers). Rerunning setup keeps viewers but resets the editor list to the two people entered there.

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
