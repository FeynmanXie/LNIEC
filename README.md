# La négation — French negation practice quiz

A static, browser-only practice page for **intermediate French**, focused on negation (*ne … pas*, *plus*, *jamais*, *rien*, *personne*, *ni … ni*, *ne … que*, etc.). Questions and reference answers live in the frontend script—open the file locally; no install or build step required.

## Features

- **One question at a time**: Submit the current item to move on; use **Back** to review or change earlier answers (editing a submitted answer clears its “submitted” state until you submit again).
- **Submit exam**: On the last question, **Submit exam** shows your score and percentage; the countdown stops, and the UI keeps only your answers (it does not display the official answer key as text).
- **Timed mode (optional)**: Enable timed exam mode, pick a duration (15 / 30 / 45 / 60 minutes), then **Start timer**; when time runs out, the quiz submits automatically.
- **Reset**: Clears answers and the timer and restarts from question 1.

## Running locally

Open `index.html` in the project root in your browser.

To serve over HTTP (useful if `file://` causes issues in some browsers), from the project directory:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Project layout

| File | Role |
|------|------|
| `index.html` | Page structure and controls |
| `styles.css` | Styling |
| `script.js` | Parsing, grading, timer, and UI logic |

Question data comes from the `CORRECTION_TEXT` string at the top of `script.js`, parsed into section and item prompts plus reference answers. Grading normalizes input (case, accents, optional `Oui`/`Non` prefixes, slash-separated answer variants in the key, etc.).

## Editing questions

Edit the `CORRECTION_TEXT` string at the top of `script.js` and keep the same shape the parser expects:

- Section headers start with `1.`–`6.` and match the section title pattern (see `sectionPattern` in code).
- Items look like `n. prompt. answer` or `n. prompt? answer`; for questions, the answer follows `?`; for statements, it follows the first period.

Save and refresh the page to load changes.

## License and use

For personal study and mock exams only. Verify French wording against your course materials or instructor as needed.
