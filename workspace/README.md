# Directorios del workspace

Los directorios `./workspace/lab*` pueden ser de dos tipos:

1. Vacíos en GitHub.
    - No vacío a nivel local en algún ordenador 
    - Incluye archivo `.gitkeep` para indicar que existe en algún lugar
2. De tipo `Git Submodule`
    - Añadidos/clonados con la orden `git submodule add <remote repo url>`
    - P.e. `<url>` puede ser la url de un repositorio remote de Azure Repos
    - Ejemplo: `git submodule add https://dev.azure.com/<organization>/<project>/_git/<Azure Repo Git>`
