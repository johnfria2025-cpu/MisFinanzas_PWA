# Mis Finanzas — PWA

App de finanzas personales offline-first inspirada en tu modelo Tributi, en COP.
Tus datos viven **solo en tu dispositivo** (IndexedDB). Nada viaja a ningún servidor.

## Qué incluye

- **Inicio**: saldo del mes, ahorro vs meta 30% (anillo con semáforo verde/amarillo/rojo), deuda total, próximo gasto periódico, gasto por nivel (obligatorio / necesario / prescindible) y dona por categoría.
- **Flujo**: proyección de saldo acumulado mes a mes (encadenado, incluyendo periódicos), barras de ingresos vs egresos y resumen anual.
- **Deudas**: tus créditos con cuota, saldo y barra de avance de pago.
- **Periódicos**: SOAT, primas, impuestos, etc. con frecuencia, calendario del próximo vencimiento y provisión mensual prorrateada.
- **Ajustes**: exportar a Excel (.xlsx), respaldo/restauración JSON, meta de ahorro, saldo inicial, datos de ejemplo y borrado.

## Cómo instalarla en tu celular

Una PWA necesita servirse por **https** (o localhost) para instalarse. Tres opciones:

### Opción A — Hosting gratuito (recomendado)
1. Sube los 5 archivos (index.html, manifest.json, sw.js, icon-192.png, icon-512.png) a:
   - **Netlify Drop** (https://app.netlify.com/drop) — arrastras la carpeta y listo, o
   - **GitHub Pages**, **Vercel**, **Cloudflare Pages**.
2. Abre la URL en Chrome (Android) o Safari (iPhone).
3. Android: aparece "Instalar app" / "Agregar a pantalla de inicio".
   iPhone: botón Compartir → "Agregar a pantalla de inicio".

### Opción B — Probar en tu computador
```bash
cd carpeta-de-la-app
python3 -m http.server 8080
```
Abre http://localhost:8080 — se instala desde el menú de Chrome.

### Opción C — Solo abrir el archivo
Abre `index.html` directo en el navegador. Funciona todo **menos** la instalación como app y el modo offline (que requieren https). Útil para probar rápido.

## Respaldo / multidispositivo

No hay nube por diseño (privacidad y cero costo). Para tener tus datos en varios equipos:
- Ajustes → **Exportar respaldo (JSON)** y guarda el archivo en tu Drive.
- En el otro dispositivo: Ajustes → **Restaurar respaldo**.
- **Respaldar a Excel** te da un .xlsx para análisis o como copia de seguridad.

> Consejo: exporta un respaldo cada cierto tiempo. Si borras los datos del navegador, IndexedDB se va con ellos.

## Personalizar

Todo está en `index.html`. Los colores son variables CSS al inicio (`:root`).
Las listas de categorías están en las constantes `CATS_GASTO` y `CATS_ING`.
