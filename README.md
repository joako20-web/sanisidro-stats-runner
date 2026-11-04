# sanisidro-stats-runner

Ejecuta, con GitHub Actions, la actualización de datos y la web de estadísticas del San Isidro RC. Este repositorio **solo contiene los workflows**;
el código y los datos están en un repositorio privado.

## Web pública (GitHub Pages)

<https://joako20-web.github.io/sanisidro-stats-runner/>

- **`actualizar.yml`:** los martes (05:00 UTC) descarga las actas nuevas y guarda los datos en el repo privado.
- **`web.yml`:** genera la web estática con las estadísticas que la federación ya publica y la despliega en GitHub Pages. Se lanza a mano
  (`workflow_dispatch`), al terminar con éxito `actualizar` y cada lunes a las 03:00 UTC.
- **Cómo:** descarga el repo privado con la llave `BOT_DEPLOY_KEY`, ejecuta `python -m sibot web --salida _site`, añade los ficheros estáticos de `web/` y publica.
- **Activación (una sola vez):** ejecutar `despliegue/activar-pages.sh` del repo privado, que habilita Pages con origen «GitHub Actions» y lanza el workflow.
