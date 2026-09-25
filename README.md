# Dollhouse docs site

The public documentation for Dollhouse, built with [Mintlify](https://mintlify.com).

## Preview locally

```bash
cd docs-site
npx mintlify dev
```

That serves the site at `http://localhost:3000` with live reload. Node 18 or newer is required. If pages 404, run `npx mintlify dev` from this folder — `docs.json` must be in the working directory.

Check for broken internal links before shipping:

```bash
npx mintlify broken-links
```

## Deploy

The site deploys through the **Mintlify GitHub app**:

1. Install the Mintlify GitHub app on the repository from the Mintlify dashboard.
2. Point the project at this repository and set the content directory to `docs-site`.
3. Push to the default branch. Every push redeploys automatically.

There is no build step and no other CI to configure.

## Structure

- `docs.json` — theme, colours and navigation. Any new page must be added to a navigation group here or it will not appear.
- `*.mdx` — one file per page, each with `title` and `description` frontmatter.

Navigation groups: **Start here**, **The economics**, **Using Dollhouse**, **Trust & safety**.

## Writing rules for this site

These are not style preferences; they are what the content was reviewed against.

- Plain English. Short paragraphs. A header every few lines. One idea per sentence.
- No jargon without a one-line definition.
- "Voting" means buying a candidate during a round. Say "your buys are your votes."
- **Never** promise returns, appreciation or passive income, anywhere, in any form.
- Every risk from the disclosure lists appears on `risks.mdx`, and the important ones are repeated in-line where they are relevant.
- Every number must trace to `docs/DEPLOY_CONSTANTS.md` or `deployments/46630.json`. If a fact is uncertain, leave it out rather than guess.

## Sources of truth

| Fact | File |
|---|---|
| Every deploy-time number | `../docs/DEPLOY_CONSTANTS.md` |
| Testnet addresses | `../deployments/46630.json` |
| Risk disclosures | the contract review record kept internally for this project |
| Plain-language answers | the readiness Q&A kept internally for this project |
| Voice and UI copy | the UI design brief kept internally for this project |

Mainnet is not deployed. Keep `contracts.mdx` saying so until it is.
