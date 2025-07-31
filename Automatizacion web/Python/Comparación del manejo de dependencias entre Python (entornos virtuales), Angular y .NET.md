---
sr-due: 2025-07-30
sr-interval: 1
sr-ease: 230
---

#tipo-documento #review 
## Tabla de diferencias

| Característica                | Python (Entornos virtuales)                  | .NET (NuGet)                               | Angular (npm)                                  |
| ----------------------------- | -------------------------------------------- | ------------------------------------------ | ---------------------------------------------- |
| Gestión de dependencias       | `pip` + entornos virtuales (`venv`)          | `NuGet` + `.csproj`                        | `npm` + `package.json`                         |
| Aislamiento de intérprete     | Sí, crea intérprete local en entorno virtual | No, usa runtimes globales con side-by-side | No, usa Node.js global                         |
| Instalación de dependencias   | Dentro del entorno virtual (`.venv/lib`)     | Caché global y referencias locales         | Carpeta `node_modules` dentro del proyecto     |
| Activación necesaria          | Sí, manual                                   | No                                         | No                                             |
| Manejo de versiones múltiples | Requiere entornos virtuales para aislar      | Permite side-by-side de runtimes           | Versiones locales definidas en proyecto        |
| Conflictos en versiones       | Evitados con entornos virtuales              | Evitados con archivos `.csproj` y NuGet    | Evitados con carpetas locales y `package.json` |
## Analogía

- Python: el intérprete global es un motor único que usan todos los carros (proyectos). Los entornos virtuales crean mini garajes con motores propios para cada carro, evitando que cambios afecten a otros.
    
- .NET: permite tener múltiples motores instalados simultáneamente (side-by-side). Cada proyecto elige qué motor usar, sin necesidad de replicar todo el garaje.
    
- Angular: cada carro instala sus piezas (librerías) en su propio garaje (`node_modules`), pero todos usan el mismo motor global de Node.js.