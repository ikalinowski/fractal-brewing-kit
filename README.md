# ☕ Fractal · Brewing Guides Kit

Sistema de guías de brewing para cafés de especialidad de **Fractal**.  
Cada café tiene su propia página HTML con recetas para V60, Origami, Aeropress y Chemex.

---

## Estructura del repositorio

```
fractal-brewing-kit/
│
├── assets/                    ← Recursos de marca (NO tocar)
│   ├── logo/
│   │   ├── fractal-isotipo.svg       ← Isotipo (flor de 4 pétalos)
│   │   ├── fractal-logo-completo.svg ← Logo con texto "fractal"
│   │   ├── fractal-sello.svg         ← Sello circular con slogan
│   │   └── fractal-logo-blanco.svg   ← Versión blanca para fondos oscuros
│   ├── icons/
│   │   ├── v60.svg
│   │   ├── origami.svg
│   │   ├── aeropress.svg
│   │   └── chemex.svg
│   └── patterns/
│       └── fractal-pattern.svg       ← Patrón repetitivo de isotipos
│
├── css/
│   └── fractal-brand.css             ← Sistema de diseño centralizado
│
├── guias/                            ← Una guía HTML por cada café
│   ├── efimero.html
│   ├── ninos-santos.html
│   ├── bosque-magico.html
│   └── ...
│
├── docs/
│   └── COMO-CREAR-NUEVA-GUIA.md     ← Instrucciones paso a paso
│
└── README.md                         ← Este archivo
```

---

## Cómo funciona

1. **Los logos viven en `assets/`** — son los archivos originales de tu diseñador. Nunca se modifican.
2. **El CSS de marca vive en `css/fractal-brand.css`** — define colores, tipografías y estilos de Fractal. Se importa desde cada guía.
3. **Las guías viven en `guias/`** — cada HTML importa el CSS y referencia los logos desde `assets/`. Si cambias el logo, se actualiza en todas las guías.

---

## Setup inicial (una sola vez)

### 1. Crear el repositorio en GitHub

1. Ve a [github.com/new](https://github.com/new)
2. Nombre: `fractal-brewing-kit`
3. Visibilidad: **Public** (necesario para GitHub Pages)
4. Crea el repositorio

### 2. Subir los archivos

Si usas GitHub Desktop (recomendado si no usas terminal):
1. Clona el repositorio a tu computadora
2. Copia toda esta estructura de carpetas dentro
3. Commit → Push

### 3. Activar GitHub Pages

1. Ve a **Settings → Pages** en tu repositorio
2. Source: **Deploy from a branch**
3. Branch: `main`, carpeta `/ (root)`
4. Guardar

Después de unos minutos, tus archivos estarán disponibles en:
```
https://TU-USUARIO.github.io/fractal-brewing-kit/assets/logo/fractal-isotipo.svg
https://TU-USUARIO.github.io/fractal-brewing-kit/guias/efimero.html
```

### 4. Reemplazar la URL base

En el archivo `css/fractal-brand.css`, cambia la línea:
```css
--f-assets-base: './assets';
```
Por tu URL real:
```css
--f-assets-base: 'https://TU-USUARIO.github.io/fractal-brewing-kit/assets';
```

---

## Cómo agregar un café nuevo

Ver instrucciones detalladas en [`docs/COMO-CREAR-NUEVA-GUIA.md`](docs/COMO-CREAR-NUEVA-GUIA.md)

**Versión rápida:**
1. Copia `guias/efimero.html`
2. Renómbralo con el nombre del café (ej: `ninos-santos.html`)
3. Cambia los datos del café en el bloque `<script>` al final
4. Commit → Push → Listo

---

## Colores de marca (referencia rápida)

| Color | Hex | Uso |
|-------|-----|-----|
| Verde Fractal | `#005347` | Color principal |
| Verde Claro | `#A7EC81` | Acentos, badges |
| Crema | `#F0EEE9` | Fondos |
| Rosa | `#F37FE1` | Acento secundario |
| Azul | `#2A7DE1` | Acento secundario |
| Negro | `#000000` | Textos fuertes |

## Tipografía

- **Logo**: CM Geon Regular (no se usa en web, solo en el archivo SVG del logo)
- **Cuerpo**: [Outfit](https://fonts.google.com/specimen/Outfit) — Light (300), Regular (400), Semibold (600), Bold (700)

---

*Siente lo auténtico · Celebra la variedad*
