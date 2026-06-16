# Instructions — Deploy to GitHub Pages

Este repo está migrado a [simonrodil.github.io](https://github.com/simonrodil/simonrodil.github.io),
donde el deploy se hace automáticamente desde `main` vía GitHub Pages nativo.

## Si quieres activar el deploy en este repo

1. **`.github/workflows/deploy.yml`** — Descomenta todas las líneas.
2. **`package.json`** — Restaura los scripts `predeploy` y `deploy` originales:
   ```json
   "predeploy": "npm run build",
   "deploy": "gh-pages -d dist"
   ```
3. **`vite.config.js`** — Verifica que `base` apunte al subpath correcto (ej: `'/simon-rodil-cv/'`).
4. En **GitHub → Settings → Pages**, selecciona la rama `gh-pages` como source (o la que uses en el workflow).

Luego, al pushear a `main`, el workflow compilará y publicará en la rama `gh-pages`.
