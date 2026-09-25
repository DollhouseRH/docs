# Editing this folder offline

This is a guide for editing the copy in this folder without touching the rest of the repository. It is not part of the published site (it is not listed in `docs.json`, so Mintlify never renders it) and not part of the navigation `docs.json` builds.

## What a page is

Every `*.mdx` file in this folder is one published page: `launching-a-coin.mdx`, `rounds.mdx`, `faq.mdx`, and so on. `README.md` and this file are not pages; they are notes for whoever works on the folder.

## What not to touch

- **The frontmatter.** Every page starts with a block between two `---` lines:

  ```
  ---
  title: "Launching a coin"
  description: "Enter a coin into a round: what it costs, what you get, and what happens if you lose."
  ---
  ```

  Leave the two `---` lines and the field names (`title:`, `description:`) exactly as they are. You can reword the text inside the quotes if it needs it, but keep it short (this is what shows in search results and link previews) and keep the quotes.

- **Code blocks.** Anything fenced with three backticks (```` ``` ````) is example code, a shell command, or a diagram in text form. Leave the content between the fences alone unless you are certain a value inside it is wrong; a typo there breaks a command a reader might copy.

- **Table structure.** Every table is built from `|` characters. You can edit the text inside each cell, but keep the number of `|` characters on each row the same, including the `|---|---|` divider row under the header. Removing or adding a `|` breaks the whole table.

- **`audits.mdx`.** This page is a condensed mirror of the dated audit ledger kept internally for this project (not published in this repository). Don't rewrite findings, dates, or test counts here by hand; if something on this page looks wrong, flag it rather than editing it, since it needs to be checked against the ledger it mirrors.

- **Component tags** like `<Steps>`, `<Step title="...">`, `<Accordion title="...">`, `<Warning>`, `<Note>`, and `<CardGroup>`. These are Mintlify formatting, not plain text. You can edit the wording inside them, but keep the opening and closing tags (`<Warning>` ... `</Warning>`) paired and in place, and keep `title="..."` attributes quoted.

## House rules for wording

- No em dashes. Use a period, a comma, or "and" / "but" instead.
- No vendor names or AI names in the text (this includes naming any specific AI model, tool vendor, or assistant by name). Describe what was done, not who or what did it.
- Plain punctuation: straight quotes and apostrophes, not curly ones; no unusual symbols.
- No "simulat-" word family. If something was modelled or projected rather than measured live, say that instead.
- No wallet or contract addresses anywhere on the site.
- Every number on the site should trace back to the contracts or to `docs/DEPLOY_CONSTANTS.md`. Don't introduce a new number, percentage, or time window from memory; if you're not sure a number is still correct, leave it as is and flag it rather than guessing a replacement.

## Handing the edits back

When you're done, send back either the whole `docs-site` folder or just the files you changed, with the same filenames. The edits get re-scanned (for the house rules above, and against the contracts for any numbers) and re-exported before anything is published. Nothing you send is published automatically.
