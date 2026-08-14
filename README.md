# GRTEC WebAR — TWO .mind markers

## Important architecture note

You asked for two separate `.mind` files:

- `assets/fotografia.mind`
- `assets/logo-grtec.mind`

A single MindAR image-tracking scene uses **one `imageTargetSrc` at a time**. Therefore this project supports both `.mind` files through a marker selector:

### Photography

```text
https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPO/?marker=foto
```

Loads:

```text
assets/fotografia.mind
```

### GRTEC logo

```text
https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPO/?marker=logo
```

Loads:

```text
assets/logo-grtec.mind
```

## If you want BOTH markers recognized simultaneously

Do not use two `.mind` files. Generate **one combined `targets.mind`** containing both images. Then MindAR can use:

```text
targetIndex 0 → photography
targetIndex 1 → GRTEC logo
```

That is the correct architecture if the camera must recognize either marker at the same time.

## Generate the two files

Use the official MindAR Image Targets Compiler:

https://hiukim.github.io/mind-ar-js-doc/tools/compile/

Generate:

```text
fotografia.mind
```

from the wedding photograph.

Generate:

```text
logo-grtec.mind
```

from:

```text
target-source/logo-grtec.jpg
```

Then put them in:

```text
frontend/assets/
├── fotografia.mind
└── logo-grtec.mind
```

## GitHub Pages

Upload the **contents of `frontend/`** to the repository branch/folder configured for GitHub Pages.

The backend is separate because private media and secrets must never be placed in GitHub Pages.

## Security

Never put:

- database passwords
- API secrets
- `MEDIA_SECRET`
- private original photographs

inside the frontend.

Minification is not encryption.

## Recommended final commercial version

For the product you are building for photographers, I recommend eventually using **one combined `targets.mind`**. It gives the user the best experience:

```text
Open GRTEC WebAR
       ↓
Point camera at ANY supported physical marker
       ↓
┌───────────────────────┐
│ Photography → target 0│
│ Logo → target 1       │
└───────────────────────┘
       ↓
GRTEC knows what was recognized
       ↓
Shows the correct digital experience
```
