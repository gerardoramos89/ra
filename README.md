# GRTEC WebAR

GitHub Pages root-ready project.

## Structure

- `index.html` — GitHub Pages entry point
- `app.min.js` — WebAR logic
- `assets/fotografia.mind` — generate/upload your photography target
- `assets/logo-grtec.mind` — generate/upload your GRTEC logo target

## GitHub Pages

Set:

`Settings → Pages → Deploy from a branch → main → /(root)`

Then the site will be:

`https://gerardoramos89.github.io/ra/`

## Important

The two `.mind` files are generated from their respective target images with the official MindAR Image Targets Compiler. They are not fabricated in this ZIP.

For simultaneous recognition of both markers in one camera session, use one combined `targets.mind` with target 0 = photograph and target 1 = logo.
