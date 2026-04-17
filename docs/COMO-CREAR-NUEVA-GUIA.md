# Cómo crear una nueva guía de brewing

## Paso 1 · Copiar la plantilla

Copia el archivo `guias/efimero.html` y renómbralo con el nombre del nuevo café:

```
guias/efimero.html  →  guias/ninos-santos.html
```

## Paso 2 · Cambiar los datos del café (HTML)

Abre el archivo nuevo y busca estas secciones en el HTML:

### Origen (la píldora verde en la parte superior)
```html
<p class="hero-origin">Inkawasi · Cusco · 1850 msnm</p>
```
Cambia por los datos de tu café:
```html
<p class="hero-origin">Junín · Chanchamayo · 1650 msnm</p>
```

### Nombre del café
```html
<h1 class="hero-name">Efímero</h1>
```

### Varietal, proceso, productor y tueste
```html
<p class="hero-meta">Geisha · Lavado anaeróbico<br>Mario Quispe Torres · Tueste medio</p>
```

### Notas de cata
```html
<div class="pills">
  <span class="pill">Té de rosas</span>
  <span class="pill">Jazmín</span>
  <span class="pill">Flor de limón</span>
  <span class="pill">Lima dulce</span>
</div>
```
Cambia las notas. Puedes tener 3, 4 o 5 notas.

### Título de la página
```html
<title>Efímero · Fractal Brewing Guide</title>
```

## Paso 3 · Cambiar las recetas (JavaScript)

Al final del archivo está el bloque `<script>` con los datos de cada método. La estructura es:

```javascript
v60: {
  t1: [['1 : 16','Ratio'], ['15 g','Café'], ['240 ml','Agua']],    // Fila 1: ratio, café, agua
  t2: [['90 °C','Temp.'], ['2:20 min','Tiempo'], ['~1.30%','TDS']], // Fila 2: temp, tiempo, TDS
  g: 'Media',           // Tipo de molienda
  m: '~680–720 µm',     // Rango en micras
  s: [                  // Pasos de extracción (máx 4-5)
    ['Título del paso',  'Descripción del paso'],
    ['Título del paso',  'Descripción del paso'],
    // ...
  ],
  tip: 'Texto del tip al final de la receta'
}
```

Repite para `origami`, `aeropress` y `chemex`.

## Paso 4 · Verificar

1. Abre el archivo HTML en tu navegador (doble clic)
2. Verifica que las 4 pestañas (V60, Origami, Aeropress, Chemex) funcionen
3. Verifica que el logo se vea (si no se ve, es porque estás abriendo el archivo fuera de la estructura de carpetas)

## Paso 5 · Publicar

```bash
git add guias/nombre-del-cafe.html
git commit -m "Agregar guía de brewing: Nombre del Café"
git push
```

La guía estará disponible en:
```
https://TU-USUARIO.github.io/fractal-brewing-kit/guias/nombre-del-cafe.html
```

---

## Notas

- **NO modifiques** el CSS ni los archivos en `assets/` al crear una guía nueva
- Si necesitas agregar o quitar un método de brewing (ej: solo V60 y Chemex), necesitas modificar los botones en el HTML y los datos en el JavaScript
- Para pedir una guía nueva a Claude, envía el nombre del café, origen, varietal, proceso, notas de cata y los parámetros de cada método
