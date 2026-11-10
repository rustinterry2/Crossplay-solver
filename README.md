# Crossplay Solver (Web)

Open: https://rustinterry2.github.io/Crossplay-solver/

This single-page HTML app reproduces the Pyto version's import, preview, review, tile-editing and best-moves screens with the same blue/green tile palette and 15×15 premium board. It includes JavaScript implementations of the existing screenshot recognizer and move solver, using the original letter-template masks embedded losslessly in the HTML.

Photos and Files both use the browser's normal image picker, with no cropping. Screenshots stay local on the device. The solver downloads the ENABLE word list from a public mirror when first used, then uses the browser cache. Because this dictionary is not identical to Crossplay's proprietary dictionary, occasional words may be rejected by the game.

You can edit recognized letters, mark existing blank tiles, choose rack blanks, navigate the 10 best moves, save a PNG image and resume the last reviewed board in browser storage. The original screenshot itself is not persisted when the tab closes.

The self-contained `index.html` includes its styles, JavaScript engine, board detection logic, and the saved recognition templates. No Pyto installation or backend is required.

Development checks: JavaScript syntax and the prior TINEA/A9/14-point regression scenario passed. The complete iPhone Safari image-reading flow has not yet been verified on a physical iPhone.

## GitHub Pages setup

In **Settings → Pages**, select **Deploy from a branch**, choose `main` and `/ (root)`, then Save. The site will publish at https://rustinterry2.github.io/Crossplay-solver/ . The previous location https://rustinterry2.github.io/crossplay/ is retained until the new deployment has been verified.
