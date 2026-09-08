# compliai-dental-site

Source for **dentalcompliance.app**. Static site, no build step, deployed via Netlify
(project `compliai-dental`). Pushing to `main` deploys automatically.

## Layout

| Path | What it is |
|---|---|
| `index.html` | Homepage. Contains the Pickaxe screener embed. |
| `terms.html` | Terms, disclaimer, privacy policy, verdict key. Served at `/terms`. |
| `blog/index.html` | Blog listing. Served at `/blog`. |
| `blog/<slug>.html` | An individual post. Served at `/blog/<slug>`. |
| `blog/POST-TEMPLATE.html` | Scaffolding for new posts. Not linked, not indexed. |

## Publishing a post

1. Copy `blog/POST-TEMPLATE.html` to `blog/<slug>.html`.
2. Replace every `{{PLACEHOLDER}}`.
3. Add a card to `blog/index.html` between the `POSTS:START` / `POSTS:END` markers,
   newest first.
4. Add the same card to the blog section of `index.html` (keep it to the newest three).
5. Add the post URL to `sitemap.xml`.
6. Commit and push. Netlify deploys in about thirty seconds.

## Cross-posting with Dental Amplify

The same post may run in full on both dentalcompliance.app and dentalamplify.com
(`Viviannz/dental-amplify-site`).

Exactly one site is the original. **Both copies set `rel="canonical"` to the original
URL.** Google then credits one source and neither site is penalised for duplicate
content. Decide the canonical per post: compliance-first pieces belong here,
practice-growth pieces belong on Dental Amplify.

## Danger zones

- Do not change the Pickaxe deployment id `deployment-54520239-a257-4463-bd24-efa3de235da1`
  or remove the `<div>` that carries it.
- Do not remove the Pickaxe loader script before `</body>`.
- Do not remove the disclaimer from the footer or from under the screener.
- The screener's brain, its email gate and its theme all live in Pickaxe Studio,
  not in this repo.

## House style

UK English. No em dashes. Calm and clear, no hype. Never present a verdict as legal
advice, and never claim the tool is fully compliant or regulator-approved.
