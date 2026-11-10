# Crossplay Solver (Web)

Open: https://rustinterry2.github.io/Crossplay-solver/

This single-page HTML app reproduces the Pyto version's import, preview, review, tile-editing, animated search and best-moves screens with the same blue/green tile palette and 15×15 premium board. It includes JavaScript implementations of the existing screenshot recognizer and move solver, using the original letter-template masks embedded losslessly in the HTML.

Photos and Files both use the browser's normal image picker, with no cropping. Screenshots stay local on the device. The solver downloads the ENABLE word list from a public mirror when first used, then uses the browser cache. Because this dictionary is not identical to Crossplay's proprietary dictionary, occasional words may be rejected by the game.

You can edit recognized letters, mark existing blank tiles, choose rack blanks, navigate the 10 best moves, save a PNG image and resume the last reviewed board in browser storage. The original screenshot itself is not persisted when the tab closes.

### Animated search

After **Find Best Move**, the app displays the same blue-and-premium 15×15 board while real, validated candidate placements appear in green approximately 13 times a second. The solver runs in a Web Worker and reports **actual** visited search states and tested word candidates. Only sampled valid moves are drawn, not every state. The preview stays onscreen for at least **two seconds**; if a search takes longer, the preview continues until completion. For a quick search, the app replays its genuine sampled moves rather than inventing words or counts. The **Back** button cancels the current search. The Best Moves screen remains unchanged.

The self-contained `index.html` includes its styles, JavaScript engine, board detection logic, and the saved recognition templates. No Pyto installation or backend is required.

Development checks: all inline scripts and the embedded worker pass JavaScript syntax checks. Move-search instrumentation preserves ranked results in a regression comparison, and a simulated browser/UI test confirms real green tile previews, counters, and a two-second minimum before results. The prior TINEA/A9/14-point regression scenario also passed. The complete iPhone Safari image-reading flow has not yet been verified on a physical iPhone.

## GitHub Pages setup

In **Settings → Pages**, select **Deploy from a branch**, choose `main` and `/ (root)`, then Save. The site will publish at https://rustinterry2.github.io/Crossplay-solver/ . The previous location https://rustinterry2.github.io/crossplay/ is retained until the new deployment has been verified.
