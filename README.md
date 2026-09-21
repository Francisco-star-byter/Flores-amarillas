# 🌻 Flores amarillas

Una flor amarilla en 3D que crece, se abre y entrega un mensaje escrito a mano.
Todo vive en un solo archivo: [`index.html`](index.html).

## Cómo verlo

Abre `index.html` en el navegador, o levanta un servidor local:

```bash
python -m http.server 8000
# luego abre http://localhost:8000
```

> Se recomienda el servidor local: la página usa módulos ES (`import`), que
> algunos navegadores bloquean al abrir el archivo directamente con `file://`.

## Cómo personalizarlo

Todo lo editable está junto, cerca del final de `index.html`:

```js
window.MENSAJE = {
  titulo: 'Para Hannita',
  texto: 'Tu mensaje aquí. Usa \n para saltos de línea.',
  firma: '💛',
};

// Color del fondo. Funciona mejor con tonos medios.
window.COLOR_FONDO = '#a67b5b';
```

## Detalles técnicos

- **Three.js 0.170** cargado desde CDN (jsDelivr) mediante un *import map* — sin
  instalación ni paso de build.
- Post-procesado con `EffectComposer` + `UnrealBloomPass` para el brillo.
- Geometría de la flor generada por código: pétalos, disco de semillas en
  espiral áurea, tallo y hojas.
- Notas musicales sintetizadas con la Web Audio API al abrirse la flor.
- Calidad adaptada a móviles (menos polígonos y menor *pixel ratio*).

## Licencia

MIT — ver [LICENSE](LICENSE).
