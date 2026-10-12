# Guía paso a paso: ver el notebook y publicarlo en GitHub (Windows)

Carpeta del proyecto: `C:\Users\doar9\OneDrive\Datos curiosos\paleta de colores\fashion-color-forecast`

---

## Parte 1 — Verlo primero en tu computador

### Opción rápida (sin instalar nada)
* Abre **`fashion_color_forecast.html`** con doble clic: es el notebook completo ya ejecutado, con gráficos y el paper, en el navegador.
* Abre **`data\color_database.xlsx`** en Excel: cada hoja tiene los colores pintados en las celdas.

### Opción completa (para ejecutar y modificar)
1. Instala **Python 3.11 o superior** desde https://www.python.org/downloads/ — en el instalador marca la casilla **"Add Python to PATH"**.
2. Abre la carpeta del proyecto en el Explorador, haz clic en la barra de dirección, escribe `cmd` y presiona Enter. Se abre una consola ya ubicada en la carpeta.
3. Instala las librerías:
   ```
   pip install -r requirements.txt
   ```
4. Abre Jupyter:
   ```
   jupyter notebook fashion_color_forecast.ipynb
   ```
5. En el navegador: menú **Kernel → Restart & Run All** (o **Run → Run All Cells**). Tarda unos 2 minutos y regenera el Excel y las figuras.

> Alternativa: **VS Code** con la extensión "Jupyter" abre el `.ipynb` directamente.

> ⚠️ OneDrive: si Excel tiene abierto `color_database.xlsx` mientras ejecutas el notebook, la última celda fallará al guardar. Cierra el Excel antes de ejecutar.

---

## Parte 2 — Publicarlo en GitHub

### Camino A: GitHub Desktop (recomendado, sin comandos)
1. Crea una cuenta en https://github.com (si aún no tienes).
2. Instala **GitHub Desktop**: https://desktop.github.com e inicia sesión con tu cuenta.
3. En GitHub Desktop: **File → Add local repository…** → elige la carpeta `fashion-color-forecast`.
   Aparecerá el aviso *"This directory does not appear to be a Git repository"* → clic en **"create a repository"** → **Create repository** (deja el nombre `fashion-color-forecast`; no marques README ni licencia porque ya existen).
4. Verás todos los archivos en la lista de cambios. Abajo a la izquierda escribe en *Summary*: `Initial commit: colour database, models, 2027 forecast and paper` → **Commit to main**.
5. Clic en **Publish repository** (arriba). Desmarca **"Keep this code private"** si quieres que sea público → **Publish repository**.
6. Listo: tu repositorio queda en `https://github.com/TU_USUARIO/fashion-color-forecast`. GitHub muestra el notebook con sus gráficos y el README con el pronóstico.

### Camino B: línea de comandos (Git)
1. Instala Git: https://git-scm.com/download/win
2. En la consola, dentro de la carpeta:
   ```
   git init
   git add .
   git commit -m "Initial commit: colour database, models, 2027 forecast and paper"
   git branch -M main
   ```
3. En github.com: botón **+ → New repository** → nombre `fashion-color-forecast` → **sin** README, .gitignore ni licencia → **Create repository**.
4. Conecta y sube (cambia TU_USUARIO):
   ```
   git remote add origin https://github.com/TU_USUARIO/fashion-color-forecast.git
   git push -u origin main
   ```
   La primera vez se abrirá una ventana para iniciar sesión en GitHub.

---

## Parte 3 — Mejoras opcionales después de publicar

* **Descripción y temas:** en la página del repo, ⚙️ junto a *About* → agrega una descripción y temas como `color-forecasting`, `pantone`, `machine-learning`, `time-series`.
* **Completar autoría:** en el notebook (Partes B y C) y en `paper/` reemplaza `[Affiliation to be completed]`.
* **DOI citable:** conecta el repositorio en https://zenodo.org (Log in with GitHub → activa el repo) y crea un *Release* en GitHub (`v1.0`): Zenodo genera un DOI automáticamente.
* **Pre-registro:** al subirlo antes de diciembre de 2026 la fecha del commit demuestra que el pronóstico se hizo antes del anuncio de Pantone. Cuando Pantone anuncie el color 2027, agrégalo a la lista `PANTONE` del notebook, vuelve a ejecutar y haz un nuevo commit con la evaluación.
* **Actualizar cambios:** tras editar archivos, en GitHub Desktop escribe un resumen → **Commit to main** → **Push origin** (o `git add . && git commit -m "mensaje" && git push`).
