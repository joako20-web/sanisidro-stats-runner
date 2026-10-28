# sanisidro-stats-runner

Ejecuta, con GitHub Actions, el bot de Telegram de estadísticas del San Isidro RC. Este repositorio **solo contiene los workflows**; el código,
los datos y el estado están en un repositorio privado.

## Web pública (GitHub Pages)

El workflow `web.yml` genera una web estática con las estadísticas que la federación ya publica y la despliega en GitHub Pages:
<https://joako20-web.github.io/sanisidro-stats-runner/>

- **Cuándo se actualiza:** a mano (`workflow_dispatch`), al terminar con éxito el workflow `actualizar` (martes) y cada lunes a las 03:00 UTC.
- **Cómo:** descarga el repo privado con la llave `BOT_DEPLOY_KEY`, ejecuta `python -m sibot web --salida _site`, añade los ficheros estáticos de `web/` y publica.
- **Buscadores:** la web es abierta, pero no se quiere indexar: lleva `robots.txt` con `Disallow: /` y `noindex` en todas las páginas. También incluye un `404.html` que redirige al inicio.
- **Activación (una sola vez):** ejecutar `despliegue/activar-pages.sh` del repo privado, que habilita Pages con origen «GitHub Actions» y lanza el workflow.
