# AlanFong Education — GitHub Pages pilot

Three existing public teaching resources, grouped under one proposed address.

## Proposed public routes

These addresses are planned, not live until GitHub Pages deployment succeeds.

- `https://alanfong-education.github.io/`
- `https://alanfong-education.github.io/pairwheel/`
- `https://alanfong-education.github.io/circle-visualizer/`
- `https://alanfong-education.github.io/circle-mastery/`

The display name is **AlanFong Education**. Use stable, lowercase project slugs so later category changes do not require changing shared links.

## Publishing

1. Create the free GitHub organisation `alanfong-education`, owned by the existing personal account. Name availability must be confirmed by GitHub's registration form.
2. Create the public repository `alanfong-education/alanfong-education.github.io`.
3. Push this directory's contents to its `main` branch.
4. In repository **Settings → Pages**, select **Deploy from a branch**, branch **main**, folder **/docs**.
5. Wait for deployment, then verify all four public routes and their interactions on desktop and mobile.

`docs/` is the complete publication directory. It contains the landing page, three unchanged public applications, `.nojekyll`, and a favicon. It contains no source-project folders, credentials, assessment originals, student records, or local QA files.

The three app files were compared byte for byte with their existing Netlify releases on 3 October 2026. The landing page is new. Existing Netlify sites and the original project files were not modified.

## Migration considerations

- PairWheel stores settings and history in browser local storage using the `pairwheel.` prefix. Existing saved data at its Netlify address will not appear automatically at the new origin. This pilot does not migrate that data.
- PairWheel's existing input handler shares a 200 ms save delay between both lists. Extremely rapid edits across both fields can cancel the first pending save. Ordinary edits with each wheel visibly updated, spinning, and persistence after reload were tested. The pilot preserves the original app.
- The Circle Reference Visualizer uses the Tailwind CDN and Google Fonts. Hosting it on GitHub Pages does not make those dependencies available offline.
- The Mastery Sheet is designed as an A3 reference. Mobile reading and printing should be assessed separately from website hosting compatibility.
- Multiple projects under this domain share one browser origin. Keep storage keys unique and service workers scoped to individual project folders as the collection grows.
- Keep the old sites active during testing. Configure redirects only after checking the new public pages and any saved-data transition.
- Changing hosts alone does not reduce an existing paid Netlify subscription. Savings depend on actual usage, migrated traffic, and a later billing-plan decision.
- A custom domain can be added later. Moving again to a different origin will require another saved-data check.

## Local preview

From this directory, run `python3 -m http.server 8947 --bind 127.0.0.1 --directory docs`, then open `http://127.0.0.1:8947/`.
