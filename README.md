# El Vórtice de los Cuatro Cielos

MMORPG de mitología chilena que se juega en el navegador. Hay tres facciones: **El Kultrun de Plata** (mapuche), **Los Custodios del Wintek** (selk'nam) y **La Cofradía de la Bruma** (chilota). Además están las fuerzas del Vórtice.

Está hecho con [Three.js](https://threejs.org/) y [Vite](https://vitejs.dev/). Todo el código es JavaScript; no hay servidor obligatorio.

---

## 0. Subirlo a GitHub por primera vez

1. Entra a [github.com/new](https://github.com/new) y crea un repositorio llamado `el-vortice-de-los-cuatro-cielos`. Déjalo **vacío**, sin README, sin .gitignore y sin licencia.
2. Descomprime este zip en tu computador. En una terminal, dentro de la carpeta descomprimida, escribe:
   ```bash
   git init
   git add .
   git commit -m "El Vórtice de los Cuatro Cielos"
   git branch -M main
   git remote add origin https://github.com/TU-USUARIO/el-vortice-de-los-cuatro-cielos.git
   git push -u origin main
   ```
   Cambia `TU-USUARIO` por tu nombre de usuario. Si GitHub pide contraseña, usa un *token* (Settings → Developer settings → Personal access tokens) o inicia sesión con [GitHub Desktop](https://desktop.github.com/).
3. **Sin terminal:** en la página del repositorio vacío pulsa **uploading an existing file** y arrastra **todo el contenido** de la carpeta. La carpeta oculta `.github` también debe subirse: es la que publica el juego. Si tu sistema la oculta, actívala: en Windows, Vista → Elementos ocultos; en Mac, `Cmd+Shift+.`.
4. Sigue el punto 4 de abajo para que el juego quede jugable en internet.

## 1. Ver el proyecto en GitHub

1. Entra a la página del repositorio (`github.com/TU-USUARIO/el-vortice-de-los-cuatro-cielos`).
2. Lo que necesitas está en estas carpetas:
   - **`src/`** tiene todo el código del juego (ver la tabla de abajo).
   - **`public/`** tiene los cuerpos 3D base, los retratos y el arte de los personajes.
   - **`index.html`** es la página del juego: pantallas, HUD y paneles.
3. Para editar un archivo directo en la web, ábrelo y pulsa el lápiz ✏️, o aprieta la tecla `.` (punto). Eso abre un editor tipo VS Code dentro del navegador.

## 2. Abrirlo en Visual Studio Code (en tu computador)

Necesitas tener instalados:
- [Git](https://git-scm.com/downloads)
- [Node.js 20 o más nuevo](https://nodejs.org/) (la versión LTS)
- [Visual Studio Code](https://code.visualstudio.com/)

Pasos:

1. En la página del repositorio pulsa el botón verde **Code** y copia la dirección HTTPS.
2. En VS Code: `Ctrl+Shift+P` (en Mac `Cmd+Shift+P`), luego **Git: Clone**. Pega la dirección y elige una carpeta.
   También puedes clonarlo desde una terminal:
   ```bash
   git clone https://github.com/TU-USUARIO/el-vortice-de-los-cuatro-cielos.git
   cd el-vortice-de-los-cuatro-cielos
   code .
   ```
3. En VS Code abre una terminal (menú **Terminal → New Terminal**) y escribe:
   ```bash
   npm install
   npm run dev
   ```
4. Abre la dirección que aparece (normalmente `http://localhost:5173`). El juego corre con tu tarjeta gráfica y **se recarga solo cada vez que guardas un archivo**.

Otros comandos:

| Comando | Qué hace |
|---|---|
| `npm run dev` | Abre el juego para desarrollar, con recarga automática |
| `npm run build` | Genera la versión final en `dist/` |
| `npm run preview` | Abre la versión final para probarla |

## 3. Guardar tus cambios en GitHub

Desde VS Code, en el ícono de **Source Control** (la ramita de la barra izquierda):
1. Escribe un mensaje que diga qué cambiaste.
2. Pulsa **Commit**.
3. Pulsa **Sync Changes**.

También puedes hacerlo desde la terminal:
```bash
git add .
git commit -m "Qué cambié"
git push
```

## 4. Publicarlo gratis con GitHub Pages

El repositorio ya trae el archivo `.github/workflows/pages.yml`, que publica el juego cada vez que subes cambios a `main`.

1. En GitHub ve a **Settings → Pages**.
2. En **Source** elige **GitHub Actions**.
3. Sube cualquier cambio o, en la pestaña **Actions**, ejecuta «Publicar en GitHub Pages».
4. El juego quedará en `https://TU-USUARIO.github.io/el-vortice-de-los-cuatro-cielos/`.

## 5. Mapa del código (`src/`)

| Archivo | Contenido |
|---|---|
| `main.js` | Bucle del juego: cámara de aventura, controles, combate (ira, 6 habilidades, combos, esquiva, derribos), gestos de cada habilidad, IA, HUD, inventario y mapa |
| `datos.js` | Personajes, facciones, atributos y habilidades |
| `heroe.js` | Cuerpos humanos con esqueleto, piel horneada, rostros, pelo por mechones con brillo anisotrópico, poses y animaciones (golpes, 15 gestos de habilidad, salto, nado, derribo) |
| `vestuario.js` | Ropa, armas y escudos de cada personaje, y los pobladores de las aldeas |
| `modelos.js`, `criaturas.js` | Modelos de seres no humanos |
| `bestiario.js`, `esculpir.js` | Bestias esculpidas (superficies implícitas) con venas, ojos y sigilos |
| `pintado.js` | Texturas pintadas a mano para armas y objetos |
| `arena.js` | Arenas de duelo, campeones, reliquias y Gran Campeón |
| `dialogos.js` | Diálogos con personalidad |
| `partidas.js` | Tres ranuras de guardado |
| `mundo.js`, `escenario.js` | Terreno, agua, bosques, rocas, aldeas y vallas |
| `lugares.js` | Lugares de las misiones (Claro del Rewe, Choza del Hain, Caleuche…) |
| `misiones.js`, `campana.js` | Las 6 sendas y 18 misiones, Mérito, objetos sagrados y poderes |
| `fisica.js` | Obstáculos sólidos, salto, nado |
| `efectos.js` | Chispas, sangre, polvo, ondas de choque, estelas, sacudida de cámara |
| `hierba.js` | Césped con viento |
| `pnj.js` | Pobladores, guardias y campamentos enemigos |
| `objetos3d.js`, `recoleccion.js` | Objetos sagrados en 3D y la cinemática al recogerlos |
| `intro.js` | Introducción cinematográfica (Colocolo, Kenos, Millalobo) |
| `sonido.js`, `voces.js` | Música y efectos sintetizados, y voces de los personajes |
| `red.js` | Modo en línea (opcional) |
| `estilo.css` | Estilos de la interfaz |

La carpeta `dev/` tiene los guiones de prueba automática (capturas con un navegador sin pantalla). No son necesarios para jugar ni para editar.

## Controles

WASD para moverse (de costado si tienes un objetivo) · Clic derecho y arrastrar gira la cámara, rueda para zoom · Espacio salta o sube a la superficie al nadar · Shift para correr · Q esquiva · 1–6 combate (repetir el 1 hace combo) · 7–8 poderes · Tab cambia de objetivo · E habla o recoge · I inventario · M mapa · J diario · F5 guarda rápido · F9 partidas · N silencio

---

Proyecto privado. Todos los derechos reservados.
