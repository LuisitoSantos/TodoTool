# TodoTool

Sitio estático en español e inglés con conversores, calculadoras y utilidades que funcionan en el navegador. No requiere servidor, dependencias ni compilación.

## Publicar en Cloudflare Pages

1. Sube este proyecto a un repositorio Git.
2. En Cloudflare, abre **Workers & Pages → Create application → Pages → Connect to Git** y selecciona el repositorio.
3. Deja vacío el comando de compilación y configura ` / ` como directorio de salida.
4. Publica. Para una actualización, sube los cambios al repositorio conectado.

También puedes publicar los archivos estáticos con la opción de carga directa de Pages. La web se sirve desde `index.html` en la raíz.

## Estructura

- `index.html`: estructura y textos de la página.
- `styles.css`: estilos adaptables a móvil y escritorio.
- `app.js`: catálogo de herramientas y lógica que se ejecuta localmente en el navegador.

## Añadir herramientas

En `app.js`, registra una herramienta con `add(categoría, nombre, descripción, icono, campos, función)`. Las categorías disponibles son `conversores`, `calculadoras` y `utilidades`. Las funciones de cálculo reciben los campos del formulario como objeto y devuelven el texto del resultado.

La página incluye una unidad Native Banner de Adsterra en `#ad-slot` y el mismo banner estático de 160 × 300 en ambos laterales (`#ad-rail-left` y `#ad-rail-right`). Adsterra indica que las impresiones de un mismo código repetido se cuentan una vez por visitante único.

## Publicidad

El código de la unidad se encuentra en `index.html`. Para cambiarla, reemplaza allí el bloque de script y contenedor con el nuevo código obtenido de Adsterra. Si Rocket Loader está activo en Cloudflare, conserva `data-cfasync="false"` en el script. Revisa también los requisitos de consentimiento y privacidad aplicables a tus visitantes.
